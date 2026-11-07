# 02 · Opportunities for Digital Infrastructure

*What follows from the diagnosis in [01 · Context](../01-context/README.md)*

The question this section answers: **given the constraints, where could software and digital
platforms make a large difference in Ethiopia — and which single opportunity is largest?**

---

## Files in this section

| File | Opportunity | Rank |
|---|---|---|
| [`01-agriculture-platform.md`](01-agriculture-platform.md) | **Agriculture supply-chain platform** — the flagship | **1** |
| [`02-digital-financial-services.md`](02-digital-financial-services.md) | Payments, credit, savings, insurance, remittances | 4 |
| [`03-marketplaces-and-logistics.md`](03-marketplaces-and-logistics.md) | Urban/SME e-commerce, freight and last-mile | 2 & 3 |
| [`04-government-and-public-services.md`](04-government-and-public-services.md) | Digital ID-linked e-services, subsidies, open data | 5 |
| [`05-connectivity-and-infrastructure.md`](05-connectivity-and-infrastructure.md) | Telecoms, power, devices — the enabling layer | enabling |
| [`06-scoring-and-ranking.md`](06-scoring-and-ranking.md) | The full comparison matrix and reasoning | — |

---

## 1. The candidate set

Six opportunity areas pass an initial screen (digital leverage is high *and* the problem is large):

1. **Agriculture** — advisory, market linkage, aggregation, traceability, insurance, mechanisation
   access, input supply.
2. **Marketplaces and logistics** — consumer/SME commerce, freight matching, last-mile delivery.
3. **Digital financial services** — mobile money, credit, savings, insurance, remittances, merchant
   acquiring.
4. **Government and public services** — e-services, permits, tax, subsidy and transfer delivery,
   open data.
5. **Human capital** — digital health and education delivery.
6. **Connectivity and infrastructure** — the enabling layer that determines what is possible.

---

## 2. The scoring method

Each opportunity is scored 1–5 on eight criteria. Scores are judgements, stated with their reasoning
in [`06-scoring-and-ranking.md`](06-scoring-and-ranking.md).

| Criterion | What it measures | Why it matters in Ethiopia |
|---|---|---|
| **Scale** | Number of people whose lives materially change | Poverty is rural and agricultural; an urban-only product touches ~24% of the population |
| **Depth** | Size of the income/price/quality change per person | A 1% fee on a large transaction is worth more than a subscription from a subsistence household |
| **Digital leverage** | How much of the problem is information/coordination rather than capital/steel | Digital can fix information; it cannot fix roads |
| **Feasibility now** | Can it be built and operated with today's rails, laws and skills | 21.7% internet penetration and 44% Tier-1 power are hard limits |
| **Evidence** | Does the intervention have demonstrated effect, ideally in Ethiopia | Avoids repeating failed pilots |
| **Moat** | Does success compound into something hard to copy | Needed to justify investment |
| **Policy fit** | Alignment with DAR, NAFIR, NDPS, Digital Ethiopia 2030 | Unlocks co-funding and reduces political risk |
| **Risk** | Exposure to conflict, FX, regulatory reversal, incumbent response | Ethiopia's risk profile is elevated |

---

## 3. The result

| Rank | Opportunity | Scale | Depth | Leverage | Feasible | Evidence | Moat | Policy | Risk control | **Total** |
|---|---|---|---|---|---|---|---|---|---|---|
| **1** | Agriculture supply-chain platform | 5 | 5 | 5 | 3 | 4 | 5 | 5 | 3 | **35** |
| 2 | Digital financial services | 4 | 4 | 5 | 4 | 5 | 3 | 5 | 3 | **33** |
| 3 | Marketplaces & logistics (urban/SME) | 3 | 3 | 4 | 4 | 2 | 3 | 3 | 4 | **26** |
| 4 | Government & public services | 5 | 3 | 5 | 2 | 4 | 1 | 5 | 2 | **27** |
| 5 | Human capital (health/education) | 4 | 3 | 3 | 2 | 3 | 2 | 4 | 3 | **24** |
| 6 | Connectivity/infrastructure | 5 | 5 | 1 | 1 | 4 | 2 | 5 | 2 | **25** |

*(Connectivity scores highest on scale and depth but lowest on digital leverage and feasibility for a
software organisation — it is an enabler to be leveraged, not an opportunity to be entered.)*

**The ranking is not the whole story.** The insight from the scoring is that the top four are not
four separate businesses — they are **one business with four revenue lines**:

```
                    ┌──────────────────────────┐
                    │  AGRICULTURE PLATFORM    │
                    │  (marketplace + advisory)│
                    └────────────┬─────────────┘
                                 │
        ┌────────────────────────┼────────────────────────┐
        ▼                        ▼                        ▼
  LOGISTICS MODULE        EMBEDDED FINANCE        GOV/NGO PROGRAMMES
  (freight matching,      (credit, savings,       (subsidy delivery,
   last mile, storage)     insurance)              extension, M&E)
        │                        │                        │
        └────────────────────────┴────────────────────────┘
                                 │
                                 ▼
                    URBAN / SME COMMERCE
                    (reuses the same logistics,
                     payments and identity rails)
```

This is the strategic argument of the whole dossier: **build one thing well, and three of the other
five opportunities fall out of it for free.**

---

## 4. Why agriculture wins, in five sentences

1. It is the only sector large enough to change national poverty: ~60% of employment and ~32% of
   GDP, with >95% of output from 12+ million smallholders.
2. Its inefficiencies are concentrated, measurable and addressable: 15–25% post-harvest loss, 20–40%
   seasonal price swings, ~2% of credit demand met, ~13% paved roads.
3. It is where Ethiopia's newly built digital rails (Fayda identity, interoperable mobile money,
   EthSwitch, DAR) have the least existing application layer — high leverage, low saturation.
4. The government has already declared it the priority (DAR 2032, NAFIR, Post-Harvest Strategy,
   Digital Ethiopia 2030), which supplies policy cover, co-funding and a counterpart.
5. It generates the two assets that compound: **verified transaction history** (which unlocks
   finance) and **farmer relationships** (which are the hardest thing for a competitor, including the
   state, to replicate).

---

## 5. What is explicitly *not* recommended

| Idea | Why not (yet) |
|---|---|
| A consumer "super-app" | Requires either messaging scale or subsidy; Ethiopia's digital purchase rate is 1% |
| A national e-commerce "Amazon" | Jumia's 11 years of losses and 5 market exits; 58% of Ethiopian e-commerce startups earn under US$10k/yr |
| A new payment network or wallet | telebirr (60.6 m), M-Pesa (5.2 m) and EthSwitch already exist; a fourth wallet adds nothing |
| A new identity system | Fayda is national, mandatory, and free to citizens |
| A blockchain-first traceability product | The problem is data capture and grading, not consensus; use conventional append-only records until a regulator asks otherwise |
| Lending on your own balance sheet in Phase 1 | Regulatory capital, and you have no underwriting data yet — partner first |
| Drone/drone-as-a-service precision agriculture | Small farms, thin margins, regulatory restrictions, minimal evidence at Ethiopian scale |
| Building rural broadband | Requires a telecom licence and capex that no startup can carry |

---

## 6. The "multiplier effect" claim, tested

The source brief argued that one intervention in agriculture has multiplier effects. That claim is
correct but often stated loosely. Here is the precise mechanism:

| Step | Effect | Evidence |
|---|---|---|
| Transparent price + aggregated sale | Farmer realises 5–15% higher net price | Price-information studies in Ethiopia (Haile et al.) find measurable welfare gains from mobile price information |
| Better price → higher income | Household crosses a resilience threshold | M-Pesa's measured effect was via risk-sharing, not income magic — but income still matters |
| Scheduled pickup + grading | Post-harvest loss falls | Loss reduction is the most mechanical, least contested benefit |
| Verified transaction history | Access to credit at 1/10th the underwriting cost | 2% of credit demand met today; cash-flow lending is the standard workaround |
| Credit buys inputs | Yield rises 14–25% (demonstrated for improved advisory + inputs) | CGIAR/AICCRA; site-specific advisory |
| Higher yield → more volume on platform | Fee revenue grows without new customer acquisition | Network economics |
| Volume → better data → better underwriting | Lower loss rates, lower interest rates | Standard fintech unit economics |
| Everything above → higher tax base, lower aid need | Fiscal and political dividend | India DBT analogue |

The multiplier is real **only if all four links hold**: price, loss, credit, yield. A price board
alone does not do it. A marketplace without finance does not do it. This is why the proposed design
puts the marketplace and the finance module in the same organisation, in that order.

---

## Read next

- The flagship opportunity in depth: [`01-agriculture-platform.md`](01-agriculture-platform.md)
- How it is architected: [`../05-ecosystem/`](../05-ecosystem/README.md)
- How it makes money: [`../06-business-model/`](../06-business-model/README.md)
