# 07.5 · Phases 4 and 5 — Platform and Ecosystem (Months 54–84)

*Part of [07 · Implementation](README.md)*

The phases in which the platform stops being a company and becomes **infrastructure** — the point at
which others build on it. This is the "digital ecosystem" the whole document is named after, and it is
only reachable after five years of transaction data.

---

## Phase 4 — Open platform (Months 54–69)

### Objective
Turn the platform's capabilities into **public building blocks** that third parties use, so growth no
longer depends on the platform's own salesforce.

### What is opened

| Asset | Access model | Who uses it |
|---|---|---|
| Price API | Open, free, rate-limited | Everyone — becomes the national reference |
| Listing / order API | Registered developers | Agritech apps, buyer ERPs |
| Verification API | Partners, consent-gated | Insurers, lenders, input suppliers |
| Credit eligibility API | Licensed lenders | Banks, MFIs, digital lenders |
| Logistics API | Contracted transporters | Fleet apps, 3PLs |
| Advisory content API | Free to accredited NGOs/extension providers | MoA, ATI, NGOs |
| Webhooks | All partners | Real-time integration |

### Developer programme

| Element | Detail |
|---|---|
| Sandbox | Synthetic data, Fayda test FINs, mock payments |
| Documentation | OpenAPI 3.1, guides, code samples, Postman collection |
| Support | Developer forum, monthly office hours |
| Commercial model | 80–85% of revenue to the developer; 15–20% to the platform |
| Certification | Badge for apps meeting security and UX standards |
| Grant fund | Small grants (ETB 500k–2 m) to build high-value apps |

### Target apps (examples of what should be built by others)

| App | Builder | Value |
|---|---|---|
| Soil testing and fertiliser recommendation | Agritech startup | ↑ yield |
| Cold storage booking | Logistics startup | ↓ loss |
| Livestock health records | Vet-tech | Enables livestock trade |
| Farm machinery booking | Equipment marketplace | ↑ mechanisation (currently 5.7% index) |
| Coffee traceability | Export-tech | EUDR compliance |
| Agricultural insurance | Insurtech | Risk transfer |
| Rural savings groups | Fintech | Financial inclusion |
| Market price analytics | Media/research | Transparency |

### Success metric
**≥20% of GMV originates from third-party applications** by end of Phase 4.

---

## Phase 5 — Full ecosystem (Months 69–84)

### Objective
Integrate with **government systems and public digital infrastructure** so the platform is a national
utility rather than a private marketplace.

### Integration targets

| System | Integration | Purpose |
|---|---|---|
| **Fayda / NIDP** | Full relying-party status | Identity everywhere |
| **FaydaVerse** | Verification + eSignet | Authentication and signatures |
| **telebirr / EthSwitch** | Full interop; instant settlement | Payments |
| **Ethiopian Customs (ECX/eTrade)** | Export documentation | Coffee and pulse exports |
| **MoA extension system** | Advisory delivery to development agents (50–60k) | Reach |
| **Regional land registries** | Plot verification | Title and collateral |
| **NAFIR** | Credit guarantee / refinance | Rural finance |
| **NBE credit information system** | Reporting | Regulatory compliance |
| **Ministry of Health / Education** | Adjacent services (later) | Super-app breadth |

### What Phase 5 looks like from a farmer's phone

```
   ┌───────────────────────────────────────────┐
   │  USSD  *80#  or  Agent  or  App           │
   ├───────────────────────────────────────────┤
   │  1. Prices today                           │
   │  2. Sell my harvest                        │
   │  3. Buy inputs (cash or credit)            │
   │  4. Ask the agronomist                     │
   │  5. My loans and payments                  │
   │  6. Insurance                              │
   │  7. Government services (permits, vouchers)│
   │  8. My ID and records                      │
   │  9. Transport my goods                     │
   │ 10. Weather                                │
   └───────────────────────────────────────────┘
```

**That menu is the digital ecosystem.** Each line is a module, each module is a revenue line, and each
line works because identity, payments and data are shared.

---

## The platform maturity model

| Level | Description | Phase | Indicator |
|---|---|---|---|
| **0. Digitising** | Moving paper to screens | — | Data entry |
| **1. Transacting** | Real money moves through the system | 1 | Settled transactions |
| **2. Serving** | Multiple services on one relationship | 2 | Attach rate |
| **3. Scaling** | Replicable operations across regions | 3 | Regional P&L |
| **4. Opening** | Third parties build on the platform | 4 | % GMV from 3rd parties |
| **5. Embedding** | Government and finance depend on it | 5 | Share of national agri trade |

---

## What "ecosystem" actually requires (and most platforms lack)

| Requirement | Why it is rare |
|---|---|
| A **stable, documented API** for 3+ years | Requires engineering discipline and backwards compatibility |
| **Trusted identity** for all participants | Requires national ID integration |
| **Instant, cheap settlement** | Requires payment rail partnerships |
| **A large enough user base** to attract developers | Requires 5 years of growth |
| **Neutral governance** — not competing with your own developers | Requires commercial restraint |
| **Legal clarity** on data sharing | Requires regulation and consent |
| **Capital to operate for years without profit** | Requires patient investors |

**The last one is the reason most ecosystems in Africa have not happened.** Ecosystems are a public
good with a private cost, and only patient capital or a state actor can absorb that.

---

## Governance at ecosystem scale

Once the platform is infrastructure, its governance becomes a public-policy question:

| Issue | Options | Recommendation |
|---|---|---|
| Data ownership | Platform / farmers / state / shared | Farmers own; platform is custodian; state has aggregate access |
| Access pricing | Market / regulated / free | Cost-based for public-good APIs; market for commercial |
| Interoperability | Proprietary / open standard | Open standard, published |
| Dispute adjudication | Platform / independent / regulator | Independent panel with platform funding |
| Market power | Unregulated / regulated | Accept regulatory oversight of access terms |
| Continuity | Private only | Public-interest continuity plan (escrow of code, open-source fallback) |

**The continuity plan matters:** if the platform holds a national dataset and fails, the state must be
able to keep it running. Committing to a code escrow and an open-source fallback builds the trust that
makes Phase 5 possible.

---

## Timeline reality check

| Claim | Reality |
|---|---|
| "Digital ecosystem in 3 years" | Impossible. You get a pilot and a product |
| "National coverage in 5 years" | Possible for transactions; not for full services |
| "Ecosystem in 7 years" | Achievable with good execution and stable conditions |
| "Ecosystem in 10 years" | More likely, and comparable to India (UPI 2016→scale 2020), Kenya (M-Pesa 2007→ubiquity 2015), Estonia (X-Road 2001→maturity 2010) |

**Every real example took 8–12 years.** Any plan that promises otherwise is selling a slide, not an
ecosystem.

---

## The end state, described plainly

A farmer in Bale checks prices on USSD, sells 40 quintals of wheat at a price discovered by auction,
gets paid the same day into her wallet, has her input loan deducted automatically, receives an
insurance payout for a dry spell, buys certified seed through her cooperative agent, and sees her
transaction history presented as a credit record that three banks accept.

None of that requires her to own a smartphone, read English, or visit a bank.

**That is what success looks like.** Everything in this repository is organised around delivering it.
