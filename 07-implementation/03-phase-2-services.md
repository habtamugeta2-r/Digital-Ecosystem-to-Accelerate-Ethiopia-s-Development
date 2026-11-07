# 07.3 · Phase 2 — Services and Finance (Months 18–36)

*Part of [07 · Implementation](README.md)*

The phase where the platform stops being a marketplace and becomes an ecosystem. It is also the phase
where most platforms die — margin expansion is harder than growth.

---

## Objective

Convert the transaction base from Phase 1 into **recurring, higher-margin services**:

1. Advisory at scale (retention and data)
2. Logistics coordination (cost and reliability)
3. **Embedded credit (the margin engine)**
4. Input commerce (attach rate and agent income)
5. 2–4 regions, 3–5 commodities

---

## Expansion map

| Region | Commodity | Rationale | Timing |
|---|---|---|---|
| Oromia (existing) | Wheat, maize, teff | Base | M18 |
| Amhara (secure woredas) | Teff, wheat, sesame | Volume; sesame export | M21 |
| SNNPR / Sidama | Coffee, maize, pulses | Coffee premium; high value | M24 |
| Addis Ababa | Demand aggregation, milling | Buyer concentration | M18 |
| *Hold* | Tigray, contested areas | Security | Review quarterly |

**Rule: expand by adding a second region to an existing commodity before adding a new commodity to an
existing region.** Commodity expertise transfers more easily than regional trust.

---

## Module 1 — Advisory at scale

| Activity | Detail |
|---|---|
| Price SMS/IVR | Daily, by market, in 3 languages |
| Weather alerts | 2×/week, by woreda |
| Agronomic tips | By crop and growth stage, weekly |
| Pest/disease alerts | Event-driven, from MoA/EIAR |
| Plot-specific advice | Fertiliser timing/dose based on plot data |
| Agent-led sessions | Group sessions at cooperative meetings |

**Channels:** USSD (self-serve), IVR (push, low literacy), SMS (transactional), agent (high-touch),
radio (mass reach partnership).

**Cost:** ~ETB 1.2–2.0 per SMS; ~ETB 3–6 per IVR minute. At 180,000 farmers × 40 messages/year =
7.2 m messages = ETB 8.6–14.4 m. **This must be zero-rated or grant-funded**, or it destroys the P&L.

**Target:** ≥60% of registered farmers receive at least one advisory per month; ≥30% report taking an
action.

---

## Module 2 — Logistics

| Stage | Capability |
|---|---|
| M18 | Dispatch desk; contracted transporters; load board (spreadsheet) |
| M24 | Driver app; GPS tracking; digital proof of delivery |
| M30 | Backhaul matching; consolidated loads |
| M36 | Route optimisation; telematics integration |

**Target metrics:** cost per tonne-km −15% vs. baseline; on-time delivery ≥85%; empty-km share ≤25%.

**Structure:** asset-light. Contract with transporters, do not own trucks (except possibly 2–3 for
quality control on priority lanes).

---

## Module 3 — Embedded credit (the core of Phase 2)

```
   ┌─────────────────────────────────────────────────────────────┐
   │                    CREDIT PRODUCT FAMILY                    │
   ├─────────────────────────────────────────────────────────────┤
   │ 1. Input credit        → repaid at harvest from sale proceeds│
   │ 2. Harvest bridge      → short-term, secured by forward contract│
   │ 3. Agent float         → working capital for agent operations│
   │ 4. Mechanisation       → equipment/PAYGo                     │
   │ 5. Group lending       → cooperative-guaranteed              │
   │ 6. Index insurance     → rainfall/NDVI, input-cost cover     │
   └─────────────────────────────────────────────────────────────┘
```

### Sequencing

| Month | Milestone |
|---|---|
| 18–21 | Lender partner selection; term sheet; pilot product design |
| 21–24 | First 100 loans to the best-documented farmers (low risk) |
| 24–27 | Scale to 1,000 loans; measure repayment |
| 27–30 | Second lender; second product (agent float) |
| 30–33 | Insurance pilot (index) with a licensed insurer |
| 33–36 | 10,000+ loans outstanding; PAR-30 <5% |

### Preconditions before the first loan

- [ ] 2 complete seasons of transaction data for the borrower
- [ ] Lender agreement signed (platform = LSP)
- [ ] First-loss guarantee facility in place
- [ ] Consent mechanism live and audited
- [ ] Repayment deduction at settlement operational and tested
- [ ] Collections policy written and approved (no coercive practices)
- [ ] Grievance mechanism for borrowers
- [ ] Credit model documented and validated by an independent reviewer

**If any is missing, do not lend.** A bad first cohort poisons the lender relationship permanently.

### The underwriting model (initial, deliberately simple)

| Factor | Weight | Data source |
|---|---|---|
| Seasons transacted | 20% | Ledger |
| Volume (kg) | 15% | Ledger |
| On-time delivery | 20% | Ledger |
| Grade consistency | 10% | Grading records |
| Repayment history | 20% | Lender feedback |
| Cooperative guarantee | 10% | Cooperative agreement |
| Plot size and crop | 5% | Registry |

**Start with a rules-based scorecard, not machine learning.** With 10,000 loans, a transparent
scorecard outperforms an opaque model and is far easier to defend to a regulator and to the borrower.

---

## Module 4 — Input commerce

| Element | Approach |
|---|---|
| Suppliers | Accredited only: ATA-verified seed, MoA-approved fertiliser, registered agrochemicals |
| Inventory | Never owned by platform; supplier delivers to agent/cooperative |
| Payment | Farmer pays via wallet, or on credit (Module 3) |
| Quality | Batch tracking; complaint mechanism; supplier scorecard |
| Pricing | Transparent; compare with regional reference prices |

**Why it matters for agents:** input margin is the largest single line in agent income (ETB 24,000/year
at Year 3 in the model). Without it, agent retention fails.

---

## Regional expansion playbook (repeatable)

| Step | Duration | Detail |
|---|---|---|
| 1. Region assessment | 4 weeks | Surplus/deficit, roads, cooperatives, conflict risk, buyer presence |
| 2. Government engagement | 4–8 weeks | Regional bureau, cooperative promotion office |
| 3. Cooperative MoUs | 6–8 weeks | 5–10 cooperatives; member lists; delivery commitment |
| 4. Agent recruitment | 4–6 weeks | 40–60 agents; training; device distribution |
| 5. Buyer commitment | 4–6 weeks | ≥2 buyers with volume |
| 6. Collection points | 3–4 weeks | Warehouse agreements; weighing equipment |
| 7. Soft launch | 2 weeks | 50 farmers, 20 transactions |
| 8. Full launch | — | Open registration |
| **Total** | **~5–7 months per region** | |

**Do not launch a region without all five of: buyers, cooperatives, agents, collection points, and a
named field lead.**

---

## Team in Phase 2

| Function | FTE | Change |
|---|---|---|
| Engineering | 12 | +7 (credit, logistics, data) |
| Product/design | 4 | +2 |
| Field operations | 12 | +8 (regional leads + staff) |
| Agronomy | 5 | +3 |
| Credit and risk | 4 | new |
| Trading desk | 5 | +3 |
| Finance/reconciliation | 3 | +2 |
| Compliance/legal | 2 | +1 |
| Data/analytics | 2 | new |
| Management | 4 | +2 |
| **Total** | **53** | |

---

## Budget (ETB m, 18 months)

| Category | Amount |
|---|---|
| Salaries | 63.0 |
| Field operations and regional launches | 18.0 |
| Technology and comms | 10.8 |
| Cooperative and agent onboarding | 9.0 |
| Credit operations (incl. guarantee provision) | 12.0 |
| Marketing | 4.5 |
| Legal, audit, compliance | 4.5 |
| Office, equipment, admin | 6.0 |
| Contingency | 7.0 |
| **Total** | **134.8** |
| Revenue offset | (56.4) |
| **Net funding need** | **78.4** |

---

## Gate 2 → 3

| # | Criterion | Threshold |
|---|---|---|
| 1 | Active farmers | ≥150,000 |
| 2 | GMV annualised | ≥ETB 8 bn |
| 3 | Blended take rate | ≥1.7% |
| 4 | Lenders live | ≥2 |
| 5 | Loan repayment rate | ≥93% (PAR-30 <7%) |
| 6 | Input attach rate | ≥20% of active farmers |
| 7 | Post-harvest loss reduction | ≥5 pp vs. baseline |
| 8 | EBITDA | ≥−10% of revenue (clear line to break-even) |
| 9 | Agent retention | ≥75% at 12 months |
| 10 | Regional P&L | ≥2 regions contribution-positive |

---

## The three Phase 2 failure modes

| Failure | Mechanism | Prevention |
|---|---|---|
| **Lending too fast** | Early defaults consume the guarantee; lender exits | Cap the first cohort at 100 loans; scale only after 3 months of clean repayment |
| **Expanding too fast** | Regional launches without field leads; quality collapses | One region at a time, with a 6-month minimum |
| **Margin illusion** | Revenue grows, but cost to serve grows faster | Track contribution margin per transaction monthly, not quarterly |
