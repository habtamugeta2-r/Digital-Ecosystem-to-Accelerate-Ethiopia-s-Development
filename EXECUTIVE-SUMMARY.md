# Executive Summary

> *"Ethiopia has built the pipes. It has not yet built the market."*

---

## 1. The problem is a system, not a list

Ethiopia is the second most populous country in Africa (~135.5 million people, 2025) and among the
least urbanised (75.9% rural in 2025). Most people farm. Agriculture is ~32% of GDP and ~60% of
employment; **more than 12 million smallholder households produce over 95% of output on farms
averaging under one hectare.** Cereal yields sit near 2.6 tonnes per hectare, mechanisation is
around 5.7%, and irrigation covers only about 4–5% of cultivated land.

That structure produces a specific and durable pattern of failure:

- **Low productivity + rain dependence → chronic food insecurity.** 15–16 million people were
  projected to face acute food insecurity (IPC Phase 3+) by mid-2026. Poverty, measured at US$3/day
  (2021 PPP), was projected to reach **43% in 2025** — a reversal of two decades of progress.
- **Fragmented markets + weak logistics → high food prices and wasted output.** Post-harvest losses
  run **15–25% for cereals and 30–50% for horticulture.** Only ~13% of the road network is paved
  (Sub-Saharan average ~25%), road density is ~148 km per 1,000 km² versus an African average of
  ~204, and **~90–95% of trade moves through a single corridor to Djibouti.**
- **Missing finance → trapped subsistence.** Formal institutions meet roughly **2% of an estimated
  ETB 2.58 trillion annual agricultural credit demand.** Only 49% of adults had any financial
  account in 2024; 39.9 million adults had none.
- **Weak state delivery + corruption → cost and delay.** Ethiopia scores 38/100 and ranks 96/182
  on the 2025 Corruption Perceptions Index (improving slowly: 34 in 2021, 37 in 2024, 38 in 2025).
- **Conflict and climate → repeated destruction of the asset base.** Tigray's reconstruction need is
  estimated near US$5 bn with under 30% funded; renewed hostilities in late 2026 displaced people
  again. The Oxford Initiative on Peace and Recovery estimated the northern conflict could cost
  **~US$125 bn in lost GDP by 2027**.

These are not independent failures. **They are a loop.** Low yields cap incomes; low incomes cap
demand; thin demand caps the incentive to process, store and distribute; weak distribution raises
input costs and post-harvest losses; losses cut the surplus available for sale; and a small taxable
surplus leaves the state with little capacity to fix roads, extension or finance. Breaking the loop
requires interventions that work on **several nodes simultaneously** — which is exactly what a
shared digital layer does.

---

## 2. What changed since 2020: the rails now exist

The strategic situation is materially different from the one described in most Ethiopia strategy
documents written before 2023. Three foundational systems have moved from pilot to national
infrastructure.

**Identity.** Fayda, built on the open-source MOSIP platform under the Digital Identification
Proclamation 1284/2023, reached **53.4 million registrations by 31 October 2026**, with roughly
200,000 new registrations per day, ~200 million authentication operations, 150+ integrated partners
and over 208 million eKYC verifications. The National Bank of Ethiopia has mandated that **all bank
accounts link to Fayda by 31 December 2026**. Registration is free; institutions pay US$0.05–0.10 per
verification (from August 2026). The institutional vehicle was re-established in August 2026 as
**FaydaVerse**, with a public developer sandbox, eSignet/OpenID Connect authentication flow, and a
stated expansion path into digital credentials, citizen wallets and digital signing.

*This is the single most consequential change.* A verified, biometric, real-time identity layer
collapses the cost of KYC, subsidy targeting, credit underwriting, SIM registration and permit
issuance simultaneously.

**Payments.** Ethiopia now has genuine, interoperable, competing rails:
- **telebirr** (Ethio Telecom, launched May 2021): **60.59 million registered users** in FY2025/26,
  ETB 2.38 trillion in transactions in FY2024/25, 310,000 merchants, 320,000 agents, ETB 13.22 bn in
  micro-loans to 6.88 million customers.
- **M-Pesa Ethiopia** (Safaricom, launched August 2023): **5.2 million active users** in FY2026
  (+119%), 442.2 million transactions, 30,700+ merchants — and integrated with **EthSwitch** in
  October 2025, connecting it to 15 (now 30+) banks and wallets and interoperable EthQR merchants.
- **EthSwitch** as the national switch, with **EthioPay** instant payments (ISO 20022, >1 million P2P
  transactions in a single day in 2026), mandated interoperable QR, and a Unified Government Payment
  Platform in development.
- The **National Digital Payments Strategy 2026–2030** targets digital payment value rising from
  **82% of GDP (2024) to 750% of GDP (2030)**, 275 transactions per adult per year (from 54 in 2025),
  60% 30-day active account usage, 80% of G2P payments digital, and 70% adult smartphone ownership.

**Policy and data.** Digital Ethiopia 2025 completed and **Digital Ethiopia 2030 launched December
2025** (three pillars: expand access, ensure equal opportunity, build trust). The Personal Data
Protection Proclamation 1321/2024 (in force July 2024) gives Ethiopia a GDPR-shaped legal basis for
handling identity and transaction data. The **Digital Agriculture Roadmap 2032 (DAR)**, launched
February 2025, is a government-owned plan covering farmer profiling, digital extension, market
linkages, input track-and-trace, credit and insurance — with a PMU funded by the Gates Foundation and
projected to reach 30 million farmers.

**Connectivity is the lagging rail.** 29.5 million internet users (21.7%) in October 2025; 93.2
million cellular connections (68.4%); electricity access at Tier 1+ only **44%**. Ethio Telecom
reaches 82.2% 4G population coverage with 6,924 4G sites (target 95% and 11,014 by FY2026/27);
Safaricom covers ~59–60% with 3,504 sites. Smartphone penetration remains the binding constraint on
app-based services — which is why **USSD, IVR and agent networks are not transitional features but
permanent design requirements.**

---

## 3. Where digital can actually move the needle

Ranked by (size of problem addressed) × (leverage of digital) × (feasibility in Ethiopia's
constraints) × (evidence of effect):

| Rank | Opportunity | Why it ranks here |
|---|---|---|
| **1** | **Agriculture supply-chain platform** (marketplace + advisory + logistics + embedded finance) | Addresses ~60% of employment, ~32% of GDP, the largest poverty mass, and three binding constraints at once. Government already owns the roadmap (DAR). Private proof points exist (Lersha: 400,000+ farmers, 4,000+ agents). |
| 2 | SME / urban e-commerce marketplace | Large latent demand but thin purchasing power, brutal unit economics, and a history of failures (58% of Ethiopian e-commerce startups earn <US$10k/yr; Jumia exited 5 markets). Better as a **second act** on top of agri logistics. |
| 3 | Freight / logistics aggregator | High value per transaction (transport is a major cost driver), but fragmented ownership, weak digital readiness of truckers, and heavy dependence on the single Djibouti corridor. Natural **module** of #1. |
| 4 | Digital financial services (lending, savings, insurance) | Huge gap (2% of agri-credit demand met) but regulated, capital-intensive, and already contested by banks, telebirr and M-Pesa. Best pursued as **embedded finance inside #1**, not standalone. |
| 5 | Digital government / e-services | High social value, high political alignment (Digital Ethiopia 2030), but procurement-led and slow. Best pursued as **API integration** rather than competition. |

The evidence that agri-digital works in Ethiopia specifically is real but bounded:
- Static, site-specific fertilizer and agronomy advisory has delivered **14–25% yield gains** in
  wheat in CGIAR/AICCRA trials.
- The **8028 Farmers' Hotline** (IVR/SMS, 2014) has ~7 million registered users and 67 million calls,
  in five languages — the largest system of its kind in Africa.
- Low-cost UX iteration on that hotline raised successful access to advisory content by **24%**.
- **Lersha** demonstrates the "phygital" model: 9 apps, 4,000+ agents, offline-tolerant Android
  builds, 163,000–400,000+ registered farmers, ~18% active rate — roughly at par with leading
  Ethiopian fintechs.

What has *not* been demonstrated in Ethiopia is a **functioning digital marketplace at scale**. That
is the gap this dossier targets.

---

## 4. What the world teaches

| Model | Transferable lesson | What *doesn't* transfer |
|---|---|---|
| **M-Pesa, Kenya** | Agent networks beat branches; interoperability and free tiers drive volume (57.8% of M-Pesa transactions are free); measured poverty effect: **~194,000 households (2%) lifted out of poverty** (Suri & Jack 2016), driven by risk-sharing, not credit. | Kenya's 100%+ mobile money penetration and 333,000 M-Pesa agents took 19 years. Ethiopia is at a fraction of that agent density. |
| **India Stack (Aadhaar + UPI + ONDC + AA)** | The composable-layer model: identity → payments → consent → commerce protocol. UPI at **~21.7 billion transactions/month** (Jan 2026); DBT cumulative savings reported at **₹3.48–5.14 lakh crore**. ONDC is the closest analogue to an open agri-commerce protocol. | India had 1.4 bn enrolments, a mature banking system, and NPCI as a single mandated operator. Ethiopia's switch is younger and its banks thinner. |
| **Rwanda (Irembo)** | A PPP one-stop portal with **240 services, 3,000+ human agents, 45% digital payment share, >120 million hours saved** — and honesty that agents are what make it inclusive. | Rwanda is small, has strong state capacity and high political continuity. |
| **Estonia (X-Road, e-ID)** | "Once-only" principle; decentralised data exchange instead of a central database; digital signature with legal equivalence. Savings estimated at **~2% of GDP**. Start with government eating its own dog food (e-Cabinet, 2000). | 1.3 million people, pre-existing digital banking, and a legal culture built for it. |
| **China / SEA super-apps (WeChat, Alipay, Grab, Gojek)** | Start with one high-frequency transaction, then attach services; own the payment moment. | Required either a messaging monopoly or huge VC subsidy in markets with rising incomes. |
| **Jumia (pan-African e-commerce)** | The cautionary tale: **11 straight years of losses**, exit from South Africa and Tunisia (2024), exit from food delivery, repeated retrenchment. Focus on core, control logistics, don't chase GMV. | — |

**Synthesis:** shared infrastructure (ID + payments + consented data) lowers the cost of every
downstream service; network effects compound; but **every success required a phygital layer**
(agents, cash-in/cash-out, human help) and **a narrow starting wedge**.

---

## 5. Constraints that shape the design

| Constraint | Reality (2025–26) | Design consequence |
|---|---|---|
| Connectivity | 21.7% internet penetration; 44% Tier-1 electricity | USSD/IVR/SMS first-class; offline-capable agent apps; queue-and-sync |
| Devices | ~70% smartphone target by 2030 (i.e. ~30% today) | Never require a smartphone for the farmer |
| Payments | Interoperable but fragmented; FX scarce; card penetration tiny | Local currency only; telebirr + M-Pesa + bank rails; no card dependency |
| FX / macro | Birr 57→161/USD since July 2024; inflation 12–16%; debt in distress | Birr-denominated revenue; avoid USD capex; price in hard-currency-linked terms only where legal |
| Regulation | Data protection law new and untested; mobile money rules evolving | Privacy-by-design, DPIA at launch, multi-rail by architecture |
| Language | 80+ languages; 5 supported by 8028 | Amharic, Afaan Oromo, Tigrinya, Somali, Afar at MVP; voice-first |
| Literacy | 90% of 10-year-olds cannot read a simple text | Voice and icon interfaces; agents as interpreters of last resort |
| Trust | Cash culture; fraud fear; conflict history | Escrow, verified badges, money-back first-transaction guarantee, cooperative anchoring |
| Market size | GDP ~US$210 bn (rebased) but formal retail small | Fees must be tiny and volumes huge; government/NGO contracts as anchor revenue |
| Security | CPI 38/100; conflict risk | Tamper-evident records, audit trails, geographic redundancy |

---

## 6. The proposed ecosystem

A **modular platform** with a thin, defensible core and many attachable services.

**Core (shared) layers**
1. **Identity & authentication** — Fayda/FaydaVerse eKYC via eSignet/OIDC; role-based credentials for
   farmers, cooperatives, buyers, transporters, agents; USSD fallback with PIN + agent attestation.
2. **Payments & wallet orchestration** — abstraction over telebirr, M-Pesa, bank APIs via EthSwitch;
   escrow, split payments, scheduled disbursement, credit disbursement and repayment.
3. **Data & API layer** — farmer/plot registry, commodity and price data, weather and soil layers,
   consent management (aligned to Proclamation 1321/2024), and public/partner APIs.

**Application modules**
4. **Marketplace / trading hub** — listings, bids, forward contracts, quality grading, verified
   sellers, delivery scheduling.
5. **Advisory & data tools** — weather, agronomy, pest alerts, price feeds; SMS/IVR/voice + agent.
6. **Logistics coordination** — truck booking, aggregation points, tracking, proof of delivery.
7. **Embedded finance** — input credit, working capital, savings, index insurance; underwritten on
   platform transaction history (this is the moat).
8. **Government & utility services** — subsidy and input-voucher disbursement, e-permits, tax.
9. **Developer ecosystem** — SDKs, sandbox, revenue share for third-party mini-apps.

**The feedback loop that creates the moat:**

> Identity enables trust → trust enables a transaction → the transaction creates data → data enables
> credit → credit buys inputs → inputs raise yield → higher yield creates a larger transaction →
> which creates better data.

Each turn of that loop raises switching costs and improves underwriting. It is the only defensible
asset in a market where the rails themselves are commoditised.

---

## 7. Business model in brief

| Stream | Mechanism | Illustrative take |
|---|---|---|
| Marketplace commission | % of GMV on matched trades | 1–3% |
| Payments | Spread / share on wallet and escrow float | 0.3–0.8% |
| Embedded finance | Origination fee + servicing share on loans and insurance | 1–3% of principal |
| Input commerce | Margin or listing fee on seed/fertiliser/mechanisation | 3–8% |
| Data & analytics | Seasonal reports, area/yield estimates, ESG and traceability | Subscription / per-report |
| Government & NGO programmes | Delivery of subsidies, vouchers, extension, M&E | Contract / per-beneficiary |

Deliberately **not** a model: monetising farmers' basic advisory access (kills adoption), or
depending on card rails and ad spend (too small, too early).

Order-of-magnitude sanity check (⚪ illustrative, not a forecast): if the platform intermediates
**1% of Ethiopia's ~30–33 Mt cereal crop** at an average farmgate value of ~ETB 25,000/t, that is
~8 million tonnes → ~ETB 200 bn GMV → **ETB 2–6 bn (~US$12–37 m) gross revenue at 1–3%**, before
finance, input, data and programme revenue. At 5% penetration the same arithmetic is 5× that.
The model is **volume × basis points**, which is why interoperability and agent density matter more
than feature depth.

---

## 8. Implementation in five phases

| Phase | Window | Focus | Exit criterion |
|---|---|---|---|
| **0 — Foundations** | Months 0–4 | Legal entity, Fayda integration, payment rails, data protection DPIA, 2 cooperatives signed, team | Sandbox transactions end-to-end; first 1,000 verified users |
| **1 — Single-commodity pilot** | Months 3–12 | One commodity (recommended: **maize or wheat in a surplus woreda cluster in Oromia or Amhara**), one region, 5,000–10,000 farmers, 20–50 buyers, escrow + Telebirr, agent onboarding | ≥40% of onboarded farmers transact twice; price realisation up ≥8% vs. local baseline; loss rate down ≥5 pp |
| **2 — Services & finance** | Months 9–24 | Advisory (SMS/IVR), input credit with a bank/MFI partner, logistics booking, 3 commodities, 3 regions | Loan book with <5% PAR-30 in pilot cohort; logistics cost per tonne-km down |
| **3 — Scale** | Months 18–42 | 10+ regions, livestock/dairy/horticulture, M-Pesa parity, multi-language, cooperative federations | 500,000+ active farmers; positive contribution margin per transaction |
| **4 — Open platform** | Months 36–60 | Public APIs, developer sandbox, third-party mini-apps, government service integration | ≥20 third-party apps; ≥30% of GMV from partners |

**Pilot design principle:** the MVP must be *embarrassingly narrow*. One crop. One cluster. Two
cooperatives. One payment rail plus cash via agents. A price board, a listing, an escrow, a truck.
Everything else is Phase 2.

---

## 9. Top risks and how they are handled

| Risk | Mitigation |
|---|---|
| **Conflict and political instability** (highest) | Region-diversified rollout; no single-region dependency; align to national programmes; keep operations light and relocatable; scenario planning for corridor and region closure |
| **Low adoption / digital divide** | USSD/IVR-first; village agents; cooperative anchoring; free core advisory; first-transaction guarantee |
| **Unit economics never cross over** | Fee discipline; asset-light logistics; agent commissions tied to GMV not signups; kill criteria at each phase gate |
| **Regulatory change** (mobile money, data, agri trading) | Multi-rail architecture; PP partnership structure; legal review of every data flow; proactive engagement with NBE, MoA, FaydaVerse |
| **Fraud and cyber** | Escrow, KYC on Fayda, device fingerprinting, anomaly detection, penetration testing, incident response plan, insurance |
| **Macro / FX / inflation** | Birr revenue and costs; no USD debt dependency; monthly re-pricing of fee schedules |
| **Incumbent response** (telebirr, Ethio Telecom, banks, Safaricom) | Partner rather than compete; be the best *application* on their rails; own the agri data and relationships they cannot easily replicate |
| **Climate shock in the pilot area** | Multi-zone pilot; index insurance from Phase 2; do not underwrite yield risk on balance sheet |

---

## 10. Recommendation

**Build the digital agriculture supply-chain platform — but build it as a narrow, agent-anchored,
identity-native marketplace for one commodity in one region, on top of rails Ethiopia already owns.**

Specifically:

1. **Anchor on Fayda** for KYC and account identity. Do not build an identity system.
2. **Anchor on telebirr + M-Pesa + EthSwitch** for money movement. Do not become a payment
   institution unless Phase 2 economics prove it necessary.
3. **Anchor on cooperatives and existing agent networks** for trust and physical reach. Do not try
   to reach farmers directly at the start.
4. **Anchor on the Digital Agriculture Roadmap** for policy cover and co-funding. Do not create a
   parallel national strategy.
5. **Own the data and the relationship**, because that is the only layer that compounds.

**Why this and not something else:** it targets the sector that employs ~60% of Ethiopians and
produces ~32% of GDP; it attacks three binding constraints (market access, finance, information)
with one asset; it converts two newly national systems (identity, payments) into economic value; and
it has a plausible path from a fee-based marketplace to national rural infrastructure.

**Why now:** Fayda crossed 53 million and became mandatory for banking; mobile money became
interoperable; the birr float and FX reform forced formality and re-pricing in agricultural trade;
the DAR created a government counterpart; and post-harvest losses plus food insecurity have made
market efficiency a political priority rather than a technical one.

**What would change our mind:** sustained closure of the Djibouti corridor or a widening war in
Oromia/Amhara (kills logistics assumptions); a regulatory decision reserving agri-marketplace
payments to a state monopoly; telebirr or Ethio Telecom launching an equivalent, well-executed agri
marketplace and locking in the cooperatives; or two consecutive pilot seasons failing the
price-realisation and repeat-transaction tests.

---

## Read next

- Full context and evidence: [`01-context/`](01-context/README.md)
- The top opportunity in depth: [`02-opportunities/01-agriculture-platform.md`](02-opportunities/01-agriculture-platform.md)
- Architecture: [`05-ecosystem/`](05-ecosystem/README.md)
- Numbers and corrections: [`data/fact-ledger.md`](data/fact-ledger.md)
