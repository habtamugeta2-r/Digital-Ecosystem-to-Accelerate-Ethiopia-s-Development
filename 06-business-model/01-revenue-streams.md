# 06.1 · Revenue Streams

*Part of [06 · Business model](README.md)*

Six lines, each with its mechanism, pricing basis, timing and honest sizing.

---

## Stream 1 — Marketplace commission

| Attribute | Detail |
|---|---|
| **Mechanism** | Percentage of gross merchandise value on a matched, settled trade |
| **Rate** | 1–3% blended (bulk cereals 1–1.5%; specialty/horticulture 2–3%) |
| **Who pays** | Buyer (folded into the price) or split; disclosed to both |
| **Starts** | Phase 1 |
| **Unit** | Per transaction (ETB 750,000 for a 30-tonne grain trade at ETB 25,000/t) |

**Pricing logic:**
- The incumbent intermediary's spread is commonly 10–30%. Undercutting at 1–3% leaves ample room to
  be attractive while funding operations.
- Anything above 3% invites side-selling.
- For high-value, quality-differentiated commodities (specialty coffee), a higher rate is defensible
  because the platform adds traceability and market access the farmer cannot obtain alone.

**Sensitivity:**

| GMV (ETB bn) | At 1.0% | At 1.5% | At 2.5% |
|---|---|---|---|
| 2 | ETB 20 m | ETB 30 m | ETB 50 m |
| 8 | ETB 80 m | ETB 120 m | ETB 200 m |
| 20 | ETB 200 m | ETB 300 m | ETB 500 m |
| 40 | ETB 400 m | ETB 600 m | ETB 1,000 m |
| 100 | ETB 1,000 m | ETB 1,500 m | ETB 2,500 m |

**Risk:** commission compression if a state platform offers free matching. Mitigation: differentiate on
settlement certainty, finance and traceability — not on matching alone.

---

## Stream 2 — Payment and escrow share

| Attribute | Detail |
|---|---|
| **Mechanism** | Share of the interchange/settlement fee with the wallet or bank partner |
| **Rate** | 0.3–0.8% of settled value |
| **Who pays** | Merchant fee borne by the transaction |
| **Starts** | Phase 1 |

**How it arises:** the platform is a merchant/aggregator for the wallet providers. It generates
payment volume; it negotiates a revenue share. As volumes grow, the rate improves.

**Note:** this is a small line per transaction but it scales directly with GMV and requires no
additional product.

---

## Stream 3 — Embedded finance

| Attribute | Detail |
|---|---|
| **Mechanism** | Origination fee + servicing fee on loans; commission on insurance |
| **Rate** | 1–3% of principal (origination) + 0.5–1.5% p.a. servicing; 10–20% of insurance premium |
| **Who pays** | Lender/insurer (from the loan margin or premium) |
| **Starts** | Phase 2 (needs 2 seasons of data) |

**Economics example (Year 3):**

| Item | Value |
|---|---|
| Loans originated | ETB 400 m |
| Origination fee at 2% | ETB 8 m |
| Servicing at 1% p.a. on average book | ETB 4 m |
| Insurance premium placed | ETB 120 m |
| Commission at 15% | ETB 18 m |
| **Total finance revenue** | **ETB 30 m** |

**At Year 5 (ETB 3 bn origination):** origination ETB 60 m + servicing ETB 30 m + insurance ETB 45 m =
**ETB 135 m**.

**This is the highest-margin line** — it requires no inventory, no logistics and no customer
acquisition — but it is entirely dependent on the ledger data being trustworthy. That is why it starts
in Phase 2, not Phase 1.

**Risk:** lender withdrawal, regulatory reclassification, default waves from covariate shocks.
Mitigation: multiple lenders, first-loss cover, geographic diversification.

---

## Stream 4 — Input commerce

| Attribute | Detail |
|---|---|
| **Mechanism** | Margin on seed, fertiliser, agrochemicals, mechanisation services, or listing fee for accredited suppliers |
| **Rate** | 3–8% margin |
| **Who pays** | The input supplier (or the farmer, embedded in the price) |
| **Starts** | Phase 2 |

**Why this line is attractive:** input demand is predictable, financeable and tied directly to the
platform's credit product. Selling a farmer inputs on credit that is repaid at harvest is the classic,
proven agricultural platform model (and Lersha's core business).

**Why it is risky:** input supply chains suffer FX shortages, import delays and quality fraud. The
platform should **only list accredited suppliers** and never take inventory risk in Phase 2.

**Sizing (Year 5):**

| Item | Value |
|---|---|
| Farmers buying inputs through platform | 300,000 |
| Average input spend | ETB 13,000 |
| Input GMV | ETB 3.9 bn |
| Margin at 4% | **ETB 156 m** |

---

## Stream 5 — Data and analytics

| Attribute | Detail |
|---|---|
| **Mechanism** | Subscription reports, custom analysis, traceability certification, ESG/sourcing verification |
| **Rate** | ETB 150k–2 m per client per year |
| **Who pays** | Processors, exporters, traders, insurers, development partners, government |
| **Starts** | Phase 2 |

**Products:**
- Weekly price and volume intelligence by commodity and region
- Crop area and yield estimates (early, monthly)
- Sourcing verification and traceability certificates (EUDR compliance)
- Post-harvest loss benchmarking
- Aggregate smallholder credit performance (for lenders and reinsurers)

**Sizing (Year 5):** 40 clients at ETB 150k average = ETB 6 m. Modest, but high margin and strategically
important because it makes the platform the reference dataset for Ethiopian agriculture.

**Caution:** never sell individual farmer data. Aggregate only (minimum 50 subjects per cell).

---

## Stream 6 — Government and programme delivery

| Attribute | Detail |
|---|---|
| **Mechanism** | Per-beneficiary delivery fee, contract fee, or M&E fee |
| **Rate** | ETB 50–150 per beneficiary; fixed contract for systems |
| **Who pays** | MoA, ATI, regional bureaus, WFP, NGOs, bilateral donors |
| **Starts** | Phase 1 |

**Why start here:** this revenue arrives **before** marketplace liquidity exists. It funds the
product, builds the government relationship and provides farmer acquisition at scale.

**Sizing (Year 3–5):**

| Programme | Beneficiaries | Fee | Revenue |
|---|---|---|---|
| Input voucher delivery | 200,000 | ETB 100 | ETB 20 m |
| Cash transfer delivery | 250,000 | ETB 60 | ETB 15 m |
| Extension distribution | 500,000 | ETB 20 | ETB 10 m |
| M&E / dashboards | contract | — | ETB 15 m |
| **Total** | | | **~ETB 60 m** |

**Risk:** 90–365 day receivables; political reallocation; scope creep. Mitigation: milestone billing,
working capital facility, at least three clients.

---

## Revenue mix over time (Base case ⚪)

| Line | Y1 | Y2 | Y3 | Y4 | Y5 |
|---|---|---|---|---|---|
| Marketplace | 1 | 12 | 60 | 180 | 600 |
| Payments | 0.2 | 3 | 12 | 36 | 120 |
| Finance | 0 | 0 | 30 | 85 | 135 |
| Inputs | 0 | 4 | 25 | 70 | 156 |
| Data | 0 | 0.5 | 3 | 6 | 12 |
| Programmes | 4 | 20 | 30 | 45 | 60 |
| **Total (ETB m)** | **5.2** | **39.5** | **160** | **422** | **1,083** |

*Slightly higher than the summary table because it includes insurance commission separately.*

**Observation:** programmes fund years 1–2; marketplace and finance drive years 3–5. Any strategy that
skips the programme line will run out of money before the marketplace matures.

---

## Pricing principles

| Principle | Application |
|---|---|
| Charge at the moment of value realisation, not admission | Fee on settlement, not on registration |
| Keep the farmer's visible fee single-digit percentage | ≤3% total, always disclosed |
| Never charge for information | Prices, weather, advisory are free forever |
| Price in birr, review monthly | Inflation 12–16% erodes fixed fees |
| Let the stronger side pay | Buyers and lenders can absorb fees; farmers cannot |
| Offer a free tier that is genuinely useful | Listing and price alerts at no cost |
| Publish the rate card | Transparency is a trust mechanism and a competitive weapon |

---

## Anti-revenue decisions (deliberate)

| Not a revenue line | Why |
|---|---|
| Farmer subscriptions | Would suppress the adoption the platform needs |
| Advisory content sales | Public good; ATI provides it free |
| Advertising | Too small a market; damages trust |
| Selling individual farmer data | Illegal under 1321/2024 and reputationally fatal |
| Card acceptance fees | Volumes negligible for a decade |
| Wallet issuance fees | Do not issue a wallet |
| Inventory trading margin (by default) | Capital-intensive; only as a Phase 1 tactic with a hard stop |
