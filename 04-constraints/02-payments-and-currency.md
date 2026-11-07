# 04.2 · Payments and Currency

*Part of [04 · Constraints](README.md)*

> **The constraint in one line.** The rails are now good; the **currency is not**, and the foreign
> exchange regime shapes every capital decision.

---

## 1. The payment rails, as they actually are

| Rail | Reach | Strength | Limitation |
|---|---|---|---|
| **telebirr** (Ethio Telecom) | 60.59 m registered; 320,000 agents; 310,000 merchants | Universal, USSD-accessible, state-backed | Activation rate lower than registration; agri-specific features thin |
| **M-Pesa Ethiopia** (Safaricom) | 5.2 m active; 30,700+ merchants | Better product design; interoperable since Oct 2025 | 15 m subscriber base, ~59% population coverage |
| **Bank accounts** (CBE, Awash, Dashen, etc.) | 49% of adults | Credit origination, large settlement | Rural branch density low |
| **EthSwitch / EthioPay** | National switch; >1 m P2P/day; mandated interoperable QR | Settlement hub; government payments (UGPP) | Younger infrastructure; merchant acceptance still maturing |
| **Card** (Visa/Mastercard) | Very limited | International | Not a viable retail rail in rural Ethiopia |
| **Cash** | Universal | Trusted, immediate | Theft, shrinkage, no record |

**Interoperability is the decisive change.** M-Pesa's October 2025 integration with EthSwitch connected
it to 15 (now 30+) banks and wallets and to interoperable EthQR merchant payments. Before that, the
market was effectively fragmented between two islands. **An escrow product is now technically
possible; in 2023 it was not.**

---

## 2. The currency problem

| Indicator | Value | Date |
|---|---|---|
| Exchange rate | ~161 birr/USD | Sep 2026 |
| Pre-float rate | ~57 birr/USD | before Jul 2024 |
| Depreciation | ~65% in two years | 2024–26 |
| Inflation (average) | 12–16% | 2025–26 |
| Headline inflation | 15.3% | Jul 2026 |
| FX allocation | Rationed; priority list | ongoing |
| Capital controls | Repatriation requires approval | ongoing |
| Sovereign debt | US$28.9 bn external; in default on Eurobond | 2024–26 |

### What this does to a business model

| Effect | Consequence |
|---|---|
| **Local currency revenue, USD-denominated costs** (cloud, licences, imported hardware) | Gross margin erodes with every depreciation; price in birr but index cloud spend |
| **Inflation** | Fee percentages stay constant in nominal terms but lose real value; re-price monthly |
| **FX rationing** | Imported devices, vehicles and servers require allocation; plan 6–9 month lead times or source locally |
| **Capital controls** | Foreign investors cannot easily repatriate; structure and disclose early |
| **Contract volatility** | Fixed-price multi-year contracts with buyers become loss-making |
| **Reporting** | USD-reported revenue can fall while birr revenue grows — a Jumia-style trap |

**Practical rule:** run the business on **birr revenue and birr costs**, minimise USD cost lines, and
hold minimal float in birr. Every USD obligation is a hedge problem.

---

## 3. Why this actually helps an agricultural marketplace

It sounds paradoxical, but inflation and cash scarcity are **tailwinds** for a transaction platform:

| Condition | Effect on adoption |
|---|---|
| Cash is bulky and risky to move (ETB 2 m for 80 quintals) | Traders prefer digital settlement — a security and shrinkage benefit |
| Prices are volatile | Real-time price information becomes valuable, not decorative |
| Cash shortages at banks | Wallet float is more available than physical cash |
| Import costs rising | Local aggregation and processing become more attractive |
| Export earnings urgent | Traceability and quality premiums become a national priority |
| Fuel payments digitised (ETB 176 bn between Aug 2024 and May 2025) | Compulsory digitisation normalised digital payment at the pump — and at the checkpoint |

The last point matters operationally: **the mandatory digitisation of fuel payments created a
population of digitised truckers.** A logistics module can build on that.

---

## 4. Payment architecture for the platform

```
                        ┌──────────────────────────────┐
                        │   PAYMENT ORCHESTRATION      │
                        │   (routing, escrow, split)   │
                        └───────────┬──────────────────┘
                                    │
        ┌───────────────┬───────────┼───────────┬───────────────┐
        ▼               ▼           ▼           ▼               ▼
   telebirr        M-Pesa       Bank APIs   EthSwitch      Agent cash
   (wallet)        (wallet)     (CBE etc.)   (instant)      (cash-in/out)
        │               │           │           │               │
        └───────────────┴───────────┴───────────┴───────────────┘
                                    │
                          ┌─────────▼─────────┐
                          │  LICENSED         │
                          │  CUSTODIAN        │
                          │  (bank or PSI)    │
                          └───────────────────┘
```

**Design rules:**
1. **Never hold customer funds without a licence.** Use a licensed custodian (bank or payment
   instrument issuer) for escrow. The platform instructs; it does not custody.
2. **Route dynamically** by cost, speed, recipient wallet preference and success rate.
3. **Cash-in/cash-out is part of the product.** The farmer's money may start and end as cash at an
   agent.
4. **Reconcile daily and expose balances to users via SMS.**
5. **Idempotency and double-entry accounting** from day one — payment bugs destroy trust permanently.

---

## 5. Escrow: the core mechanism, specified

| Element | Specification |
|---|---|
| Trigger | Buyer accepts a listing or bid |
| Funding | Buyer pays into a custodian-held escrow account via wallet/bank |
| Notification | Farmer receives SMS in local language with amount and expected delivery date |
| Delivery | Transporter confirms pickup; buyer or warehouse confirms receipt (photo + geotag + OTP) |
| Release | Funds released to farmer (minus fees) on confirmed acceptance |
| Dispute window | 48–72 hours for quality/quantity dispute |
| Dispute resolution | Platform adjudicates with evidence; reserved funds returned or split |
| Fees | Platform fee + payment fee deducted at release, disclosed upfront |
| Failure modes | Timeout → auto-release or auto-refund per contract terms; both parties notified |

**Regulatory note:** escrow is the feature most likely to require a licence or a custodian
arrangement. Confirm with NBE before building.

---

## 6. Remittances and cross-border

| Element | Status |
|---|---|
| Diaspora remittances | Large and economically significant; largely informal or bank-based |
| Mobile remittance | telebirr and M-Pesa support international remittance corridors |
| PAPSS | Ethiopian non-bank mobile money operators preparing integration; requires NBE Letter of No Objection |
| AfCFTA | Kenya–Ethiopia MoU on cross-border trade facilitation signed |
| FX controls on outbound | Outbound remittances were historically restricted; NDPS 2026–2030 signals opening |
| Opportunity | Diaspora-funded agricultural investment and input purchase is a real, underserved flow |

**The interesting product:** a diaspora customer in Minneapolis pays for a family member's fertiliser
in Bale, with the platform ensuring the input (not cash) is delivered, and the farmer receives a
credit-history entry. This is a genuine wedge for a remittance-linked revenue line — and it is a
better fit than generic wallet-to-wallet remittance.

---

## Decisions forced

| Decision | Choice |
|---|---|
| Custody | Licensed custodian; platform never holds funds |
| Rails | All three (telebirr, M-Pesa, bank) + EthSwitch, from day one |
| Currency | Birr-denominated; minimal birr float; USD costs minimised |
| Pricing | Percentage fees re-set monthly against inflation |
| Cash | Agent cash-in/out supported in every flow |
| Escrow | Custodian-held, delivery-triggered, 48–72 h dispute window |
| Cross-border | Only via licensed partner; PAPSS posture later |
| Reporting | Report in birr for operations, USD for investors, and explain the difference |
