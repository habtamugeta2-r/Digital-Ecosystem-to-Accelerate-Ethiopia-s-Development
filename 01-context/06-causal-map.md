# 01.6 · The Causal Map

*Part of [01 · Context](README.md)*

This file sets out the reinforcing structure of Ethiopia's underdevelopment and identifies where
digital intervention has the highest leverage. It is the analytical core of the diagnosis and the
justification for the choice of a single top opportunity.

---

## 1. The seven loops

### Loop 1 — Productivity / poverty (a vicious cycle)

```
 LOW YIELD ──► LOW INCOME ──► CANNOT BUY INPUTS ──► LOW YIELD
     ▲                                                   │
     └──── LOW SOIL / SEED QUALITY ◄── NO SURPLUS ◄──────┘
```

**Reinforcing. Slow.** Breaking it requires simultaneous access to inputs *and* a buyer for the
incremental output. Input-only interventions (fertiliser distribution without market access) increase
production but depress local prices at harvest, so the farmer captures little.

### Loop 2 — Post-harvest loss / food insecurity

```
 GROW SURPLUS ──► POOR STORAGE/TRANSPORT ──► 15–25% LOSS ──► LESS FOOD & INCOME
      ▲                                            │
      │                                            ▼
      └───── RECOUP BY EXPANDING AREA ◄──── PRESSURE TO PRODUCE MORE
                     (soil mining)
```

**Reinforcing. Moderate speed.** Also pushes farmers to expand cultivated area rather than intensify,
which accelerates soil degradation.

### Loop 3 — Market fragmentation / price volatility

```
 NO PRICE INFORMATION ──► SELL AT HARVEST, FARM GATE ──► GLUT LOCALLY, PRICE COLLAPSE
        ▲                            │                            │
        │                            ▼                            ▼
   NO VOLUME TO JUSTIFY       TRADER CAPTURES SPREAD       LEAN-SEASON PRICE SPIKE
   INFORMATION SERVICE                                              │
        ▲                                                          │
        └──────────── LOW TRUST IN FORMAL MARKETS ◄─────────────────┘
```

**Reinforcing. Fast.** This is the loop a marketplace attacks most directly. Publishing prices
changes bargaining; aggregating supply changes the counterparty; forward contracts change the timing
of sale.

### Loop 4 — Finance exclusion

```
 NO COLLATERAL ──► NO FORMAL CREDIT ──► NO INPUTS / NO BUFFER ──► SHOCK = ASSET SALE
      ▲                                                                    │
      │                                                                    ▼
 NO TITLED ASSETS ◄──────── ASSET DEPLETION ◄───────────── DEEPENED POVERTY
      ▲                                                                    │
      │                                                                    ▼
      └──────────── NO CREDIT HISTORY ◄──── NO FORMAL BORROWING ◄───────────┘
```

**Reinforcing. Very slow to reverse.** The only fast exit is **cash-flow lending on verified
transaction data** or **value-chain guarantees**, because both bypass the collateral requirement.

### Loop 5 — Logistics / cost

```
 POOR ROADS ──► HIGH TRANSPORT COST ──► NARROW MARKET RADIUS ──► LESS COMPETITION
      ▲                                                                    │
      │                                                                    ▼
 LOW REVENUE FOR MAINTENANCE ◄── LOW TRADE VOLUME ◄── LOW FARM-GATE PRICES
      ▲                                                                    │
      └──────────── EMPTY BACKHAULS, SINGLE CORRIDOR, CHECKPOINTS ◄────────┘
```

**Reinforcing. Slow and capital-intensive.** The digital lever is **matching** (fill backhauls,
aggregate loads, schedule pickups), not road building.

### Loop 6 — State capacity / fiscal

```
 NARROW TAX BASE ──► LOW PUBLIC INVESTMENT ──► POOR SERVICES & INFRASTRUCTURE
       ▲                                                │
       │                                                ▼
 LARGE INFORMAL SECTOR ◄──────── LOW PRODUCTIVITY ◄── LOW GROWTH IN FORMAL FIRMS
       ▲                                                │
       │                                                ▼
       └──────── WEAK COLLECTION, SOE LOSSES, DEBT ◄────┘
```

**Reinforcing. Slow.** Digital contribution: formalisation through digital payments (each digital
transaction leaves a taxable trail), and cheaper subsidy delivery (India's DBT savings).

### Loop 7 — Conflict and climate shocks

```
 CONFLICT / DROUGHT ──► DISPLACEMENT & ASSET LOSS ──► LOWER PRODUCTION & DEMAND
        ▲                                                    │
        │                                                    ▼
  RESOURCE COMPETITION ◄── POVERTY & FOOD INSECURITY ◄── HIGHER PRICES
        ▲                                                    │
        └──────────── WEAKER STATE CAPACITY ◄────────────────┘
```

**Reinforcing, and exogenous to any single intervention.** The only response is resilience design
(diversification, insurance, cash transfer capacity, light assets).

---

## 2. The leverage map

Not all nodes in a system are equal. The table below ranks intervention points by
**leverage** (how many loops they touch) × **digital tractability** × **feasibility in Ethiopia's
current constraints**.

| Leverage point | Loops touched | Digital tractability | Feasibility | Net |
|---|---|---|---|---|
| **Farm-gate price discovery + matching** | 1, 3, 5 | High | High | ★★★★★ |
| **Transaction-based credit history** | 1, 4, 6 | High | Medium (needs 2 seasons of data) | ★★★★★ |
| **Post-harvest loss reduction via scheduling + storage** | 2, 3, 5 | Medium | Medium | ★★★★☆ |
| **Input aggregation and voucher digitisation** | 1, 4, 6 | High | High (aligns with ATI IVS) | ★★★★☆ |
| **Logistics matching / backhaul** | 5, 3 | Medium | Medium | ★★★☆☆ |
| **Index insurance with plot-level data** | 1, 2, 7 | Medium | Low–Medium (basis risk, reinsurance) | ★★★☆☆ |
| **Digital ID-linked subsidy targeting** | 6, 4 | High | High (Fayda already mandated) | ★★★★☆ |
| **Traceability for export premiums** | 3, 6 | High | High (EUDR, ECX reform) | ★★★★☆ |
| **Road building** | 5, 3, 6 | None | Very low (capital) | — |
| **Land titling / collateral reform** | 4 | Low | Very low (political) | — |
| **Currency / FX reform** | All | None | Out of scope | — |

**The top-right quadrant** is precisely: *price discovery, matching, transaction-based credit, input
digitisation, targeting and traceability.* Every one of them is a module of the platform proposed in
[05 · Proposed ecosystem](../05-ecosystem/README.md).

---

## 3. Why agriculture is the entry point and not, say, urban e-commerce

| Criterion | Agriculture platform | Urban e-commerce | Digital government | Fintech lending |
|---|---|---|---|---|
| Share of population affected | ~75–80% (rural, farming) | ~24% (urban) | 100% | ~49% (banked) |
| Share of GDP touched | ~32% directly, ~60%+ indirectly | small | large but indirect | small |
| Alignment with national strategy | DAR, NAFIR, PGMS, Digital Ethiopia 2030 | Digital Ethiopia 2030 (partial) | Digital Ethiopia 2030 (core) | NDPS, NFIS |
| Existing private proof points | Lersha, ATI platforms, ECX | weak (58% <US$10k revenue) | Irembo analogue but slow procurement | crowded |
| Ability of one organisation to execute | medium | high | low (state-led) | medium (regulated) |
| Political salience | very high (food security) | medium | high | high |
| Moat potential | high (data + network + relationships) | low | none (state-owned) | medium (underwriting data) |
| Risk of being displaced by state/incumbent | medium | low | total | medium |

The agriculture column dominates on population reached, GDP touched, alignment and moat. The urban
e-commerce column wins only on ease of execution — and loses on every other dimension, including
evidence (Jumia's 11 years of losses; Ethiopia's own sub-scale platforms).

---

## 4. Counter-arguments and honest responses

**"Ethiopia's problem is capital, not software."**
Partly true. Roads, power, irrigation and storage need capital. But the *allocation* of that capital
is currently information-poor: investors do not know where the surplus is, lenders do not know who is
creditworthy, buyers do not know who has quality supply, and government does not know who received
what. Digital infrastructure raises the return on the capital that already exists before it adds any
new capital. That is the correct, modest claim.

**"Smallholders are too poor and too dispersed to be a market."**
They are dispersed, but they are not small in aggregate: 12–15 million households producing 30–33
Mt of cereals plus livestock, coffee, pulses and horticulture. The correct unit of analysis is the
**cooperative or woreda cluster**, not the individual farmer. Aggregation is the business model.

**"The government will capture it."**
Possible. Mitigation: be the operational partner in a national programme rather than a rival to it,
keep the data asset distributed (consent-based, farmer-owned), and stay asset-light enough to
survive a change in policy.

**"This has been tried and failed."**
Parts have. The failures share identifiable causes: smartphone-only design, no physical agent layer,
no payment rail, no buyer liquidity, and no second act beyond the app. Every one of those conditions
has changed since 2020 — Fayda, interoperable mobile money, EthSwitch, and the DAR did not exist in
usable form before.

---

## 5. The single-sentence conclusion

**Ethiopia's development trap is held together by information and coordination failures at the farm
gate; the cheapest way to loosen it is to digitise the farm-to-market transaction and let identity,
payments and data do the rest.**
