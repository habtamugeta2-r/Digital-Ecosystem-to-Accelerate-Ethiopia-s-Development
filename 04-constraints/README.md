# 04 · Constraints

*What any digital intervention in Ethiopia must work within*

The constraints in this section are not objections to the strategy. They are the **design
specification**. Each one is paired with the specific product or business decision it forces.

---

## Files in this section

| File | Constraint | Design consequence |
|---|---|---|
| [`01-connectivity-power-devices.md`](01-connectivity-power-devices.md) | Connectivity, electricity, devices, literacy | USSD/IVR-first; agent intermediation; offline-first |
| [`02-payments-and-currency.md`](02-payments-and-currency.md) | Payment rails, FX scarcity, capital controls | Multi-rail; birr-denominated; no card dependency |
| [`03-regulation-and-licensing.md`](03-regulation-and-licensing.md) | NBE licensing, data protection, trade rules | Licence clarity before launch; privacy-by-design |
| [`04-language-and-literacy.md`](04-language-and-literacy.md) | 80+ languages, 90% learning poverty | Five languages at MVP; voice-first; iconography |
| [`05-trust-and-culture.md`](05-trust-and-culture.md) | Cash culture, fraud fear, conflict history | Escrow, guarantees, cooperative anchoring |
| [`06-market-size-and-competition.md`](06-market-size-and-competition.md) | Small formal market, state incumbents | Basis-point economics; partner posture |
| [`07-security-and-fraud.md`](07-security-and-fraud.md) | Cyber, fraud, insider risk | Controls, monitoring, insurance |

---

## The constraint table

| # | Constraint | Reality (2025–26) | Design decision |
|---|---|---|---|
| 1 | Internet penetration | **21.7%** of population; ~9% rural | USSD, IVR, SMS as primary channels |
| 2 | Mobile phone ownership | **58%** of adults | Agent intermediation; never require a personal device |
| 3 | Smartphone penetration | ~30% (target 70% by 2030) | No smartphone-only features |
| 4 | Electricity at Tier 1+ | **44%** | Battery/solar-capable agent devices; short-session flows |
| 5 | Adult literacy | 90% learning poverty among 10-year-olds | Voice interfaces; icons; local languages |
| 6 | Payment rails | telebirr 60.6 m, M-Pesa 5.2 m, EthSwitch live | Multi-rail orchestration; never single-wallet |
| 7 | Online purchase behaviour | **1%** of adults bought online digitally | Cash-on-delivery and agent cash-in as first-class |
| 8 | FX availability | Birr 57→161/USD; rationed FX | No imported hardware dependency; birr P&L |
| 9 | Inflation | 12–16% | Monthly fee re-pricing; avoid long fixed-price contracts |
| 10 | Capital controls | Repatriation requires approval | Local incorporation; plan exit routes early |
| 11 | Payment licensing | Unclear for escrow/marketplace | Written NBE position before launch |
| 12 | Data localisation | Restricted cross-border transfer | Ethiopia-hosted; consent architecture |
| 13 | Trade policy volatility | Price caps and export bans recur | Commodity-level suspension capability |
| 14 | Language diversity | 80+ languages; 5 supported by 8028 | Launch in 5; add by region |
| 15 | Conflict | Active in Tigray/Amhara/Oromia; 3.3 m IDPs | Geographic diversification; light assets |
| 16 | Corruption | CPI 38/100 | Automate discretion; publish prices; audit trails |
| 17 | Formal market size | GDP ~US$210 bn, formal retail small | Basis-point fees on large volume |
| 18 | Incumbent state players | telebirr, Ethio Telecom, state banks | Partner posture; don't compete on rails |
| 19 | Talent | Strong engineering, scarce agronomy/product | Hire agronomists early; train product locally |
| 20 | Security | Fraud, kidnapping risk in some regions | Fraud controls; field-staff safety policy |

---

## The three constraints that most often kill projects

### Constraint A: The device assumption

Every failed Ethiopian digital agriculture project shares one feature: **it assumed the farmer has a
smartphone and can read.** With 58% phone ownership, ~30% smartphone penetration and 90% learning
poverty, an app-based direct-to-farmer product addresses perhaps **10–15% of the target population** —
and those are the least poor, least rural, least in need.

**Response:** the farmer-facing product is a **phone call, an SMS, and a person at the cooperative.**
The app is for agents, buyers, transporters and staff. This inverts the usual product priority and is
the single most important design decision in the dossier.

### Constraint B: The licensing gap

Ethiopia's regulatory framework is modern and clear on **identity** and **payments**, but silent or
ambiguous on:
- whether a marketplace holding funds in escrow needs a payment-instrument issuer licence;
- whether a platform can be an agent for multiple wallets simultaneously;
- how transaction data can be shared with lenders under Proclamation 1321/2024;
- whether an agricultural platform can act as a lending service provider.

**Response:** obtain written NBE positions on all four before building. Structure the entity so that
regulated activity sits inside a licensed partner and the platform provides technology and
origination. Budget 3–6 months.

### Constraint C: The unit-economics trap

A rural agricultural transaction is small, infrequent and expensive to serve. Agent commissions,
SMS costs, cash handling, transport and support can easily exceed a 2% take rate.

**Response:** three structural choices —
1. **Bulk B2B transactions** (ETB 750,000 per truckload) rather than retail orders;
2. **Bundled revenue per farmer relationship** (marketplace + finance + inputs + logistics + data),
   not one fee stream;
3. **Cooperative-level** rather than individual-farmer operations for anything expensive.

---

## What is *not* a constraint (common misconceptions)

| Claim | Reality |
|---|---|
| "There's no internet in rural Ethiopia" | 82% 4G population coverage exists; usage is the problem, not coverage |
| "Farmers don't have phones" | 58% of adults do; and agents cover the rest |
| "Mobile money doesn't work here" | 60.6 m telebirr users; ETB 2.38 trn processed in one year |
| "There's no digital ID" | 53.4 m Fayda registrations; mandated for banking by end-2026 |
| "E-commerce is booming" | 1% of adults have bought online with a digital payment |
| "The government blocks fintech" | It has opened telecom, mobile money, retail and payments since 2021; the constraints are capacity and clarity, not prohibition |
| "Agriculture is too informal to digitise" | 30,000+ cooperatives, an ECX with grading and e-receipts, and a government digital agriculture roadmap exist |

---

## Read next

Each constraint file ends with a "decisions forced" table that feeds directly into
[`../05-ecosystem/`](../05-ecosystem/README.md).
