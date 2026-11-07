# 02.4 · Government and Public Services

*Part of [02 · Opportunities](README.md) · Ranked #5 as a business, #1 as an alignment strategy*

> **Verdict.** Ethiopia's e-government opportunity is large, politically central and **state-led**.
> A private organisation cannot own it, but it can be the **operational layer** that makes it work —
> and that is a durable, cash-generating position.

---

## 1. What Ethiopia is building

| Initiative | Status (2026) | Owner |
|---|---|---|
| **Fayda digital ID** | 53.4 m registrations; 150+ integrated partners; 208 m+ eKYC verifications; public developer sandbox; rebranded **FaydaVerse** | NIDP / FaydaVerse |
| **Digital Ethiopia 2030** | Launched Dec 2025; pillars: expand access, equal opportunity, trust; AI, cybersecurity, data governance | PMO |
| **National Digital Payments Strategy 2026–2030** | Digital payments from 82% → 750% of GDP; 80% of G2P digital by 2030; all bank accounts Fayda-linked | NBE |
| **EthSwitch Unified Government Payment Platform (UGPP)** | Presented at Ethiopia Finance Forum 2026; consolidates P2G collections | EthSwitch |
| **EthioPay instant payment system** | Live; ISO 20022; >1 m P2P transactions/day | EthSwitch |
| **Digital Agriculture Roadmap 2032** | Launched Feb 2025; PMU funded by Gates Foundation; 30 m farmer target | MoA / ATI |
| **Input Voucher System** | Operational digitisation of input distribution | ATI |
| **National Market Information System (6077)** | Commodity prices from ~157 markets | ATI |
| **8028 Farmers' Hotline** | ~7 m registered users; 67 m calls; 5 languages | ATI |
| **Fayda-linked student registration** | Mandatory for school registration and national exams | MoE |
| **National data cloud / AI Institute** | Sovereign cloud build; local-language speech models | Ethiopian AI Institute |

**Reading:** the state has built the front door (identity), the plumbing (payments) and the strategy
documents. What it has not built — and structurally struggles to build — is **an operational service
layer with product discipline, uptime, user support and iteration speed**.

---

## 2. The four models for private participation

| Model | Description | Revenue | Control | Examples |
|---|---|---|---|---|
| **Vendor / contractor** | Build and operate a system for a ministry under procurement | Contract value | Low | Typical government IT contracts |
| **PPP platform** | Operate a citizen-facing service on a concession, retain fee income | Transaction or service fees | Medium | **Rwanda's Irembo** |
| **API / infrastructure supplier** | Provide identity, data or payment APIs to government systems | Usage fees | Medium | **India's NPCI ecosystem**, **Estonia's X-Road** |
| **Programme delivery partner** | Deliver subsidies, vouchers, extension or M&E for government/donors | Per-beneficiary fee | Medium | WFP/CRS voucher programmes |

The **PPP** and **programme delivery partner** models are the most attractive in Ethiopia: they pay,
they align with policy, and they build operational capability rather than one-off software.

---

## 3. The specific services worth building

### 3.1 Subsidy and voucher delivery (highest near-term value)

**The problem:** in-kind distribution leaks, duplicates, and is slow. The 2023 food-aid diversion
scandal forced a nationwide pause. Donors are shifting to cash and vouchers.

**The mechanism:**
```
Government/donor defines eligibility
        ↓
Fayda verification + de-duplication
        ↓
Digital voucher / cash issued to wallet (telebirr / M-Pesa / bank)
        ↓
Farmer redeems at an accredited input dealer (on-platform)
        ↓
Dealer redeems with platform; platform settles and reports in real time
```

**Benefits across the chain:** no ghost beneficiaries (biometric de-dup), no diversion (digital trail),
price transparency (dealer competition), real-time monitoring (dashboard), and market stimulus (cash
spent locally).

**Evidence base:** India's DBT system reports cumulative savings of **₹3.48–5.14 lakh crore** by
eliminating duplicate and ghost beneficiaries across PDS, MGNREGS, PM-KISAN and LPG. Ethiopia's
equivalent scope (fuel subsidies, input vouchers, safety nets, school feeding) is smaller but the
mechanism is identical.

### 3.2 Permit, licence and tax e-services

Streamline what currently requires physical presence: agricultural export permits, phytosanitary
certificates, cooperative registration, business licensing, land-use certificates. The value is time
saved (Rwanda's Irembo reports **>120 million hours saved** and a **>80% reduction** in service
time) and reduced discretionary contact (reduced bribery).

### 3.3 Open data and market intelligence

- Commodity prices by market, daily (built on ATI's 6077)
- Weather and forecast data (EthioMet)
- Soil maps (EthioSIS)
- Land use and crop area estimates (remote sensing)
- Post-harvest and logistics indicators

Published openly, this data is a **public good** that raises the productivity of every private actor.
It is also the cheapest possible demonstration of the platform's legitimacy.

### 3.4 Digital extension

Build on 8028 rather than replace it: add plot-specific advisory, pest alerts, and two-way feedback
(which also generates ground-truth data for the government's crop forecasts).

### 3.5 G2P cash transfers

Ethiopia's Productive Safety Net Programme and humanitarian cash transfers are moving toward digital
delivery, and the NDPS targets 80% of G2P payments digital by 2030. A platform with verified farmer
identities and agent cash-out capability is the natural delivery channel.

---

## 4. Why the state needs a private operator

| Public-sector constraint | Private operator's answer |
|---|---|
| Procurement cycles of 12–24 months | Ship in weeks |
| No product management discipline | Roadmap, user research, A/B tests |
| Difficulty retaining engineers | Competitive compensation, mission |
| Political churn in leadership | Continuity of operations |
| Weak customer support infrastructure | Call centres, agent networks |
| Limited uptime/ops culture | SRE practices, SLAs |
| Budget cycles | Absorbs working-capital needs |

**But be realistic:** the state controls the licence, the data and the customer. A private operator in
this space has real revenue and real leverage, but not durable control. That is acceptable — it is a
cash-generating, relationship-building position, not a moat.

---

## 5. Risks and how they differ from commercial risk

| Risk | Nature | Mitigation |
|---|---|---|
| **Payment delay** | Government and donor receivables can run 90–365 days | Working capital facility; milestone-based contracts; diversified client base |
| **Political reallocation** | A contract can be reassigned after a leadership change | Multiple ministries/donors; contractual protections; deliver visible results |
| **Scope creep** | "While you're at it…" expands cost without revenue | Fixed-scope statements of work; change control |
| **Data access disputes** | Ownership of data generated under a government contract | Negotiate data rights explicitly up front |
| **Procurement competition** | Price-based tendering erodes margin | Differentiate on operational track record, not price |
| **Corruption exposure** | Kickbacks and influence | Written compliance policy; refuse, document, escalate |
| **Being nationalised or duplicated** | State builds its own version | Partner posture; make yourself the implementation, not the obstacle |

---

## 6. Sequencing recommendation

| Phase | Government work | Why then |
|---|---|---|
| 0–1 | Fayda integration (eKYC), EthSwitch settlement, NBE licensing clarity | Prerequisites for everything |
| 1 | One voucher or transfer programme with a cooperative and a donor | Revenue before marketplace liquidity; builds trust with MoA |
| 2 | Price data publication, extension content integration, e-permits for agri trade | Builds legitimacy and data |
| 3 | Full G2P delivery, subsidy targeting at scale, M&E dashboards | Requires proven operational scale |
| 4 | Open API to government systems (identity, land, weather, payments) | Platform becomes infrastructure |

---

## Key takeaways

1. Ethiopia has built the front door and the plumbing; the missing layer is **operational service
   delivery with product discipline** — a legitimate private role.
2. The highest near-term value is **Fayda-verified voucher and cash-transfer delivery**, which has
   strong donor demand, policy alignment and an India-scale evidence base.
3. Open data and price publication are cheap, high-leverage public goods that build legitimacy.
4. Choose the **PPP or programme-delivery** model over pure contracting; avoid owning the strategy.
5. Expect long receivables and political risk; price and diversify accordingly.
