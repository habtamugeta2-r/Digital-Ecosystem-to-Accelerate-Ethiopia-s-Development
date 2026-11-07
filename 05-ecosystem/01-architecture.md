# 05.1 · Architecture

*Part of [05 · Proposed ecosystem](README.md)*

---

## 1. The layer model

### Layer 0 — External rails (integrate, never build)

| Rail | Interface | Purpose |
|---|---|---|
| FaydaVerse / NIDP | eSignet OIDC authentication API; verification API; sandbox | Identity verification, KYC, eKYC |
| EthSwitch | Instant payments (EthioPay), EthQR, UGPP, ISO 20022 | Settlement and interoperability |
| telebirr | USSD, app API, merchant API, agent API | Wallet and cash network |
| M-Pesa Ethiopia | Daraja-style API, merchant API | Wallet and alternative rail |
| Banks (CBE, Dashen, Awash, etc.) | Host-to-host, ISO 20022, EthSwitch | Accounts, credit, bulk disbursement |
| Ethio Telecom / Safaricom | USSD short code, SMS gateway, bulk rates | Farmer-facing channels |
| EthioMet / ATI | Weather and agro-met data | Advisory |
| ATI 8028/6077 | Advisory content, price data | Content (not duplicative) |
| Ethio Telecom USSD | Short code provisioning | Universal access |
| AI Institute | Local-language speech and text models | Voice interfaces (later) |
| ECX | Grading, warehouse receipts | Quality and storage |

### Layer 1 — Shared core

| Component | Responsibility | Key design decision |
|---|---|---|
| **Identity service** | Fayda verification, session management, role credentials, agent binding, fallback hierarchy | Stateless verification; cache only the verification result and reference, never biometrics |
| **Payment orchestrator** | Route, escrow, split, disburse, reconcile | Adapter pattern per rail; double-entry ledger; idempotency keys |
| **Ledger** | Event-sourced, append-only transaction record | The source of truth for every balance and history |
| **Consent registry** | Store, version, enforce and audit every data-sharing consent | Query-based access; never bulk export |
| **Registry** | Farmers, plots, cooperatives, buyers, transporters, agents | Fayda-anchored; deduplicated |
| **Data services** | Prices, weather, soil, grades, yields | Blend public data and platform-observed data |
| **API gateway** | Auth, rate limiting, versioning, public and partner APIs | Versioned from day one |
| **Notification service** | SMS, IVR outbound, in-app, agent tasks | Multi-channel, multi-language |

### Layer 2 — Application modules

| Module | Primary users | Depends on |
|---|---|---|
| Marketplace & trade | Farmers, cooperatives, buyers | Identity, payments, ledger, registry, data |
| Advisory & data | Farmers | Identity, data, notification |
| Logistics | Cooperatives, transporters, buyers | Identity, payments, ledger, registry |
| Embedded finance | Farmers, lenders, insurers | Identity, ledger, consent, registry |
| Government & programmes | MoA, donors, NGOs | Identity, payments, ledger, consent |
| Developer platform | Third parties | API gateway, consent |

### Layer 3 — Channels

| Channel | Users | Technology |
|---|---|---|
| USSD | Farmers (no smartphone) | Operator-hosted menus; server-side session state |
| IVR | Farmers (low literacy) | Asterisk/FreeSWITCH-class PBX; recorded prompts |
| SMS | Farmers (push) | Bulk SMS gateway; short codes; local script support |
| Agent app | Cooperative agents | Android, offline-first (SQLite + sync queue) |
| Buyer app/web | Traders, processors, exporters | React Native / Progressive Web App |
| Driver app | Transporters | Android with GPS, POD capture, offline mode |
| Staff console | Operations, support, compliance | Web |
| Public price board | Cooperatives, public | SMS, IVR, printed board, public web page |
| Open API | Developers | REST + webhooks, sandbox |

---

## 2. Technology recommendations

| Layer | Recommendation | Rationale |
|---|---|---|
| Backend | Typed language (Go/TypeScript/Java/Kotlin); modular monolith with clear boundaries | Correctness and auditability over microservice fashion at this scale |
| Ledger | Event-sourced with an append-only journal; double-entry | Financial correctness; auditability; replay |
| Database | PostgreSQL (primary) + object storage for documents/images | Mature, cheap, well-understood; avoids exotic operational burden |
| Queue / events | Managed queue (SQS-class) or Kafka-lite (Redpanda) if scale requires | Reliable async for offline sync and notifications |
| Mobile | Android-first, Kotlin/Flutter; **strong offline mode** | Device and connectivity reality |
| Web | Server-rendered PWA, text-light, low-bandwidth | Data cost and device constraints |
| Hosting | Ethiopian data centre / national cloud + regional failover | Data residency compliance |
| Observability | Structured logs, metrics, tracing; alerting on payment anomalies | Financial systems need deep visibility |
| Security | Secrets manager, KMS, WAF, SIEM-lite | See [04.7](../04-constraints/07-security-and-fraud.md) |
| CI/CD | Automated tests including ledger invariants; staged rollout | Payment bugs are unrecoverable |
| Feature flags | Per-region, per-commodity toggles | Ability to suspend a commodity or region instantly |
| Consent | Purpose-based token model; per-lender, per-purpose grants | Compliance and product |

**Deliberately avoided:** microservices at launch (operational overhead); blockchain (the problem is
data capture, not consensus); custom ML at launch (no data yet); building an app store (no users yet).

---

## 3. Critical integration specifications

### 3.1 Fayda (identity)

```
Registration flow:
  1. Farmer visits cooperative agent with any ID (or none)
  2. Agent initiates Fayda authentication (fingerprint/iris/face)
  3. eSignet OIDC flow returns verified claims: name, DOB, sex, address, FIN
  4. Platform creates a farmer record keyed on FIN
  5. Farmer sets a 4-digit PIN for USSD/IVR
  6. Agent records: cooperative membership, plot location (GPS polygon or point), crops

Fallback if biometric fails:
  a. OTP to the phone number registered with Fayda (if any)
  b. Agent visual verification + OTP + recorded attestation + photo
  c. Cooperative officer countersignature + 24h cooling period
  d. NEVER: outright rejection of a genuine farmer
```

**FaydaVerse cost:** institutions pay US$0.05–0.10 per verification (from August 2026). At 1 million
verifications/year that is US$50–100k — a material but manageable line. Cache verification results
with a validity period to control cost.

### 3.2 Payments (escrow flow)

```
1. Buyer accepts listing → order created (state: PENDING_PAYMENT)
2. Platform calls custodian to reserve buyer funds (telebirr / M-Pesa / bank)
3. On reservation success → order state: FUNDED, farmer notified by SMS + IVR
4. Transporter assigned → pickup confirmed (photo + geotag)
5. Delivery → receiver OTP + photo + weighbridge ticket
6. Buyer acceptance → dispute window opens (48–72h)
7. On acceptance/expiry → platform instructs custodian:
       farmer_payout = gross − platform_fee − freight (if platform-paid)
8. Settlement confirmation → SMS + IVR to farmer; ledger updated
9. Reconciliation job matches custodian statements to ledger daily
```

**Invariants (tested in CI):**
- Sum of all ledger entries = 0 at every point.
- No order can be in two states simultaneously.
- Every state transition is logged with actor, timestamp and evidence.
- Funds never leave escrow without a delivery confirmation or an explicit adjudication.

### 3.3 USSD session handling

| Constraint | Handling |
|---|---|
| 182-char screens | Numbered menus; no prose |
| Session timeout | Server-side state keyed by MSISDN + session ID; resume on next dial |
| No rich input | Numeric commodity and market codes; printed cards at cooperatives |
| Cost per session | Negotiate zero-rating; otherwise batch into one session |
| Concurrency | Queue campaigns; avoid simultaneous broadcasts to a whole woreda |
| Confirmation | Always end with an SMS receipt (so the record survives the session) |

---

## 4. Non-functional requirements

| Requirement | Target |
|---|---|
| Availability (core) | 99.5% Phase 1 → 99.9% Phase 3 |
| Payment transaction integrity | 100% (no lost or duplicated payments) |
| USSD response time | <3 seconds per screen |
| IVR response time | <2 seconds |
| SMS delivery | <60 seconds (95th percentile) |
| Offline tolerance (agent app) | ≥7 days of queued transactions |
| Data residency | 100% in Ethiopia |
| Backup RPO / RTO | 15 min / 4 h |
| Consent propagation | Immediate on revocation |
| Audit retention | ≥5 years (align to NBE requirements) |
| Accessibility | Works on Android 8+, 2G fallback, 4" screen |
| Language coverage | 2–3 at MVP, 5 by Phase 2 |
| Security | Annual pen test; quarterly vulnerability scan; 72h breach notification |

---

## 5. Environments and rollout

| Environment | Purpose | Data |
|---|---|---|
| Local dev | Engineering | Synthetic |
| Sandbox | FaydaVerse test credentials, partner integration | Synthetic |
| Staging | Full integration, UAT with cooperatives | Synthetic + anonymised |
| Pilot (production) | One region, one commodity | Real |
| Production | Scaled | Real |

**Feature flags** control: region enablement, commodity enablement, module enablement, fee schedules,
language availability, agent limits. This is how a conflict-affected region is suspended without
shutting down the platform.

---

## 6. Team and build sequence

| Phase | Engineering team | Focus |
|---|---|---|
| 0 (M0–4) | 4–6 (1 lead, 2 backend, 1 Android, 1 integrations, 1 QA/DevOps) | Core: identity, payments, ledger, USSD, agent app |
| 1 (M3–12) | 8–10 | Marketplace, escrow, SMS/IVR, ops console |
| 2 (M9–24) | 15–20 | Advisory, logistics, finance, consent service, buyer app |
| 3 (M18–42) | 25–35 | Scale, multi-region, multi-commodity, data platform |
| 4 (M36–60) | 35–50 | Open API, developer platform, partner integrations |

**Critical hires outside engineering:** agronomist(s), cooperative relations lead, logistics operations
manager, compliance officer, data protection officer, regional field managers, and a head of product
with FMCG/agriculture experience — not a pure software product manager.

---

## 7. Architecture anti-patterns to avoid

| Anti-pattern | Why it fails here | Instead |
|---|---|---|
| App-only product | 58% phone ownership, 22% internet | USSD/IVR/agent channels |
| Microservices at launch | Operational burden with no scale benefit | Modular monolith |
| Storing biometrics | Catastrophic breach impact; illegal under 1284/2023 without basis | Verify through FaydaVerse |
| Holding customer funds | Licensing requirement; fraud exposure | Custodian partners |
| Custom identity or wallet | Duplicates national infrastructure | Integrate |
| Blockchain for traceability (first) | Solves the wrong problem | Append-only conventional ledger; revisit if a regulator requires |
| Rebuilding advisory content | Duplicates ATI's 10+ years of work | Licence and extend |
| Multi-country ambition at launch | The Jumia failure mode | One region, one commodity |

---

## Decisions recorded

| Decision | Choice | Reversible? |
|---|---|---|
| Backend style | Modular monolith | Yes |
| Ledger | Event-sourced, double-entry, append-only | No (foundational) |
| Identity | FaydaVerse only, no local biometric storage | No |
| Custody | Licensed partner | Yes |
| Primary channel | USSD + IVR + agent | No |
| Hosting | Ethiopia | No |
| Mobile framework | Native Android / Flutter | Yes |
| API style | REST + webhooks, versioned | Yes |
