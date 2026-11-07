# 07.6 · Team and Organisation

*Part of [07 · Implementation](README.md)*

---

## 1. Hiring plan by phase

| Function | P0 | P1 | P2 | P3 | P4 | P5 |
|---|---|---|---|---|---|---|
| Engineering | 2 | 5 | 12 | 20 | 30 | 40 |
| Product / design | 1 | 2 | 4 | 7 | 10 | 12 |
| Data / analytics | 0 | 0 | 2 | 5 | 8 | 12 |
| Field operations | 1 | 4 | 12 | 22 | 30 | 35 |
| Agronomy | 1 | 2 | 5 | 8 | 10 | 12 |
| Credit & risk | 0 | 0 | 4 | 9 | 14 | 18 |
| Trading desk | 0 | 2 | 5 | 8 | 10 | 12 |
| Finance | 1 | 1 | 3 | 7 | 10 | 12 |
| Compliance / legal | 1 | 1 | 2 | 4 | 6 | 8 |
| HR / admin | 0 | 1 | 3 | 5 | 8 | 10 |
| Management | 2 | 2 | 4 | 5 | 7 | 8 |
| **Total** | **9** | **20** | **56** | **100** | **143** | **179** |

*Slightly higher than the phase summaries because those show average FTE; this shows year-end headcount.*

---

## 2. The first ten hires (in order)

| # | Role | Why this order |
|---|---|---|
| 1 | CEO | — |
| 2 | CTO | Architecture decisions are irreversible |
| 3 | **Field operations lead** | The business is field operations; hire before the 4th engineer |
| 4 | Lead backend engineer | Ledger, escrow, identity |
| 5 | Designer | USSD/IVR design is specialised and often done badly |
| 6 | Agronomist | Content credibility |
| 7 | Mobile/USSD engineer | The actual farmer interface |
| 8 | Compliance / legal | Licences, DPIA, data protection |
| 9 | BD / partnerships | Wallet, Fayda, buyers |
| 10 | Finance / operations | Reconciliation, cash control |

**The most common hiring error:** 6 engineers and 0 field staff. The product then solves a problem
nobody has.

---

## 3. Roles that are hard to fill in Ethiopia (and how to handle it)

| Role | Scarcity | Approach |
|---|---|---|
| Senior backend engineer (payments) | High | Remote hiring; diaspora; competitive USD-linked pay for critical roles |
| Data engineer | High | Train internally from strong analysts |
| Product designer (USSD/IVR) | Very high | Regional hire or consultant; document patterns internally |
| Credit risk analyst | Medium | Hire from MFI/banking sector |
| Agronomist with digital experience | High | Pair an agronomist with a product manager |
| Compliance/DPO | High | Fractional external counsel + internal coordinator |
| Field operations manager | Medium | Hire from NGOs/agri-input companies |

**Practical note:** the shortage of senior technical talent is a real constraint. Budget for **regional
salaries** for 3–5 senior roles rather than pretending local rates will attract them.

---

## 4. Organisation structure at Phase 3

```
                        ┌──────────┐
                        │   CEO    │
                        └────┬─────┘
        ┌────────────────┬───┴────┬─────────────────┐
        ▼                ▼        ▼                 ▼
   ┌─────────┐     ┌─────────┐ ┌──────────┐   ┌──────────┐
   │   CTO   │     │   COO   │ │   CFO    │   │  CRO     │
   │         │     │         │ │          │   │ (Risk)   │
   └────┬────┘     └────┬────┘ └────┬─────┘   └────┬─────┘
        │               │           │              │
   ┌────┴────┐     ┌────┴────┐ ┌────┴─────┐   ┌────┴─────┐
   │ Eng     │     │ Field   │ │ Finance  │   │ Credit   │
   │ Product │     │ Ops     │ │ Legal    │   │ Compliance│
   │ Data    │     │ Trading │ │ Admin    │   │ Security │
   │         │     │ Agro    │ │          │   │          │
   └─────────┘     └─────────┘ └──────────┘   └──────────┘
```

**Note the separate CRO.** In an agricultural credit platform, risk must not report to the person whose
incentive is volume. This is a governance requirement, not a preference.

---

## 5. Capability gaps and how to fill them

| Gap | Fill |
|---|---|
| Digital financial services experience | Advisor or board member from a bank/MFI |
| Commodity trading expertise | Hire a trading desk head with ECX or exporter experience |
| Government relations | Senior advisor with ministry experience (part-time) |
| Data science for credit | Partner with a research institution; hire one senior |
| UX for low-literacy users | Specialist consultant; field testing |
| Payments/ledger engineering | Contractor from a fintech; 6-month engagement |
| Cold chain (Phase 4) | Partner, do not hire |

---

## 6. Compensation philosophy

| Principle | Application |
|---|---|
| Pay competitively for critical technical roles | USD-linked for 3–5 roles |
| ESOP for the first 30 employees | 10–15% pool, 4-year vesting |
| Field staff paid for outcomes | Cooperative onboarding bonus, agent retention bonus |
| No commission on loan volume alone | Would incentivise reckless lending |
| Cooperative equity tranche separate | 5–10%, non-dilutive to ESOP |

---

## 7. The founder's job changes four times

| Phase | The CEO's real job |
|---|---|
| 0 | Regulatory and partnership negotiation |
| 1 | Being in the field, watching transactions happen |
| 2 | Hiring and building a management layer |
| 3 | Capital, governance, and external relationships |
| 4–5 | Institutional leadership and public accountability |

**Founders who stay in Phase 1 mode at Phase 3 stall the company.**

---

## 8. What to avoid

| Anti-pattern | Why it hurts |
|---|---|
| Large expatriate technical team | Cost, continuity, knowledge transfer failure |
| BPO/outsourced core engineering | Cannot maintain a ledger you do not understand |
| Hiring for growth before unit economics work | Burns runway |
| Two co-CEOs with unclear division | Decision paralysis |
| Field team on short-term contracts | Destroys the relationships that are the moat |
