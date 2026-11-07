# 08.3 · Execution and Technology Risk

*Part of [08 · Risks](README.md)*

The platform can fail simply by being built badly. This file is about that.

---

## 1. The execution failure modes that kill agri-platforms

| Failure | Mechanism | Frequency |
|---|---|---|
| **Built before understood** | 18 months of engineering, then discovers farmers do not want it | Very common |
| **Over-engineered** | Microservices, ML, blockchain before 1,000 transactions | Common |
| **Under-engineered** | Spreadsheets and WhatsApp past 10,000 transactions | Common |
| **Data quality collapse** | Records entered retrospectively, by people with no incentive | Very common |
| **The demo trap** | Product works in Addis, fails in Arsi | Common |
| **Operations valued less than engineering** | Engineers outnumber field staff 5:1 | Very common |
| **No reconciliation** | Money in ≠ money out; nobody notices until audit | Occasional, fatal |

---

## 2. Technology risks

| # | Risk | L | I | Score | Mitigation |
|---|---|---|---|---|---|
| T1 | **Ledger inconsistency** (money doesn't balance) | 3 | 5 | 🔴 15 | Double-entry, append-only, daily reconciliation, invariant tests in CI |
| T2 | **Data loss** | 2 | 5 | 🟠 10 | Point-in-time recovery, offsite replication, tested restores monthly |
| T3 | **Identity integration failure** (Fayda outage or policy change) | 3 | 4 | 🟠 12 | Degraded mode: cached verification + agent attestation, tightened limits |
| T4 | Payment rail failure | 4 | 3 | 🟠 12 | Two rails; retry logic; manual fallback with dual control |
| T5 | Security breach | 3 | 5 | 🔴 15 | 3–6% of opex; pen testing; least privilege; encryption; incident plan |
| T6 | USSD gateway costs or performance | 3 | 3 | 🟡 9 | Negotiate zero-rated; cache; SMS fallback |
| T7 | Scalability failure at harvest peak | 3 | 3 | 🟡 9 | Load testing at 10× normal; queue-based design |
| T8 | Vendor lock-in (cloud, SMS) | 3 | 3 | 🟡 9 | Abstraction layers; multi-vendor where feasible |
| T9 | Poor offline behaviour | 4 | 3 | 🟠 12 | Offline-first agent app; ≥7 days queued; conflict resolution |
| T10 | Silent data corruption | 2 | 4 | 🟡 8 | Checksums; reconciliation; anomaly detection |

---

## 3. The five technical non-negotiables

### 3.1 The ledger must always balance

```
For every transaction: SUM(debits) == SUM(credits)
Verified in CI on every commit.
Reconciled against bank statements daily.
Any imbalance halts new transactions until resolved.
```

**Why:** a platform that cannot prove where money is cannot be trusted with money. This is the single
most important engineering property.

### 3.2 Every state change is idempotent

Payment APIs time out; networks drop; retries happen. Every operation carries an idempotency key. A
retried "release escrow" must not release twice.

### 3.3 The farmer always gets an independent notification

Every agent action affecting a farmer triggers an SMS directly to the farmer's phone (not the agent's).
This is the primary defence against agent fraud and the primary trust mechanism.

### 3.4 Offline is the default, not a feature

The agent app must work for **7 days without connectivity**, queue operations, and resolve conflicts on
reconnection. Connectivity in rural Ethiopia is not improving fast enough to assume otherwise.

### 3.5 Feature flags per region and commodity

Any module, region or commodity must be suspendable in seconds. This is the operational answer to
conflict, regulatory action and fraud.

---

## 4. Delivery risk: the build sequence

| Stage | Wrong | Right |
|---|---|---|
| Discovery | Write specs from a desk | 40 farmer interviews + observe 20 transactions |
| Design | Figma-first | Paper/USSD prototypes tested with real users |
| Build | 12 features, none complete | 1 flow end-to-end, then the next |
| Test | Unit tests only | End-to-end with real money, in the field |
| Launch | Big bang | 50 farmers, 20 transactions, then expand |
| Scale | Add regions | Fix unit economics first |

**The most expensive line of code is the one written for a flow that is later abandoned.** Spend the
time in discovery.

---

## 5. Operational execution risks

| # | Risk | L | I | Score | Mitigation |
|---|---|---|---|---|---|
| O1 | Harvest-peak capacity failure | 4 | 4 | 🔴 16 | Seasonal staffing; pre-booked logistics; capacity plan |
| O2 | **Agent fraud** | 4 | 4 | 🔴 16 | Independent SMS; spot audits; limits; clawback; police referral |
| O3 | Quality dispute spike | 4 | 3 | 🟠 12 | Grading SOP; retained samples; clear standards |
| O4 | Reconciliation backlog | 3 | 4 | 🟠 12 | Daily reconciliation; dedicated finance staff; automation |
| O5 | Cooperative governance failure | 3 | 3 | 🟡 9 | Screening; multiple cooperatives; member verification |
| O6 | Buyer defaults | 3 | 4 | 🟠 12 | Pre-funded escrow only; buyer limits |
| O7 | Staff turnover in field | 4 | 3 | 🟠 12 | Competitive pay; career path; local hiring |
| O8 | Poor local language support | 3 | 4 | 🟠 12 | 5 languages at Phase 2; native-speaker QA |

---

## 6. The security programme (budgeted at 3–6% of opex)

| Control | Detail |
|---|---|
| Identity and access | SSO; least privilege; MFA for staff; role-based agent access |
| Encryption | At rest (AES-256); in transit (TLS 1.3); field-level for PII |
| Key management | Rotated; hardware-backed where possible |
| Logging | Immutable audit log; every PII access recorded |
| Monitoring | Anomaly detection on transactions and agent behaviour |
| Penetration testing | Annual external + after major changes |
| Incident response | Documented plan; 72-hour breach notification |
| Vendor security | Due diligence on every processor |
| Backup | Daily; offsite; encrypted; restore tested monthly |
| Physical | Device encryption; screen locks; remote wipe for agent devices |
| Insider threat | Dual authorisation for payments; segregation of duties |
| Training | Annual for all staff; quarterly for agents |

**The fraud triangle applies to agents:** pressure (low income), opportunity (control of transactions),
rationalisation (the platform owes me). **The mitigation is economic** (adequate agent income) as much
as technical.

---

## 7. Business continuity

| Scenario | RTO | RPO | Plan |
|---|---|---|---|
| Data centre outage | 4 hours | 0 (sync replica) | Failover to secondary site |
| Payment rail outage | 2 hours | — | Switch to second rail; queue |
| Internet shutdown | 0 (no service) | — | USSD/SMS only; operations reduced |
| Loss of key staff | 2 weeks | — | Documentation; cross-training; deputies |
| Region inaccessible | 1 month | — | Suspend; redeploy; preserve data |
| Cyber incident | 24 hours | 1 hour | Isolate; restore; notify; investigate |

---

## 8. The execution discipline that matters most

**Ship one complete flow before starting the second.**

A farmer can list, receive a bid, accept, deliver and be paid — end to end, with real money, in a real
woreda, before the platform builds advisory, logistics, credit or anything else.

Every additional module multiplies complexity. A half-built platform with five modules is worth less
than a complete platform with one.
