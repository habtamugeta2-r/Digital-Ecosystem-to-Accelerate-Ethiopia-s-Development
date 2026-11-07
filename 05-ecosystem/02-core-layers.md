# 05.2 · The Three Core Layers

*Part of [05 · Proposed ecosystem](README.md)*

The core is what makes the platform infrastructure rather than an app. It is built once, owned by the
platform, and used by every module.

---

## 1. Identity and authentication

### 1.1 What it does

| Function | Implementation |
|---|---|
| eKYC at onboarding | Fayda biometric verification via FaydaVerse eSignet/OIDC |
| Authentication per session | PIN + OTP; biometric for higher-value actions |
| Role credentials | Farmer, cooperative officer, agent, buyer, transporter, staff, auditor |
| Agent binding | Agent identity bound to device and cooperative |
| Delegation | A cooperative officer can act for members with recorded authority |
| Fallback | Four-level hierarchy; never block a genuine farmer |
| Revocation | Instant; cascades to sessions and connected apps |

### 1.2 Why it is not just "login"

In Ethiopia, identity is not a UX convenience — it is the **economic unlock**:

| Without verified identity | With verified identity |
|---|---|
| No bank account | Account opening in minutes |
| No credit file | Credit history can begin |
| No enforceable contract | Contract with legal attribution |
| Subsidy leakage | Targeted, de-duplicated delivery |
| No traceability | Plot-level provenance for export |
| No accountability for agents | Every action attributable |

### 1.3 The design rules

1. **Fayda is the anchor; the platform is not an identity provider.**
2. **Never store biometric templates** — store the verification result and the Fayda reference.
3. **Always provide a path for a farmer whose biometrics fail.** India's experience shows exclusion
   through failed authentication is real and politically damaging.
4. **Publish access transparency** — tell the user by SMS when their data was accessed, by whom, and
   for what. This is the single cheapest trust-building feature available.
5. **Separate authentication from authorisation.** Identity proves who you are; the consent registry
   decides what can be done with your data.

### 1.4 Cost management

| Item | Unit cost | Control |
|---|---|---|
| Fayda verification | US$0.05–0.10 | Cache with validity period; re-verify only on material change |
| SMS OTP | ~ETB 0.3–1.0 | Batch; use USSD callback where possible |
| Biometric re-auth | per verification | Reserve for high-value actions (above ETB 50,000) |

At 1 million verifications/year: US$50–100k. At 10 million: US$500k–1 m. **Verification caching is a
material financial decision, not just a technical one.**

---

## 2. Payments and wallet orchestration

### 2.1 The abstraction

The platform does not have a wallet. It has a **routing and settlement layer** that speaks to every
rail:

```
Platform instruction
       │
       ▼
┌──────────────────┐
│  ROUTING ENGINE  │  rules: cost, speed, recipient preference, success rate, limits
└────────┬─────────┘
         │
   ┌─────┴─────┬──────────┬───────────┬─────────────┐
   ▼           ▼          ▼           ▼             ▼
telebirr    M-Pesa    Bank API    EthSwitch     Agent cash
 adapter     adapter   adapter      adapter       ledger
```

### 2.2 The five payment primitives

| Primitive | Use case | Notes |
|---|---|---|
| **Collect** | Buyer pays for an order | Into custodian escrow |
| **Disburse** | Pay farmer, transporter, agent | Single or bulk |
| **Split** | Divide one payment among parties | Farmer + transporter + platform fee |
| **Escrow** | Hold until condition met | Custodian-held; platform instructs |
| **Refund** | Return funds on dispute or failure | Reverses to original rail where possible |

Every module composes these five primitives. There are no bespoke payment flows.

### 2.3 Rail selection logic

| Condition | Route |
|---|---|
| Recipient prefers wallet and has one | telebirr or M-Pesa (by preference and success rate) |
| Recipient has a bank account | Bank transfer via EthSwitch |
| Amount > ETB 100,000 | Bank rail; dual approval |
| Recipient has no account | Agent cash-out (agent receives float, pays cash) |
| Rail outage | Automatic failover to next rail; notify |
| Cross-border | Licensed partner only |

### 2.4 The ledger

The ledger is the platform's most valuable technical asset. Requirements:

| Requirement | Implementation |
|---|---|
| Double-entry | Every transaction has balanced debits and credits |
| Append-only | Corrections are new entries, never edits |
| Event-sourced | Every state change is an event with actor, time, evidence |
| Idempotent | Client-generated idempotency key on every money movement |
| Reconcilable | Daily match against custodian and operator statements |
| Queryable by subject | Every farmer can see their own full history via USSD/SMS |
| Auditable | Immutable logs, retained ≥5 years |
| Portable | Farmer can request an export (data portability under 1321/2024) |

**Why this matters commercially:** the ledger *is* the credit history. Its completeness and integrity
determine whether a bank will lend against it. Treat it as a product, not a database table.

### 2.5 Float and liquidity

| Issue | Approach |
|---|---|
| Agent float | Agents hold working capital; platform provides a float line or partner credit after 3 months of history |
| Escrow float | Held by custodian; interest accrues per agreement (often to custodian) |
| Bulk disbursement | Pre-fund with the programme client; never pre-finance |
| Settlement timing | T+0/T+1 depending on rail; disclose to farmers |

---

## 3. Data, consent and API layer

This is the layer that does not exist anywhere in Ethiopia today, and the one that creates the moat.

### 3.1 Data domains

| Domain | Source | Owner | Access |
|---|---|---|---|
| **Identity** | FaydaVerse | Citizen / government | Platform stores reference only |
| **Farmer profile** | Registration + agent | Farmer (platform as processor) | Consent-gated |
| **Plot / land** | GPS capture + cooperative records | Farmer | Consent-gated |
| **Transactions** | Platform ledger | Farmer + platform (joint) | Consent-gated for third parties |
| **Prices** | ATI 6077, ECX, platform observations | Public / platform | Public (aggregated) |
| **Weather** | EthioMet, satellites | Public | Public |
| **Soil** | EthioSIS, CGIAR | Public | Public |
| **Grades** | ECX standards + platform grading | Platform + ECX | Public standards; platform results consent-gated |
| **Delivery performance** | Driver app + buyer confirmation | Platform | Counterparties |
| **Credit history** | Ledger + lender repayment | Farmer + lender | Consent-gated |

### 3.2 The consent registry

**The problem it solves:** a bank wants to underwrite a farmer using platform data. The farmer must
consent, specifically, revocably, and the platform must prove it. Proclamation 1321/2024 requires this.
Nothing in Ethiopia implements it for agriculture.

**The model:**

```
┌──────────┐   1. request access    ┌──────────────┐
│  LENDER  │ ─────────────────────► │   PLATFORM   │
│  (FIU)   │                        │   CONSENT    │
└──────────┘                        │   REGISTRY   │
     ▲                              └──────┬───────┘
     │ 5. time-limited, query-based        │ 2. request consent
     │    access to specific fields        ▼ (USSD/SMS/IVR + agent)
     │                              ┌──────────────┐
     │                              │    FARMER    │
     │                              └──────┬───────┘
     │                                     │ 3. grant / deny
     │                              ┌──────▼───────┐
     └──────────────────────────────│  4. TOKEN    │
                                    │  (purpose,   │
                                    │   scope,     │
                                    │   expiry)    │
                                    └──────────────┘
```

| Element | Specification |
|---|---|
| Granularity | Per-lender, per-purpose, per-field-group |
| Duration | 90 days default; renewable with fresh consent |
| Revocation | Immediate; lender notified; no further access |
| Transparency | Farmer can see every access by SMS/USSD |
| Audit | Every query logged: who, what, when, why |
| No bulk export | Query API only (single-subject, field-limited) |
| Purpose limitation | Credit assessment ≠ marketing ≠ research |

**Why this is the moat:** any competitor can copy a marketplace UI. Nobody can copy a consent registry
with a two-year history of verified, consented, queryable agricultural transaction data that lenders
already trust.

### 3.3 The API

| API | Audience | Example endpoints |
|---|---|---|
| **Public** | Everyone | `GET /prices?commodity=maize&market=Adama` |
| **Partner** | Lenders, insurers, NGOs | `POST /credit-eligibility`, `POST /consent/request` |
| **Developer** | Third parties | `GET /listings`, `POST /orders`, webhooks |
| **Internal** | Modules | Full domain access |

Standards: REST, JSON, OpenAPI 3.1 spec published, versioned (`/v1/`), rate-limited, webhook-based
events (`order.funded`, `delivery.confirmed`, `settlement.completed`). **Publish the spec even if the
endpoints are not yet live** — it signals infrastructure intent and attracts partners.

### 3.4 Data governance policy

| Principle | Implementation |
|---|---|
| Lawful, fair, transparent | Published privacy policy in 5 languages; consent at collection |
| Purpose limitation | Every dataset tagged with allowed purposes |
| Minimisation | No ethnicity, no religion, no household income unless required for a programme |
| Accuracy | Farmer can correct any record via USSD or agent |
| Storage limitation | Retention schedule; delete when purpose served (except where law requires retention) |
| Integrity and confidentiality | Encryption, access control, audit |
| Accountability | Named DPO; DPIA per module; breach register |
| Portability | Farmer can export to another provider |
| No automated decisions without explanation | Credit decisions must state the top three factors and offer human review |

---

## 4. How the three layers interact: one worked example

**A maize farmer in Arsi sells 40 quintals to a miller in Addis.**

| Step | Layer invoked | What happens |
|---|---|---|
| 1 | Identity | Agent verifies the farmer with Fayda (already cached from onboarding); farmer authenticates with PIN |
| 2 | Data | Platform shows the current Adama and Addis prices from the price service |
| 3 | Marketplace (module) | Farmer lists 40 q at a suggested price; three buyers bid |
| 4 | Identity | Buyer authenticated and KYC-verified via Fayda |
| 5 | Payments | Buyer accepts; custodian collects ETB 1,000,000 into escrow |
| 6 | Notification | Farmer receives SMS + IVR confirmation: "ETB 1,000,000 is held safe" |
| 7 | Logistics (module) | Truck booked; driver app captures pickup photo + geotag |
| 8 | Data | Weighbridge ticket recorded; grade sampled |
| 9 | Payments | Delivery confirmed; escrow splits: farmer ETB 970,000, transport ETB 20,000, platform ETB 10,000 |
| 10 | Ledger | Double-entry posted; farmer's history updated (40 q, on time, grade A) |
| 11 | Data / consent | Transaction becomes part of the farmer's verified record |
| 12 | Finance (module, later) | With 3 such transactions, the farmer is pre-approved for ETB 60,000 input credit — with consent |

**Every step reuses a core service. There is no bespoke code path.** That is the definition of a
platform.

---

## Decisions recorded

| Decision | Choice |
|---|---|
| Identity | Fayda-anchored, verification-only, no biometric storage |
| Payments | Five primitives, adapter per rail, custodian-held escrow |
| Ledger | Event-sourced, double-entry, append-only, farmer-visible |
| Consent | Purpose-based token registry, query-only access, SMS transparency |
| API | REST, versioned, OpenAPI-published, public price API from day one |
| Data governance | DPO appointed; DPIA per module; no ethnicity data |
