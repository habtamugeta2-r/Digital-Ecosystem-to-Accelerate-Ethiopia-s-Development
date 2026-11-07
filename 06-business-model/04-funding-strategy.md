# 06.4 · Funding Strategy

*Part of [06 · Business model](README.md)*

The capital requirement is small (~ETB 80 m / US$0.5 m to break-even, ~ETB 200 m / US$1.3 m to raise
for safety), but the **mix** of capital matters as much as the amount. This file sets out what to raise,
from whom, and in what order.

---

## 1. Capital plan by phase

| Phase | Months | Activity | Capital need (ETB m) | Source |
|---|---|---|---|---|
| 0 | 0–6 | Design, partnerships, licences, pilot prep | 12–18 | Grant / founder |
| 1 | 6–18 | Single-commodity pilot, 1–2 regions | 30–45 | Grant + seed equity |
| 2 | 18–36 | Services, finance, 3–4 regions | 60–90 | Seed/A equity |
| 3 | 36–48 | Scale to national footprint | 150–300 | Series A/B |
| 4–5 | 48–72 | Platform and API economy | 300–600 | Series B/C + DFI debt |
| **Total to break-even** | | | **~80–150** | |

**Note:** the ETB 80 m is the *net* need. Gross raised should be 1.5–2× to absorb variance. This is the
most under-appreciated point in the whole plan.

---

## 2. Capital stack — what fits where

| Instrument | Amount | Use | Why this instrument |
|---|---|---|---|
| **Grant (DAR/ATI/Gates/IFC)** | ETB 25–50 m | Content, advisory, cooperative onboarding, M&E | Public-good outputs: advisory is free, so it must be grant-funded |
| **Development finance equity (IFC, BII, Norfund, Proparco)** | ETB 60–150 m | Core platform, working capital | Patient capital; impact mandate matches; accepts 7–10 year horizon |
| **Local impact equity (Rift Valley, Launch Africa, Catalyst)** | ETB 20–60 m | Growth, local presence | Local networks; follow-on support |
| **Blended finance / first-loss facility** | ETB 20–50 m (guarantee) | De-risk lender entry | Unlocks bank balance sheets at low cost to the platform |
| **Working capital debt** | ETB 30–80 m (revolver) | Bridge programme receivables | Non-dilutive; matches cash cycle |
| **Strategic partner equity (telco, bank)** | Optional | Distribution or payments | Access > money |
| **Revenue-based / venture debt** | Phase 3+ | Growth without dilution | Only once revenue is predictable |

---

## 3. Sequencing logic

```
Grants (Phase 0–1) ──► Seed equity (Phase 1–2) ──► Series A (Phase 2–3)
        │                      │                          │
        ▼                      ▼                          ▼
  prove concept         prove unit economics      prove scale
  no dilution           small dilution            growth capital
```

**Rule: raise each round on evidence, not on narrative.**

| Round | Evidence required |
|---|---|
| Grant | Signed MoU with a ministry or ATI; pilot design |
| Seed | 5,000 farmers, 1,000 completed transactions, positive contribution margin |
| Series A | 2 seasons of data, 1 lender partner, ETB 1 bn GMV, <5% dispute rate |
| Series B | Multi-region, multi-commodity, 2+ lenders, ETB 10 bn GMV |

**Do not raise on projections.** In this market, investors have heard the projections before; evidence of
repeat transactions is the only currency.

---

## 4. The grant-first argument

A considerable share of the platform's value is a **public good**: free advisory, price transparency,
producer data, market intelligence, reduced post-harvest loss, financial inclusion. These outputs are
non-excludable and non-rival — a classic case for public funding.

| Public-good function | Appropriate funder |
|---|---|
| Advisory content at scale | ATI, Gates, Mastercard Foundation, GIZ |
| Farmer registration and ID linkage | Government, World Bank |
| Post-harvest loss reduction | USAID, FAO, AfDB |
| Financial inclusion of women and youth | UNCDF, FSD Africa, IFC |
| Market information system | Government, EU, DFID/FCDO |
| Traceability for EUDR compliance | Exporters, EU programmes |

**Approach: separate the P&L.** Run the public-good functions in a not-for-profit subsidiary or under
restricted grant agreements, and the commercial functions in the PLC. This is standard practice and it
prevents grant compliance from strangling the business.

---

## 5. The blended-finance facility (the highest-leverage instrument)

This is the single most important structure to get right, because **it unlocks lending without putting
credit risk on the platform's balance sheet.**

```
   DFI / donor (e.g. IFC, BII, Gates)
              │
              ▼
   First-loss guarantee fund (ETB 20–50 m)
              │
              ▼
   Partner bank / MFI lends to farmers
              │
              ▼
   Platform originates, services, and deducts repayment at settlement
              │
              ▼
   Defaults absorbed by the guarantee first (up to 10–20% of principal)
```

| Element | Purpose |
|---|---|
| First-loss tranche (10–20%) | Makes the bank whole on early defaults while it learns the segment |
| Platform as LSP | Platform does origination and servicing without a lending licence |
| Ledger data | Underwriting basis |
| Settlement deduction | Repayment mechanism |
| Performance reporting | Proves the model; guarantee shrinks over time |

**Why this matters:** a US$0.3 m guarantee can support US$1.5–3 m of lending — a 5–10× multiplier on
development capital, and it costs the platform nothing except administration.

**Over time:** as default data accumulates, the guarantee requirement falls and eventually becomes zero.
At that point the platform is a pure origination channel and finance becomes the highest-margin line.

---

## 6. What not to raise

| Instrument | Why not |
|---|---|
| **Pure VC on a 5-year exit clock** | Infrastructure takes 8–12 years; misaligned horizon |
| **Debt on the platform's balance sheet for farmer lending** | Regulatory classification; credit risk; FX risk |
| **Convertible notes with aggressive discounts** | Creates messy cap table before Series A |
| **Strategic equity from a single telco** | Creates channel conflict with the other operator |
| **Crowdfunding equity** | Regulatory complexity; small ticket sizes; reputational risk |
| **Too much grant funding** | Distorts incentives; delays commercial discipline; can make the entity ineligible for later equity |

**The last one deserves emphasis:** too much grant money is a real risk. It allows a team to avoid
decisions about pricing and repeat rate for years. Set a rule: **grants can fund public goods, never
operating losses on commercial functions.**

---

## 7. Investor narrative (one paragraph)

> Ethiopia has 12–15 million smallholder households producing over 30 million tonnes of cereals, with
> almost no verified data on who produced what, no functional smallholder credit market (only ~2% of a
> US$1.6 bn annual demand is met), and no digital infrastructure connecting farmers to buyers. We are
> building the transaction layer: an agent-anchored, Fayda-native agricultural marketplace that settles
> in escrow, records every transaction in an auditable ledger, and converts that ledger into credit.
> Ethiopia's digital public rails — Fayda (53 m registered), telebirr (60 m), EthSwitch, and a
> national payments strategy targeting 275 transactions per adult by 2030 — mean the hard infrastructure
> is being built by others. We are the agricultural application layer on top of it. We reach break-even
> on under US$1.5 m, and the asset we accumulate — the first verified smallholder production and
> repayment dataset in the country — cannot be bought, only earned over multiple seasons.

---

## 8. Use of funds (Seed, ETB 90 m / US$0.56 m)

| Category | % | ETB m | Detail |
|---|---|---|---|
| Engineering and product | 38% | 34 | 10 engineers, 1 designer, 1 PM for 18 months |
| Field operations | 22% | 20 | 5 regions, agents, cooperative onboarding |
| Agronomy and content | 8% | 7 | 3 agronomists; EIAR/ATI content partnership |
| Compliance and legal | 7% | 6 | Licences, DPIA, contracts, NBE engagement |
| Technology infrastructure | 8% | 7 | Hosting, SMS/USSD/IVR, FaydaVerse fees |
| Working capital | 12% | 11 | Programme receivables, guarantee provision |
| Contingency | 5% | 5 | |

---

## 9. Milestones tied to funding

| Milestone | Evidence | Unlocks |
|---|---|---|
| M1: Government MoU | Signed with MoA or ATI | Grant tranche |
| M2: 1,000 transactions | Settled, escrow-cleared | Seed close |
| M3: Positive contribution margin | Monthly cohort data | Series A conversations |
| M4: First lender live | Loan disbursed and repaid | Blended facility |
| M5: Second season repeat ≥40% | Cohort tracking | Series A close |
| M6: 3 regions profitable | Regional P&L | Series B |

---

## 10. Governance expectations of investors

| Requirement | Platform commitment |
|---|---|
| Board with independent chair by Series A | Agreed |
| Quarterly audited management accounts | Agreed |
| Impact metrics reported to standard (IRIS+) | Agreed |
| Data protection audit annually | Agreed |
| No related-party transactions without approval | Agreed |
| Cooperative equity tranche preserved | Agreed (ESOP-like reserve) |
| Double-materiality / ESG report from Year 2 | Agreed |

**The cooperative equity tranche is unusual and worth defending:** reserving 5–10% for cooperatives
converts the platform's most important stakeholders into owners and is the strongest available defence
against political and community opposition.
