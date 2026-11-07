# 09.1 · The Recommendation

*Part of [09 · Recommendation](README.md)*

---

## 1. The problem, stated precisely

Ethiopia has 12–15 million smallholder households producing over 30 million tonnes of cereals a year.
Almost none of that production is **recorded**, **verified** or **connected to finance**.

| Fact | Source |
|---|---|
| Agriculture ~32–35% of GDP, ~60% of employment | World Bank / NBE |
| Cereal yield ~2,632 kg/ha (vs. 4,000+ achievable) | World Bank / FAO |
| Post-harvest losses 15–25% (cereals), 30–50% (horticulture) | MoA / FAO |
| **Only ~2% of ETB 2.58 trn agricultural credit demand is met** | Addis Standard / NBE |
| Banks lend ~8% of portfolios to agriculture; MFIs ~18% | NBE |
| <20% of smallholders have any financial service | IFC |
| Land is not usable as collateral for most smallholders | Legal/tenure |
| ~49% of adults have an account; 21% made a digital payment | Global Findex |
| 58% of adults own a mobile phone; ~9% of rural adults use the internet | DataReportal / GSMA |

**The core problem is not liquidity, technology or demand. It is the absence of a verified record of
who produced what, at what quality, and whether they paid.**

Without that record:
- Lenders cannot underwrite.
- Buyers cannot contract.
- Insurers cannot price.
- Government cannot target.
- Farmers cannot prove anything about themselves.

**Every other problem in Ethiopian agriculture — low yields, post-harvest loss, thin markets, exclusion
from finance — is downstream of that missing record.**

---

## 2. What the platform is

**A transaction system of record for Ethiopian agriculture.**

```
        ┌─────────────────────────────────────────────────────┐
        │   WHAT THE PLATFORM ACTUALLY IS                     │
        │                                                      │
        │   An identity-verified, escrow-settled, auditable    │
        │   record of every agricultural transaction,          │
        │   accessible by USSD to anyone, and open by API      │
        │   to anyone who needs it.                            │
        └─────────────────────────────────────────────────────┘
```

Everything else — the marketplace, the advisory, the logistics, the credit — is either a **way to
generate transactions** or a **way to monetise the record**.

---

## 3. Why agriculture, and why now

### Why agriculture

| Criterion | Assessment |
|---|---|
| **Size** | 32–35% of GDP; 60% of employment; 30+ Mt of cereals |
| **Pain** | 15–25% post-harvest loss; 10–30% intermediary spread; zero credit access |
| **Frequency** | 2–4 transactions per farmer per season |
| **Value per transaction** | ETB 28,000–46,000 — high enough for basis-point fees |
| **Data generation** | Every trade produces credit-relevant data |
| **Monetisation** | Transaction fees + finance + inputs + programmes |
| **Competition** | No dominant digital player |
| **Policy alignment** | DAR 2032, ATI, NAFIR, Digital Ethiopia 2030 |

**No other sector combines all eight.**

### Why now

| Rail | Status (2026) | What it enables |
|---|---|---|
| **Fayda** | 53.4 m registered, ~200k/day, verification at US$0.05–0.10 | Identity for every farmer |
| **telebirr** | 60.6 m registered, 320k agents, 310k merchants | Payment reach |
| **M-Pesa** | 5.2 m active, 30,700+ merchants | Second rail; redundancy |
| **EthSwitch** | Interoperability live | Wallet-to-bank settlement |
| **Ethio Telecom 4G** | 82.23% population coverage | Connectivity (partial) |
| **NDPS 2026–2030** | 54 → 275 transactions/adult; 70% smartphone by 2030 | Policy commitment |
| **Digital Ethiopia 2030** | Adopted Dec 2025 | National strategy alignment |
| **FaydaVerse** | Sandbox, eSignet, verification API | Developer infrastructure |

**Three years ago this platform was impossible. In three years it may be too late.**

---

## 4. Why this design and not another

### Why agent-anchored, not app-first

| Fact | Consequence |
|---|---|
| 58% of adults own a mobile phone; 29.5 m internet users (21.7%) | An app excludes 70%+ of farmers |
| ~9% of rural adults use the internet | An app excludes almost all of the target market |
| 44% have Tier-1 electricity access | Smartphones are not reliably chargeable |
| Literacy ~50–55% | Text menus exclude half the market |
| 320,000 telebirr agents already exist | The agent network is already built — use it |

**An app-first platform in Ethiopia would serve the top 10% of farmers — the ones who need it least.**

### Why escrow, not direct payment

Without escrow, the platform is a directory: buyers and farmers exchange numbers and transact off-
platform. Escrow is what makes the platform **structurally necessary** rather than merely convenient.

### Why one commodity and one region

| Reason | Explanation |
|---|---|
| Trust is local | A farmer in Arsi does not care about a platform that also works in Sidama |
| Grading is commodity-specific | Teff grades are not maize grades |
| Buyers are commodity-specific | Millers buy wheat; exporters buy coffee |
| Operations are geography-specific | Roads, warehouses, agents, cooperatives |
| Learning is faster | One region means one set of problems at a time |

### Why the platform should not issue a wallet

| Reason | Explanation |
|---|---|
| telebirr has 60.6 m users | Competing is futile |
| M-Pesa has 5.2 m active | The market is already served |
| Wallet licensing is capital-intensive | PSI minimum capital is prohibitive for a startup |
| Wallets are a commodity | The platform's value is the transaction record, not the balance |

**Be the merchant, not the wallet.**

### Why the platform should not lend from its own balance sheet

| Reason | Explanation |
|---|---|
| No lending licence | NBE requirements are substantial |
| Credit risk on a young balance sheet | Fatal if defaults spike |
| Capital efficiency | Origination fees without credit risk is a better business |
| DFI first-loss facilities exist | They absorb the risk the platform cannot |

**Be the originator, not the lender — until the data justifies more.**

---

## 5. The strategic logic in one diagram

```
        RAILS BUILT BY OTHERS              APPLICATION LAYER
        ─────────────────────              ─────────────────
        Fayda (identity)          ──►      Farmer / agent / buyer identity
        telebirr, M-Pesa (payment)──►      Escrow settlement
        EthSwitch (interop)       ──►      Wallet-to-bank flows
        Ethio Telecom (network)   ──►      USSD / SMS / IVR channels
        FaydaVerse (verification) ──►      KYC and signatures
        EthioMet (weather)        ──►      Advisory
        ATI / 8028 (content)      ──►      Market prices
                                            │
                                            ▼
                              ┌─────────────────────────────┐
                              │  THE PLATFORM (the gap)     │
                              │  Verified transaction ledger │
                              │  Consent registry            │
                              │  Credit history              │
                              └──────────────┬──────────────┘
                                             │
                    ┌────────────────────────┼────────────────────────┐
                    ▼                        ▼                        ▼
              Marketplace              Embedded finance         Government
              Advisory                 Insurance                programmes
              Logistics                Inputs                   Data products
```

**Ethiopia has built the rails. It has not built the agricultural application layer.** That is the gap,
and it is a business, not a public service — because whoever fills it accumulates the data.

---

## 6. The evidence that this can work

| Evidence | What it shows |
|---|---|
| **M-Pesa (Kenya)** | 40.99 m active users; KSh 41.68 trn/yr (2.4× GDP); 57.8% of transactions free — rails create ecosystems |
| **India UPI** | 21.7 bn transactions/month; built on Aadhaar identity — identity + payments enables everything |
| **Rwanda Irembo** | 240 services, 3,000+ agents, >5 m applications, 45% pay digitally — agent-assisted digital government works |
| **Estonia X-Road** | ~2% of GDP saved; 2001→maturity in ~10 years — ecosystem timelines |
| **Lersha (Ethiopia)** | 400,000+ farmers, 4,000+ agents, US$1 m IFC investment — Ethiopian farmers do use digital agri services |
| **8028 (Ethiopia)** | ~7 m users, 67 m calls — USSD works at national scale in Ethiopia |
| **telebirr** | 60.59 m users in ~5 years — adoption can be extremely fast when the value is clear |
| **DAR 2032** | 30 m farmers, +8% income, US$90 m programme — policy is aligned |

**The counter-evidence:** Jumia lost money for 11 years; most African agri-platforms stayed small;
Ethiopia's e-commerce sector is tiny (58% of platforms under US$10k revenue). **The difference is
whether the business is built around a transaction that must happen (a harvest sale) or one that might
happen (an online purchase).**

---

## 7. What must be true

| Assumption | Confidence | Test |
|---|---|---|
| Farmers will switch to a platform for a ≥5% net price gain | 🟡 Medium | Pilot cohort |
| Escrow is legally achievable with a bank/PSI partner | 🟢 High | NBE correspondence |
| Agents can earn a living from 3 bundled services | 🟡 Medium | Agent income tracking |
| Lenders will lend on 2-season ledger data | 🟢 High (with first-loss) | Lender term sheet |
| Take rate of 1.5% is sustainable | 🟡 Medium | Pilot price tests |
| Government will pay for programme delivery | 🟠 Medium | First contract |
| The security situation permits operations in 3+ regions | 🟠 Medium | Regional assessment |
| Capital is available for a 7-year build | 🟠 Medium | Fundraising |

**Four of eight are medium or lower.** The recommendation is therefore: **proceed, but proceed as an
experiment with explicit stop conditions** — not as a certainty.

---

## 8. The recommendation, in five sentences

1. **Build the transaction layer for Ethiopian agriculture**, starting with one commodity in one region,
   because the missing record is the root cause of everything else.
2. **Anchor it in agents and USSD/IVR**, because most Ethiopian farmers will not have a smartphone or
   reliable internet for a decade.
3. **Settle in escrow** through a licensed institution, because that is what makes the platform
   structurally necessary rather than a directory.
4. **Treat the verified ledger as the asset**, and monetise it through credit, insurance, inputs and
   programme delivery — not through transaction fees alone.
5. **Partner with the state rather than compete**, because the state controls the rails, the
   cooperatives and the policy environment, and a partner is harder to shut down than a rival.

---

## 9. What success looks like in 2032

| Metric | Target |
|---|---|
| Active farmers | 400,000–750,000 |
| Cooperatives | 200–400 |
| Agents | 1,500–3,000 |
| GMV | ETB 25–85 bn |
| Loans originated (cumulative) | ETB 5–10 bn |
| Farmers with a credit record for the first time | 300,000+ |
| Post-harvest loss reduction in platform regions | 5–8 pp |
| Net price gain to participating farmers | 5–10% |
| Regions | 5–7 |
| Third-party developers on the API | 15–40 |

**The most important number is not GMV. It is the number of farmers who, for the first time, have a
verifiable record of what they produced and repaid — because that record is what unlocks everything
else.**

---

## 10. The final judgement

**This is worth attempting.** The market is large, the rails exist, the capital requirement is modest,
and the asset accumulated is not purchasable by competitors.

**It is also genuinely risky.** Conflict, thin margins, farmer behaviour, and policy could each prevent
it. There is no version of this plan where success is likely — only a version where the downside is
bounded and the upside is a national institution.

**That asymmetry is the argument for building it.**
