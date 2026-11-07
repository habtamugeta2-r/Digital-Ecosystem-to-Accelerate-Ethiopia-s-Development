# 05.6 · Feedback Loops: Why the Ecosystem Compounds

*Part of [05 · Proposed ecosystem](README.md)*

A platform's value comes from loops, not from features. This file specifies the five loops the
ecosystem depends on, the conditions under which each accelerates or stalls, and the metrics that
show whether it is working.

---

## Loop 1 — The data-to-credit loop (the primary engine)

```
        ┌──────────────────────────────────────────────┐
        │                                              │
        ▼                                              │
   MORE TRANSACTIONS ──► BETTER DATA ──► BETTER       │
        ▲                                  UNDERWRITING
        │                                       │      │
        │                                       ▼      │
   MORE CREDIT ◄── HIGHER YIELD ◄── INPUTS BOUGHT ◄────┘
```

| Stage | Condition for acceleration | Condition for stall |
|---|---|---|
| Transaction → data | Complete, verified, provenance-tagged records | Gaps, farmer-declared data, side-selling |
| Data → underwriting | 2+ seasons, low default, lender trust | Thin file, covariate shock, high default |
| Underwriting → credit | Lender partner with risk appetite; first-loss cover | Lender caution; NBE classification; capital constraints |
| Credit → inputs | Inputs available at the right time and place | Supply chain failure; FX shortage on fertiliser |
| Inputs → yield | Correct input, correct timing, correct advice | Late delivery, wrong product, weather |
| Yield → transaction | Farmer sells through the platform | Side-selling; better trader offer |

**Cycle time: one season (~6 months).** This is slow. It means the platform needs ~2.5 years before
the credit loop is fully powered. Plan for it; do not promise impact in year one.

*Note: the source brief claimed 10–20% yield boosts as evidence of effect. The more defensible
statement is 14–25% for site-specific fertilizer/advisory in wheat trials (CGIAR/AICCRA) — but these
gain apply only where inputs and advice are delivered together. Apply a large discount for delivery
failure.*

---

## Loop 2 — The liquidity loop (marketplace network effect)

```
   MORE FARMERS ──► MORE SUPPLY ──► MORE BUYERS ──► BETTER PRICES
        ▲                                              │
        │                                              ▼
        └────────── FASTER MATCHING ◄──────── MORE LISTINGS
```

| Condition for acceleration | Condition for stall |
|---|---|
| Anchor buyers committed before launch | Buyers wait for supply, farmers wait for buyers |
| Narrow geography (dense supply) | Too dispersed to aggregate |
| Standard grades | Every lot is a bespoke negotiation |
| Fast settlement | Payment delays kill repeat listings |
| Farmer sees a better price | Side-selling after matching |

**The classic cold-start problem.** Solution: **subsidise the demand side first.** Pay or guarantee
buyers (or be the buyer yourself) for the first season to create certainty of sale; then supply
follows.

**Alternative approach the platform should consider for Phase 1:** act as **principal** (buy and resell)
for a small volume — which requires a trading margin, working capital and a commodity licence. It is
messier but it removes the matching risk and proves the value proposition. Many agricultural platforms
in Africa end up doing this.

---

## Loop 3 — The trust loop

```
   FIRST TRANSACTION ──► GOOD OUTCOME ──► WORD OF MOUTH ──► MORE FARMERS
        ▲                                                       │
        │                                                       ▼
   LOWER ACQUISITION COST ◄── HIGHER VOLUME ◄── LOWER RISK ◄────┘
```

| Accelerant | Brake |
|---|---|
| Guarantee honoured when things go wrong | One unresolved dispute destroys local trust |
| Cooperative endorsement | Platform seen as aligned with an unpopular actor |
| Visible price boards | Perceived as extracting a hidden spread |
| Agent continuity | Agent turnover or fraud |
| On-time payment | One bounced or late payment |

**Trust is asymmetric:** it is built at the speed of one transaction and lost at the speed of one
failure. This is why the guarantee fund and the dispute process are not operational niceties but core
product.

---

## Loop 4 — The agent economics loop

```
   MORE SERVICES PER AGENT ──► HIGHER AGENT INCOME ──► BETTER AGENTS
        ▲                                                   │
        │                                                   ▼
   MORE FARMERS SERVED ◄── BETTER SERVICE ◄── LOWER CHURN
```

| Accelerant | Brake |
|---|---|
| Bundled commissions (float + listing + logistics + inputs) | Single-stream income (float only) |
| Input sales margin | Capital constraints prevent stocking |
| Float credit after 3 months | No credit history for the agent either |
| Device and data support | Agent bears all equipment cost |

**The failure mode:** a platform launches with one service, agents cannot make a living, they churn,
and the platform loses its rural distribution. This is why the module sequence matters — advice and
price information should launch early, at zero cost, simply to give agents something to talk about
and to build the habit before revenue arrives.

---

## Loop 5 — The policy loop

```
   PLATFORM DELIVERS PROGRAMMES ──► STATE SEES RESULTS ──► MORE PROGRAMMES
        ▲                                                        │
        │                                                        ▼
   BETTER POLICY ACCESS ◄── DATA AND EVIDENCE ◄── INSTITUTIONAL TRUST
```

| Accelerant | Brake |
|---|---|
| Verified delivery outcomes (leakage reduction, time saved) | One audit failure |
| Published data that the state uses | Political turnover |
| Programme revenue that funds product development | Dependence on a single ministry |
| Alignment with DAR/NAFIR/NDPS | Being seen as a parallel strategy |

**This loop is the most valuable and the most fragile**, because it depends on individuals in
ministries. Diversify across at least three ministries/donors within two years.

---

## The reinforcing system, drawn

```
                          ┌─────────────────────┐
                          │   MORE FARMERS      │
                          └──────────┬──────────┘
                                     │
              ┌──────────────────────┼──────────────────────┐
              ▼                      ▼                      ▼
     ┌────────────────┐    ┌────────────────┐    ┌────────────────┐
     │ MORE SUPPLY    │    │ MORE DATA      │    │ MORE AGENT     │
     │ (Loop 2)       │    │ (Loop 1)       │    │ INCOME (Loop 4)│
     └────────┬───────┘    └────────┬───────┘    └────────┬───────┘
              │                     │                      │
              ▼                     ▼                      ▼
     ┌────────────────┐    ┌────────────────┐    ┌────────────────┐
     │ MORE BUYERS    │    │ MORE CREDIT    │    │ BETTER AGENTS  │
     └────────┬───────┘    └────────┬───────┘    └────────┬───────┘
              │                     │                      │
              └──────────────────────┼──────────────────────┘
                                     ▼
                          ┌─────────────────────┐
                          │  BETTER OUTCOMES    │
                          │  (price, yield,     │
                          │   reliability)      │
                          └──────────┬──────────┘
                                     │
                                     ▼
                          ┌─────────────────────┐
                          │  TRUST + WORD OF    │
                          │  MOUTH (Loop 3)     │
                          └──────────┬──────────┘
                                     │
                                     ▼
                          ┌─────────────────────┐
                          │  POLICY ACCESS      │
                          │  (Loop 5)           │
                          └──────────┬──────────┘
                                     │
                                     └──────► back to MORE FARMERS
```

---

## Where the system can stall — and the early-warning indicators

| Stall point | Early warning | Intervention |
|---|---|---|
| Buyers don't commit | <3 anchor buyers by month 6 | Pay for demand; consider principal trading |
| Farmers don't repeat | <40% second-season transaction rate | Diagnose: price, payment speed, or trust |
| Agents churn | >30% annual agent attrition | Increase bundled income; reduce device cost |
| Credit doesn't flow | No lender partner by month 12 | First-loss facility; start with MFI not bank |
| Data quality fails | >20% of records farmer-declared only | Enforce verification at aggregation points |
| Trust breaks | Any unresolved dispute >14 days | Dispute fund; adjudication SLA; publish outcomes |
| Policy loop closes | Single-ministry dependency >50% of revenue | Diversify clients; donor contracts |

---

## The compounding claim, quantified (illustrative ⚪)

| Year | Farmers active | GMV (ETB bn) | Revenue (ETB m) | Loans (ETB m) | Moat strength |
|---|---|---|---|---|---|
| 1 | 8,000 | 0.3 | 5 | 0 | None |
| 2 | 45,000 | 2.0 | 40 | 60 | Thin data |
| 3 | 180,000 | 8.0 | 160 | 400 | 2 seasons; lender trust |
| 4 | 400,000 | 20.0 | 420 | 1,200 | Multi-lender; scoring works |
| 5 | 750,000 | 40.0 | 850 | 3,000 | Hard to displace |

The **inflection is year 3** — the point at which the data-to-credit loop closes. Before that, the
business is a subsidised operations company. After it, it is a financial infrastructure company. Plan
the capital accordingly: **the platform needs enough runway to survive to year 3.**

---

## The single most important operational discipline

**Measure the loop, not the output.**

| Bad metric | Good metric |
|---|---|
| Registered farmers | Second-season repeat transaction rate |
| Total GMV | Contribution margin per transaction |
| Loans disbursed | PAR-30 and repeat-borrower rate |
| Agents onboarded | Agent monthly income and 12-month retention |
| App downloads | USSD sessions completed |
| Beneficiaries reached | Verified delivery rate at the cooperative |

Every one of the good metrics measures whether a loop is turning. The bad metrics measure activity.
