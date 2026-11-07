# 05.3 · Application Modules

*Part of [05 · Proposed ecosystem](README.md)*

Six modules, each of which can be built, launched, paused or replaced independently. Each is specified
with its users, its flows, its dependencies, its metrics and its failure modes.

---

## Module 1 — Marketplace and Trade

**Users:** farmers, cooperatives, buyers (traders, millers, processors, exporters), agents

### Flows

| Flow | Farmer side | Buyer side |
|---|---|---|
| **List** | USSD or agent: commodity, grade, quantity, location, availability date, asking price | — |
| **Discover** | — | Search by commodity, grade, region, volume, delivery window |
| **Bid** | Receive bids by SMS/IVR; accept or counter | Place bid or post a buy request |
| **Contract** | Confirm terms by PIN + spoken IVR confirmation | Confirm terms; fund escrow |
| **Deliver** | Deliver to collection point or farm-gate pickup | Confirm receipt |
| **Settle** | Receive payment to wallet or cash at agent | Release escrow |
| **Rate** | Rate buyer | Rate farmer/delivery |

### Market mechanisms by commodity

| Commodity | Mechanism | Why |
|---|---|---|
| Maize, wheat, sorghum (bulk) | Reverse auction / bidding | Standard grades, high volume |
| Teff | Fixed-price listing with negotiation | Quality variation by region and colour |
| Coffee (cherry) | Station-based pricing with quality premium | Wet mill catchment areas |
| Coffee (specialty) | Forward contract + traceability premium | Export buyer requirements |
| Pulses/oilseeds | Fixed-price listing | Export-driven, gradeable |
| Horticulture | Same-day matching | Perishability |
| Livestock | Weight-based auction with veterinary certificate | Health and weight verification |

### Trust mechanics
Verified seller badges · delivery performance score · escrow-only above threshold · published bid
dispersion · first-transaction guarantee · dispute resolution with public statistics

### Metrics
Listings per week · bid-to-listing ratio · time-to-match · fill rate · repeat transaction rate ·
price realisation vs. local baseline · dispute rate · side-selling rate

### Failure modes
Thin liquidity on one side · buyer collusion · side-selling after matching · quality disputes ·
cooperative capture by local elites

---

## Module 2 — Advisory and Data

**Users:** farmers, development agents, cooperatives

### Content types

| Content | Channel | Frequency | Source |
|---|---|---|---|
| Daily market prices | SMS, IVR, board | Daily | ATI 6077 + platform observations |
| Weather forecast | SMS, IVR | 2×/week | EthioMet + satellite |
| Planting-window alert | SMS, IVR | Seasonal | Agro-met modelling |
| Pest/disease alert | SMS, IVR | Event-driven | MoA, EIAR, AI Institute models |
| Agronomy tips by crop/stage | IVR, agent | Weekly | ATI/EIAR content |
| Input usage guidance | IVR, agent | At purchase | Site-specific advisory (HaFAS) |
| Post-harvest handling | IVR, agent | At harvest | MoA post-harvest strategy |
| Contract/price explanation | Agent | At transaction | Platform |

### The design principle
**Free to the farmer, always.** Advisory is the acquisition channel and the data-collection mechanism,
not a revenue line. Monetising advice would suppress the very adoption the platform needs.

### The differentiator
Generic advice is a public good. **Plot-specific advice attached to a transaction is proprietary.**
"Your plot in Arsi, planted 12 June, with DAP at 100 kg/ha, should top-dress now because rainfall is
forecast for 8–11 July, and the Adama price is ETB 2,850/q" is worth more than any generic tip.

### Metrics
Registered advisory users · weekly active listeners · action rate (did the farmer act?) · yield delta
in pilot cohort · cost per advisory session

### Failure modes
Content irrelevance · language mismatch · alert fatigue · wrong advice damaging trust (catastrophic —
validate everything with EIAR/ATI)

---

## Module 3 — Logistics Coordination

**Users:** cooperatives, transporters, buyers, drivers

### Flows

| Flow | Detail |
|---|---|
| **Request** | Cooperative or buyer requests a movement: origin, destination, tonnage, date, cargo type |
| **Match** | Platform assigns a contracted transporter; or broadcasts to the driver pool |
| **Confirm** | Driver accepts; farmer/shipper receives driver name and plate by SMS |
| **Track** | GPS ping (where available) + checkpoint confirmations |
| **Load** | Weighbridge ticket + photo at origin |
| **Deliver** | Photo + geotag + receiver OTP at destination |
| **Pay** | Freight paid from escrow or by shipper; driver receives wallet payment |
| **Rate** | Shipper rates driver; driver rates shipper (waiting time) |

### The three cost levers
1. **Backhaul matching** — the import corridor runs empty on the return leg.
2. **Consolidation** — combine small loads at collection points.
3. **Turnaround** — scheduled slots reduce waiting and demurrage.

### Build sequence
Dispatch desk (phone + WhatsApp) → load board → driver app → telematics integration → cold chain

### Metrics
Cost per tonne-km · empty-km share · on-time delivery · average waiting time · damage rate ·
driver utilisation

### Failure modes
Driver smartphone/literacy limits · no-shows · cargo theft · weight disputes · checkpoint delays

---

## Module 4 — Embedded Finance

**Users:** farmers, agents, cooperatives, lenders, insurers

### Products and partners

| Product | Underwriting basis | Legal structure |
|---|---|---|
| Input credit | 2 seasons of platform sales + cooperative guarantee | Lender of record: bank/MFI; platform as LSP |
| Harvest working capital | Forward contract assigned to lender | Bank; escrow assignment |
| Agent float credit | Agent transaction history | MFI or wallet partner |
| Index insurance | Plot polygon, planting date, weather | Licensed insurer; platform as distribution |
| Mechanisation PAYGo | Service bookings | Equipment supplier + lender |
| Savings | Wallet balance + seasonality | Bank or wallet provider |

### The credit lifecycle on-platform

```
1. Farmer registers, transacts for one season
2. Platform computes an eligibility estimate (transparent factors)
3. Farmer consents to share specified fields with a specified lender
4. Lender receives a query-based, field-limited view
5. Lender decides; platform is notified of the decision and terms
6. On approval, input cost is disbursed directly to the accredited supplier
7. Repayment is deducted from the next sale at settlement (automatic)
8. Repayment event updates the farmer's record (positive or negative)
9. Eligibility improves; the loop tightens
```

### Non-negotiables
- No lending from the platform's own balance sheet in Phases 1–2.
- No credit decision without a stated explanation and a human review path.
- No data shared without per-lender, per-purpose consent.
- No punitive collection practices; default handled through future market access, not harassment.

### Metrics
Loans originated · approval rate · repayment rate · PAR-30/90 · time-to-decision · cost per
origination · insurance penetration · claim payout time

### Failure modes
Covariate shocks in the pilot region · lender partner risk appetite · regulatory reclassification ·
over-indebtedness of early adopters · basis risk in insurance

---

## Module 5 — Government and Programmes

**Users:** MoA, ATI, regional bureaus, donors, NGOs, cooperatives

### Services

| Service | Client | Mechanism |
|---|---|---|
| Input voucher delivery | MoA / ATI / donors | Fayda-verified eligibility → digital voucher → accredited dealer redemption → settlement |
| Cash transfer delivery | Government / WFP / NGOs | Bulk disbursement to wallets/agents with de-duplication and reporting |
| Extension content distribution | MoA / ATI | SMS/IVR campaigns with reach reporting |
| Programme M&E | Donors | Dashboards, geo-tagged verification, independent data |
| Market intelligence | MoA, ECTA, NBE | Weekly price and volume reports |
| e-Permits for agri trade | Regional bureaus | Digital application and payment |
| Emergency response | Humanitarian agencies | Rapid beneficiary registration and cash delivery in 48 hours |

### Why this module matters early
It generates revenue **before** marketplace liquidity exists, it builds government relationships, it
provides farmer acquisition at scale, and it aligns the platform with national priorities.

### Metrics
Beneficiaries reached · leakage rate (audited) · delivery time · cost per beneficiary vs. in-kind ·
redemption rate · audit findings

### Failure modes
Payment delays to the platform · political reallocation · scope creep · data ownership disputes ·
being associated with a diversion incident

---

## Module 6 — Developer and Partner Platform

**Users:** startups, banks, insurers, NGOs, researchers, government agencies

### Offering

| Asset | Access |
|---|---|
| Public price API | Open, rate-limited |
| Listing and order API | Registered developers, sandbox first |
| Credit eligibility API | Licensed lenders only, consent-gated |
| Verification API | Partners with a legitimate use case |
| Webhooks | All registered partners |
| Sandbox | Synthetic data + Fayda test credentials |
| Documentation | OpenAPI spec, code samples, Postman collection |

### Revenue share model
Third-party mini-apps keep 80–85% of their revenue; the platform takes 15–20% plus payment costs.
This mirrors the app-store model and is the mechanism by which the platform becomes an ecosystem.

### Metrics
Registered developers · live integrations · third-party GMV share · API uptime · time-to-first-
successful-call

---

## Module dependency and sequencing

| Module | Depends on | Earliest start |
|---|---|---|
| Advisory & data | Identity, data | Phase 1 (month 3) — can run before the marketplace |
| Marketplace & trade | Identity, payments, ledger, registry | Phase 1 (month 3) |
| Government & programmes | Identity, payments, consent | Phase 1 (month 6) |
| Logistics | Marketplace volume | Phase 2 (month 9) |
| Embedded finance | 2 seasons of ledger data | Phase 2 (month 12–15) |
| Developer platform | Stable APIs | Phase 4 (month 36) |

**Note:** advisory can and should launch *before* the marketplace. It builds the user base, tests the
channels, generates price data, and establishes trust — at low cost and low risk.

---

## What each module contributes to the whole

| Module | Revenue | Data | Trust | Lock-in |
|---|---|---|---|---|
| Marketplace | High (fees) | High (transactions) | High | High |
| Advisory | None | Medium (plot, behaviour) | **Very high** | Medium |
| Logistics | Medium (freight) | Medium (routes, costs) | Medium | Medium |
| Finance | **Very high** | Very high (repayment) | High | **Very high** |
| Government | High early | High (beneficiary) | High (state) | Medium |
| Developer | Low early | Low | Medium | **Very high** |

The portfolio is deliberately balanced: advisory buys trust, government buys revenue and users,
marketplace buys data, finance buys margin and lock-in.
