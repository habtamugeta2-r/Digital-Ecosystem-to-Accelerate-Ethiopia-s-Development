# 01.4 · Institutions, Governance and the Business Environment

*Part of [01 · Context](README.md)*

---

## 1. Corruption and institutional quality

| Indicator | Value | Year | Confidence |
|---|---|---|---|
| Corruption Perceptions Index score | **38/100** | 2025 | 🟢 |
| CPI rank | **96/182** | 2025 | 🟢 |
| CPI trajectory | 34 (2021) → 37 (2024) → 38 (2025) | — | 🟢 |
| Global CPI average | 42/100 | 2025 | 🟢 |

> ⚠️ **Correction to the source brief.** The brief cited "~96/182 in 2024". Ethiopia's 2024 CPI was
> **37/100, rank 99/180**. The 2025 edition (published February 2026) is **38/100, rank 96/182**.
> The direction is mildly positive — Ethiopia is one of 31 countries that improved since 2012 — but
> the level remains below the global average and the improvement is small relative to the scale of
> the problem. Use the 2025 figure.

**What corruption costs a digital platform, concretely:**
- **Weighbridge and checkpoint rent-seeking** along transport corridors — a per-trip cost that must
  be modelled into logistics unit economics.
- **Discretionary licensing** — permits, export licences, and quality certificates that can be
  delayed.
- **Procurement risk** — government contracts can be politically reallocated.
- **Aid diversion history** — the 2023 food-aid diversion scandal triggered a nationwide pause and
  made donors (and citizens) sceptical of in-kind distribution; this actually **favours digital,
  traceable transfer models**.

**What digital infrastructure can and cannot fix:** it can reduce discretionary human contact
(e-government portals, automated subsidy targeting, tamper-evident records, published prices). It
cannot fix political capture. The realistic claim is modest but real: Rwanda's Irembo users
explicitly reported reduced bribery because the payment and application process no longer required
an official's discretion.

---

## 2. The state-owned enterprise footprint

| Sector | State presence | Consequence for a platform |
|---|---|---|
| Telecom | Ethio Telecom (90.12 m customers; telebirr 60.59 m) | Your payment rail and your potential competitor |
| Banking | Two state banks hold ~half of sector assets; state-directed credit | Credit partner and potential competitor |
| Payments switch | EthSwitch (bank-owned) | Mandatory interoperability partner |
| Commodity exchange | ECX | Potential partner for grading/warehousing; potential competitor for trade |
| Energy | EEP, EEU | Reliability risk; tariff reform in progress |
| Retail/wholesale | Recently opened; 40 foreign permits issued | New competition in urban commerce |

**The crowding-out problem, stated precisely.** State-owned credit rose from ~14% of total domestic
credit (2007) to ~60% (2018), largely directed to SOEs and infrastructure. Private firms — including
agribusinesses and SMEs along agricultural value chains — were squeezed out. If the platform's
embedded-finance module depends on bank balance sheets, it is competing for a shrinking private
credit pool. This argues for **partnering with MFIs, fintechs and development finance** (IFC,
Dashen risk-sharing facility, NAFIR risk-sharing instruments) rather than relying on commercial bank
appetite alone.

---

## 3. The regulatory environment, dated

| Instrument | Year | What it does | Relevance |
|---|---|---|---|
| Digital Identification Proclamation **1284/2023** | 2023 | Establishes Fayda, the national digital ID system; rules on data quality, locking, revocation | Legal basis for identity-based KYC and account linking |
| Personal Data Protection Proclamation **1321/2024** | 2024 (in force Jul 2024) | GDPR-shaped: consent, data-subject rights, DPIAs, breach notification, cross-border transfer limits, extraterritorial reach | Every data flow in the platform must be designed against this |
| Payments Instrument Issuers Directive | 2020 | Legalised mobile money; introduced tiered KYC | Enabled telebirr and M-Pesa |
| Licensing Directive for Payment Operators | 2020–21 | Opened switching, POS, ATM, gateway services to non-banks | Enables payment intermediaries |
| National Digital Payments Strategy (NDPS) 2021–2024, then **NDPS 2026–2030** | 2021, 2025 | Interoperability, instant payments, QR standardisation, inclusion targets | Alignment and possible licensing path |
| National Financial Inclusion Strategy (NFIS-II) | 2021–25 | Account ownership target 70% (not met; 49% actual) | — |
| Telecom liberalisation | 2021 | Safaricom unified licence; second operator | Multi-rail payments |
| Mobile money opening to foreign-owned firms | 2023 | Enabled M-Pesa Ethiopia | Multi-rail payments |
| Directive **1106/2025** (coffee) | 2025 | Expanded vertical integration and direct delivery in coffee | Confirms policy direction toward disintermediation and traceability |
| National Agri-Finance Implementation Roadmap (NAFIR) 2025–2030 | 2025 | ETB 881 bn agri-credit target; risk-sharing; agri bank | Finance partner architecture |
| Digital Agriculture Roadmap (DAR) 2032 | 2025 | National digital agriculture plan with PMU | Policy cover and co-funding |
| Digital Ethiopia 2030 | 2025 (launched Dec) | Successor strategy; access, equity, trust; AI and data governance | Umbrella strategy |
| Post-Harvest Management Strategy 2024–2030 | 2024 | National loss-reduction strategy | Directly aligned with the marketplace thesis |

**Reading the direction of travel.** Across identity, payments, data protection, agriculture finance
and commodity trading, Ethiopian policy between 2023 and 2026 moved consistently in one direction:
**formalise, digitise, interoperate, trace.** A digital agricultural marketplace is not a deviation
from policy; it is the intended destination.

**The risks in the same direction of travel:**
- **Licensing ambiguity.** It is not yet settled whether an agri-marketplace handling escrow needs a
  payment-instrument licence, an agent-network licence, or neither. This must be resolved with NBE
  before launch, not after.
- **Data localisation.** Proclamation 1321/2024 restricts cross-border transfer; cloud architecture
  must be Ethiopia-hosted or explicitly approved.
- **Price controls and trade restrictions.** Ethiopia has periodically imposed price caps and export
  bans on commodities. A marketplace must be able to suspend and re-price instantly.
- **Mobile money exclusivity history.** telebirr had a period of effective exclusivity (petrol
  stations and 600+ government institutions accepted only telebirr), which slowed M-Pesa. Multi-rail
  design protects against a policy reversal in either direction.

---

## 4. Doing business: the practical frictions

| Friction | Practical effect |
|---|---|
| Foreign exchange scarcity and allocation | Importing devices, vehicles, servers or software licences requires FX that is rationed |
| Import permits and customs delays | Hardware lead times of months; buffer stock essential |
| Capital controls | Repatriation of profits/investment requires approval; structure must anticipate this |
| Business registration and licensing | Multi-step, multi-agency; budget 3–6 months |
| Land and office access | Addis Ababa costs are high; regional offices cheaper but harder to staff |
| Talent | Strong engineering supply (Addis Ababa University, A2SV alumni network, AI Institute); scarce product, agronomy and data-engineering talent |
| Security | Kidnapping and theft risk in some regions affects field staff deployment |
| Internet reliability | Frequent outages; offline-first is mandatory |

> **Talent note.** Ethiopia has an unusually strong software talent base relative to its income
> level — a legacy of university expansion, the Addis Ababa tech scene, and diaspora return. This is
> a genuine comparative advantage for building the application layer locally rather than importing
> it.

---

## 5. The public-sector partner map

| Institution | Role | Why engage |
|---|---|---|
| **FaydaVerse / NIDP** | Digital ID issuance and authentication | eKYC, account linking, credential verification; public sandbox available |
| **National Bank of Ethiopia** | Payments, banking, MFI regulation; NAFIR/NDPS | Licensing clarity, risk-sharing instruments, digital payment targets |
| **EthSwitch** | National switch, instant payments, QR, UGPP | Interoperability, escrow settlement, government payments |
| **Ethio Telecom / telebirr** | Dominant mobile money and connectivity | Wallet, USSD, agent network, SMS |
| **Safaricom Ethiopia / M-Pesa** | Second operator and wallet | Redundancy, competition, lower fees |
| **Ministry of Agriculture** | DAR, extension, input vouchers, post-harvest strategy | Policy cover, programme contracts, cooperative access |
| **Agricultural Transformation Institute (ATI)** | 8028 hotline, digital market linkage platform, input voucher system | Advisory content, existing farmer base, avoid duplication |
| **Ethiopian Commodity Exchange** | Grading, warehousing, electronic receipts | Quality standards, storage finance |
| **Cooperative Promotion / regional cooperative bureaus** | 30,000+ cooperatives | The single fastest route to organised farmer supply |
| **Ethiopian AI Institute** | National cloud, language models, agri AI | Speech-to-text for local languages, compute, pest/disease models |
| **Development partners** (World Bank, Gates, IFC, GIZ, USAID-successor programmes, FSD Ethiopia) | Grant and blended finance | Pilot funding, de-risking, credibility |

---

## 6. What this means for the project

1. **Engage NBE early** on the licensing question for escrow and agent networks. A 6-month delay
   here can kill a launch window.
2. **Design for Ethiopian data residency** from day one; do not retrofit.
3. **Do not build identity, payments or the switch.** They exist. Build on them.
4. **Use the state's own strategy documents (DAR, NAFIR, NDPS, PGMS) as your business plan annex.**
   It converts a private proposal into a national programme component and unlocks co-funding.
5. **Budget for friction**: FX, permits, import delays, security, and 3–6 months of licensing.
6. **Treat corruption as a cost line and a design constraint**, not a moral footnote: automate
   discretion wherever a payment, certificate or approval is involved.
