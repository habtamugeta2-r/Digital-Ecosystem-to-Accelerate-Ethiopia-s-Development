# 01.3 · Markets, Logistics and Finance

*Part of [01 · Context](README.md)*

---

## 1. Market fragmentation

Ethiopia's domestic agricultural markets are fragmented in three dimensions at once: **geographically**
(poor roads, many small markets), **informationally** (prices not known across markets), and
**structurally** (long intermediary chains, weak grading, limited contracting).

**Evidence of fragmentation:**

| Symptom | Evidence |
|---|---|
| Price dispersion across markets | Analysts describe annual price volatility of **20–40%** for key cereals; lean-season vs harvest-season spreads are large and predictable |
| Limited price information | Only a minority of farmers access auction or exchange prices; a large share sell to village traders at the farm gate |
| Weak grading | Quality is inconsistently assessed; the ECX introduced grading but coverage is partial |
| Long chains | Coffee can pass through 4–5 hands between farmer and exporter |
| Low contract enforcement | Forward contracts are rare; the ECX briefly introduced forward trading and halted it |
| Thin competition in buying | In many woredas a small number of traders dominate local purchase |

**The ECX experience.** Established 2008 to formalise trade, the exchange built ~60 warehouses, a
grading system, electronic warehouse receipts and (in January 2025) online trading. It has processed
billions of birr in digital transactions, but its historical model — anonymous pooled lots by grade
rather than by origin — **undermined traceability and therefore the specialty premium**, which is
why the 2017 reforms and Directive 1106/2025 progressively opened direct and vertical-integration
channels. Trading volumes have at times declined by up to ~51% year-on-year, and the exchange's
reach to the smallholder at the farm gate remains limited.

**Lesson for a new platform:** the exchange solved *price discovery for bulk commodity grades*. It
did not solve *origin traceability, quality differentiation, farm-gate aggregation, or finance*.
Those are the open opportunities.

---

## 2. Post-harvest losses

| Commodity | Loss estimate | Confidence |
|---|---|---|
| Cereals (aggregate) | **15–25%** (some estimates to 30%) | 🟠 |
| Maize | 18–25% | 🟡 |
| Wheat / teff | 15–20% (teff 16–30%) | 🟡 |
| Sorghum | 22–28% | 🟡 |
| Horticulture | **30–50%** | 🟠 |
| Milk | ~30% | 🟠 |
| Red meat | ~40% | 🟠 |

**Causes:** harvest damage and shattering, threshing losses, inadequate drying, traditional
granaries, pest and mould, poor transport, market delays, and lack of cold chain.

**Why this is the single most attractive quantitative target in Ethiopian agriculture:** reducing
cereal losses from 20% to 10% is equivalent to adding 3–3.3 million tonnes of grain — roughly a
10% increase in national supply — **without a single additional hectare or a single additional
kilogram of fertiliser.** The government adopted a National Post-Harvest Management Strategy
(2024–2030) precisely for this reason.

Digital contribution to loss reduction is indirect but real: better matching (selling faster),
scheduled logistics (less waiting), quality grading (price signals for quality), warehouse receipt
systems (storage finance), and demand aggregation (fewer rejected loads).

---

## 3. Logistics and transport

| Indicator | Ethiopia | Comparator | Confidence |
|---|---|---|---|
| Road network | 171,176 km (2024) | — | 🟡 |
| Paved share | **~13%** | Sub-Saharan average ~25%; world ~60% | 🟡 |
| Road density | 148 km / 1,000 km² | Africa ~204; world ~394 | 🟡 |
| Road density per 1,000 people | 1.4–1.6 km | SSA ~3.3 | 🟡 |
| Roads in good condition | ~26% | SSA ~70% (IRF-based comparison) | 🟠 |
| Share of trade via Djibouti | **90–95%** | single-corridor dependence | 🟡 |
| Cost, Djibouti→Addis per FEU | US$3,555 by truck; US$2,462 by rail | Berbera US$3,760 | 🟡 |
| Estimated annual port/transit fees to Djibouti | ~US$1.5 bn | — | 🟠 |
| Urban congestion cost | ~3% of GDP | Addis Ababa | 🟠 |
| Addis Ababa paved road share | 26% | Nairobi 45%, Kampala 38% | 🟡 |

**The economics of an export-light, import-heavy corridor.** Because exports are a small fraction of
trade volume, trucks run back empty, and import cargo effectively pays for the round trip. This makes
domestic backhaul capacity cheap in principle but poorly utilised in practice — a classic
**matching problem** that a freight platform can address (find a load for the returning truck).

**The Berbera alternative.** The Berbera corridor (Somaliland) reached Addis at ~US$3,760/FEU by
truck versus US$3,555 from Djibouti by truck and US$2,462 by rail, but is cheaper for eastern
destinations (Kebri Dehar: US$2,585 vs US$2,806). Analysts conclude the binding constraint is the
missing transit agreement, not the road. **Corridor diversification is a national resilience issue**
and a reason to design logistics modules that are corridor-agnostic.

---

## 4. The agricultural finance gap

This is the constraint most amenable to digital intervention, and the numbers are stark.

| Indicator | Value | Year | Confidence |
|---|---|---|---|
| Estimated annual agri-credit demand | **ETB 2.58 trillion** | 2023/24 | 🟡 |
| Share of demand met by formal institutions | **~2%** | 2024–26 | 🟡 |
| Alternative lower estimate of unmet demand | ETB 52 bn (older, narrower definition) | earlier | 🟠 |
| Commercial bank lending to agriculture | 8% of total | 2023/24 | 🟡 |
| MFI lending to agriculture | 18% of portfolio | 2023/24 | 🟡 |
| Smallholders who accessed formal credit in past 3 years | 15–20% | 2024 | 🟠 |
| Agricultural credit disbursed (2022) | ETB 35 bn, of which ~two-thirds unused | 2022 | 🟡 |
| Development Bank of Ethiopia agricultural allocation (2022) | ~ETB 14 bn, only 37% effectively used | 2022 | 🟡 |
| Seasonal working capital need, cereals only (IFC estimate) | ~US$3 bn/yr | earlier | 🟠 |
| NAFIR 2030 target | ETB 881 bn annual agri-credit | 2030 | 🟡 |

### 4.1 Why the gap persists

1. **No usable collateral.** Land is state-owned and cannot be mortgaged. Smallholders have few
   titled, movable assets. Livestock is hard to pledge and easy to lose.
2. **No credit history.** Most smallholders have never borrowed formally, so no bureau record exists.
   Even where a record exists, it is thin.
3. **High transaction cost per loan.** A loan of ETB 10,000 requires the same appraisal, disbursement
   and monitoring effort as a loan of ETB 10 million. Branch presence in rural areas is sparse.
4. **Covariate risk.** Drought, flood and conflict hit whole portfolios at once; lenders cannot
   diversify within a woreda.
5. **Weak risk-sharing instruments.** Credit guarantee funds, index insurance and warehouse receipts
   are small, donor-funded pilots rather than national infrastructure.
6. **Demand-side capacity.** The 2022 evidence that two-thirds of disbursed agricultural credit went
   unused shows that borrowers often lack the business plans, financial literacy or compliance
   capacity to absorb credit — a training and intermediation need, not just a funding one.

### 4.2 What is being built

The **National Agri-Finance Implementation Roadmap (NAFIR) 2025–2030**, jointly led by the National
Bank of Ethiopia and the Ministry of Agriculture, targets ETB 881 bn in annual agri-credit by 2030
across three pillars: a National Agri-Finance Accelerator (NAFA) with dedicated credit lines,
lower refinancing rates and first-loss risk sharing; institutional reform including a wholesale
**Agricultural Finance Institute / agricultural bank** modelled on India's NABARD; and digital
enablement. First pilots are being prepared in selected woredas.

### 4.3 The digital lever

The gap is not only a shortage of money — it is a shortage of **verifiable information and cheap
distribution**. A platform that records a farmer's sales, repayment, input purchases and delivery
performance for two seasons creates exactly the asset a lender needs: a cash-flow history with
third-party corroboration. This is the highest-value output of an agricultural marketplace, and it
is why the marketplace and the finance product must be built by the same organisation.

---

## 5. Digital finance: where Ethiopia actually stands

| Indicator | Value | Year | Confidence |
|---|---|---|---|
| Adults with any financial account | 49% | 2024 | 🟢 |
| Adults with a mobile money account | 9.5% (Findex) / 19.4% (alt. series) | 2024–25 | 🟠 |
| Adults making/receiving digital payments | 21% | 2024 | 🟢 |
| Adults receiving private-sector wages into an account | 4% | 2024 | 🟢 |
| Adults receiving digital government transfers | 3% | 2024 | 🟢 |
| Adults paying bills online | 7% | 2024 | 🟢 |
| Adults buying online with digital payment | **1%** | 2024 | 🟢 |
| Digital payments value | 82% of GDP | 2024 | 🟡 |
| Digital payments value target | 750% of GDP | 2030 | 🟡 |
| Digital transactions per adult | 54 (2025) → 275 (2030 target) | — | 🟡 |
| 30-day active account rate | 16% → 60% target | 2025 → 2030 | 🟡 |
| Merchant payment participation | 24% → 60% target | 2025 → 2030 | 🟡 |
| Digital credit/savings/insurance share of digital value | <1% → 3% target | 2025 → 2030 | 🟡 |

> **The 1% figure is the most important number in this table.** Virtually nobody in Ethiopia buys
> anything online with a digital payment. Any e-commerce model that assumes digital checkout as the
> default is built on air. Cash-on-delivery, agent-mediated payment and escrow-with-cash-in must be
> first-class options for years.

### The paradox: 200 million accounts, 49% of adults

Between June 2022 and March 2025, digital financial accounts in Ethiopia grew from 94.7 million to
222.1 million — yet Findex account ownership rose only from 46% to 49%. The explanation is that
**most new accounts were opened by people who already had one**, typically for a specific use case
(fuel payment, salary, a subsidy), and then lay dormant. The strategy's 16% → 60% active-use target
is a direct admission of this.

**Design consequence:** the product must not measure success by registrations. It must measure
**30-day active transactors**, which is the same metric the central bank now uses.

---

## 6. The composite market failure, in one diagram

```
   NO COLLATERAL ─────────────► NO CREDIT ─────────────► NO INPUTS
        ▲                          ▲                        │
        │                          │                        ▼
   LAND LAW                 NO CREDIT HISTORY          LOW YIELD
        │                          ▲                        │
        │                          │                        ▼
   SMALL FARM SIZE ◄────── NO SURPLUS TO SELL ◄──── HIGH POST-HARVEST LOSS
        │                          ▲                        ▲
        │                          │                        │
        └──── WEAK BARGAINING ─────┴──── FRAGMENTED MARKETS ┘
                     POSITION                    + POOR LOGISTICS
```

Every arrow in this diagram is either an **information problem** (history, prices, quality, identity)
or a **coordination problem** (matching, scheduling, aggregation). That is the precise definition of
where digital infrastructure earns its return.

---

## Key takeaways

1. Fragmentation is measurable: 20–40% seasonal price swings, long chains, thin grading.
2. Post-harvest loss (15–25% cereals; 30–50% horticulture) is the largest single quantifiable
   inefficiency — equal to ~10% of national grain supply.
3. Logistics is structurally expensive: 13% paved roads, 90–95% single-corridor dependence,
   empty backhauls.
4. Agricultural credit meets ~2% of demand, and the binding constraint is *verifiable information*,
   not only capital — the exact asset a transaction platform produces.
5. Digital finance has scale (200m+ accounts) but not usage (49% of adults; 1% online purchase).
   Design for activity, not registration.
