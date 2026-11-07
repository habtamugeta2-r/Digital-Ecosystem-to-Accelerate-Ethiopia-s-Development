# 07.1 · Phase 0 — Foundations (Months 0–6)

*Part of [07 · Implementation](README.md)*

Six months, no public launch, no farmers. The phase that determines whether the rest is possible.

---

## Objective

**Remove every external dependency before writing production code.** By the end of Phase 0 the team
should be able to transact on day one of Phase 1.

---

## Workstreams

### 1. Legal and regulatory (owner: CEO + counsel)

| Task | Deliverable | Deadline |
|---|---|---|
| Incorporate the operating company | Ethiopian PLC registered, TIN, bank account | M1 |
| Reserve cooperative equity tranche | Shareholder agreement clause (5–10%) | M1 |
| Draft the data protection framework | DPIA v1, privacy notice in 5 languages, retention schedule | M3 |
| **Written NBE positions on four questions** | Formal letter + reply | **M4** |
| Commodity trading licence (if acting as principal) | Licence or a decision not to trade as principal | M4 |
| Insurance distribution arrangement | Agreement with a licensed insurer (if offering insurance) | M5 |
| Agent agreement template | Contract reviewed by counsel | M3 |
| Buyer and seller terms | Terms of service in Amharic and English | M3 |
| IP assignment from founders | Clean cap table | M1 |

**The four NBE questions (do not proceed without written answers):**

1. Is escrow via a licensed bank/PSI sufficient, or does the platform need its own licence?
2. Can the platform act as agent for **two** wallet providers simultaneously?
3. Under what conditions may the platform share transaction data with a lender?
4. Can the platform originate and service loans as an LSP without a lending licence?

**Why this is first:** building a product that cannot legally operate is the most expensive mistake
available. Ambiguity is more dangerous than refusal, because it invites a build-then-prohibit outcome.

---

### 2. Partnerships (owner: CEO + BD)

| Partner | What is needed | Why |
|---|---|---|
| **FaydaVerse / NIDP** | Sandbox access, verification contract, pricing | Identity for every transaction |
| **telebirr (Ethio Telecom)** | Merchant agreement, settlement terms, USSD shortcode | Primary payment rail |
| **Safaricom M-Pesa** | Merchant agreement | Second rail; redundancy |
| **EthSwitch** | Interoperability terms | Wallet-to-bank settlement |
| **Partner bank (escrow)** | Custody agreement, escrow account, API | Funds never held by platform |
| **3–5 anchor buyers** | Signed letters of intent with volume commitments | Liquidity side first |
| **2–3 cooperatives / unions** | MoU with member lists and delivery commitments | Supply side |
| **ATI** | Content partnership, 8028/6077 integration | Advisory and prices |
| **EthioMet** | Weather data feed | Advisory |
| **Ethiopian Commodity Exchange** | Membership or access route | Price discovery, contract standards |
| **EQA** | Grading standards | Quality assurance |
| **MoA / regional bureau** | Letter of support, ideally a programme | Legitimacy |

**Rule: no partnership is real until there is a signed document and a named counterpart.**

---

### 3. Product and design (owner: CTO + design)

| Task | Deliverable |
|---|---|
| User research in the pilot region | 40 farmer interviews, 10 agent interviews, 10 buyer interviews |
| Channel decisions validated | Can farmers complete a USSD flow? Test with 30 real users |
| Language validation | Terminology for grades, prices, contracts in Amharic and Oromiffa |
| Escrow state machine | Specified, reviewed by legal and bank partner |
| Ledger design | Double-entry schema, invariants, audit trail |
| Fayda integration design | Registration flow, fallback levels, error handling |
| Agent app prototype | Offline-first, tested in low-connectivity conditions |
| Price API specification | Public spec published |
| Threat model | Security review of every flow |

**The most valuable Phase 0 activity is field research.** No amount of desk analysis substitutes for
watching a farmer try to use a USSD menu.

---

### 4. Operations design (owner: COO)

| Task | Deliverable |
|---|---|
| Pilot region and commodity confirmed | Oromia (Arsi/Bale wheat or Shewa maize/teff) with a named woreda list |
| Agent recruitment criteria | Selection rubric, training curriculum, commission structure |
| Warehouse and collection point plan | 3–5 locations identified, agreements drafted |
| Weighing and grading procedure | Standard operating procedure, equipment list |
| Logistics partner shortlist | 3 transporters assessed |
| Dispute resolution procedure | Written procedure, SLA, escalation matrix |
| Quality assurance standard | Sampling protocol, retained sample policy |
| Cash handling procedure | Cash-in/cash-out at agents, reconciliation |

---

### 5. Team (owner: CEO)

| Role | Count | Timing |
|---|---|---|
| CEO | 1 | M0 |
| CTO | 1 | M0 |
| Lead engineer | 1 | M1 |
| Mobile/USSD engineer | 1 | M2 |
| Backend engineer | 1 | M2 |
| Designer | 1 | M1 |
| Agronomist | 1 | M2 |
| Field operations lead | 1 | M1 |
| Compliance/legal | 1 (may be fractional) | M2 |
| Finance/admin | 1 | M2 |
| **Total** | **10** | |

**Hire the field operations lead before the fourth engineer.** Most teams invert this and regret it.

---

## Deliverables checklist

- [ ] Company registered; bank account open
- [ ] Cap table clean; ESOP and cooperative tranche reserved
- [ ] NBE correspondence complete (4 questions answered in writing)
- [ ] Escrow agreement signed with a licensed institution
- [ ] Merchant agreements with ≥1 wallet provider (ideally 2)
- [ ] FaydaVerse sandbox access; verification contract signed
- [ ] ≥3 anchor buyers with signed volume commitments
- [ ] ≥2 cooperatives with signed member supply commitments
- [ ] DPIA v1 complete; privacy notice published in 5 languages
- [ ] Terms of service, agent agreement, buyer agreement drafted
- [ ] Pilot region, woredas, commodities, and crop calendar defined
- [ ] Agent recruitment plan with 10 named candidates
- [ ] Warehouse/collection points identified
- [ ] Core product architecture documented and reviewed
- [ ] Threat model complete; security requirements set
- [ ] 12-month budget approved; seed committed
- [ ] Readiness review with an external advisor

---

## Gate 0 → 1

| Criterion | Threshold | Evidence |
|---|---|---|
| Legal basis | Escrow partner signed; NBE questions answered | Signed documents |
| Identity | Fayda sandbox working; verification contract | Successful test verification |
| Payments | ≥1 rail live in sandbox, preferably 2 | Test transaction |
| Demand | ≥3 anchor buyers with volume commitments | Signed LOIs |
| Supply | ≥2 cooperatives with member commitments | Signed MoUs |
| Product | Escrow + ledger + USSD listing flows functional in test | Demo |
| Team | 10 people; field lead in place | Org chart |
| Money | ≥ETB 20 m committed | Bank statement |

**If any of the first four is unresolved, delay Phase 1.** Launching without escrow or identity means
launching a spreadsheet with a logo.

---

## What Phase 0 costs

| Category | ETB m |
|---|---|
| Salaries (10 people, 6 months) | 7.2 |
| Legal, regulatory, compliance | 2.0 |
| Research, travel, field work | 1.5 |
| Software and infrastructure (pre-scale) | 0.8 |
| Partnership and networking costs | 0.5 |
| Office and admin | 0.6 |
| Contingency | 0.9 |
| **Total** | **13.5** |

---

## The five most common Phase 0 mistakes

| Mistake | Consequence | Antidote |
|---|---|---|
| Writing code before securing escrow | Product built on an illegal premise | Regulatory work first |
| Signing an MoU without named volumes | Fake partnership on the slide deck | Require numbers and dates |
| Hiring engineers before a field lead | Product built for an imaginary user | Field lead by month 1 |
| Skipping the DPIA | Retrofit is expensive and slows launch | Do it at design time |
| Underestimating government timelines | 3-month delays cascade | Start negotiations in month 1, buffer 2× |
