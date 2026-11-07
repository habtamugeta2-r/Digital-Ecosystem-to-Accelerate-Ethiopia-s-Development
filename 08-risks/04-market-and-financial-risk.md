# 08.4 · Market and Financial Risk

*Part of [08 · Risks](README.md)*

---

## 1. The demand risk (the most fundamental)

**Question: will Ethiopian smallholders actually transact through a digital platform at a rate that
produces a viable business?**

Honest answer: **unknown**. No platform has done it in Ethiopia at scale. Lersha has ~400,000 registered
farmers but primarily in input supply, not market-matched trade.telelmi/Agri-GO and similar are small.

| Evidence for | Evidence against |
|---|---|
| Farmers adopt mobile money rapidly when useful (telebirr 60 m users) | Few have used e-commerce (1% of adults bought online) |
| Price opacity is a real, felt pain | Traders provide credit, transport and immediacy that platforms don't |
| Cooperative aggregation already exists | Cooperatives are weak and politically mediated |
| Lersha shows 400k+ farmers will register for agricultural services | Registration ≠ transaction |
| Cash crops (coffee) have clear traceability-driven demand | Staples are low-margin and price-sensitive |

**The honest position:** demand is a **hypothesis to be tested in the pilot**, with a hard kill criterion
(net price gain <3% → stop). Presenting it as a certainty would be dishonest.

---

## 2. Financial risks

| # | Risk | L | I | Score | Mitigation |
|---|---|---|---|---|---|
| F1 | **Under-funded before break-even** | 3 | 5 | 🔴 15 | Raise 2× modelled need; staged tranches; flex cost base |
| F2 | **Birr depreciation >40%/yr** | 3 | 4 | 🟠 12 | Local cost base; local hosting; quarterly repricing |
| F3 | Inflation >25% erodes fixed fees | 4 | 3 | 🟠 12 | Index fees to CPI; review quarterly |
| F4 | Credit losses exceed provisioning | 3 | 5 | 🔴 15 | First-loss cover; diversification; stop rule |
| F5 | Programme payment delays | 4 | 3 | 🟠 12 | Milestone billing; revolver; 3+ clients |
| F6 | FX shortage blocks input imports | 4 | 4 | 🔴 16 | Local suppliers; no import risk on platform; supplier diversification |
| F7 | Interest rate rises | 3 | 2 | 🟡 6 | Minimal debt |
| F8 | Investor sentiment for African tech falls | 4 | 3 | 🟠 12 | DFI focus; revenue-based financing; grants |

---

## 3. The FX problem in detail

The birr has depreciated substantially since the 2024 float (to ~ETB 161/USD by mid-2026).

### What it does to the platform

| Cost line | FX exposure | Annual cost at ETB 10 m baseline |
|---|---|---|
| Cloud hosting (if AWS/Azure) | 100% USD | ETB 10 m → ETB 14 m at +40% |
| SMS/USSD (local operators) | 0% (birr) | No change |
| Salaries | 0% (mostly) | Some senior roles USD-linked |
| FaydaVerse verification | Partly USD | Moderate |
| Software licences | 100% USD | Moderate |

**Design response:**
- **Ethiopian hosting** for primary systems (also a data-sovereignty and regulatory advantage).
- Minimal foreign SaaS; prefer open-source self-hosted.
- Pay senior staff in birr where possible; budget a USD-linked allowance only where necessary.
- Price services in birr and review quarterly.

### What it does to the *value* proposition (the upside)

A depreciating birr makes Ethiopian agricultural exports cheaper and more competitive. Coffee, sesame
and pulses earn more dollars per unit — which increases exporter willingness to pay for traceability and
supply assurance. **The FX risk is also an export opportunity.**

---

## 4. The margin problem

| Reality | Implication |
|---|---|
| 1.5% commission on a 30-tonne grain trade = ETB 2,520 | Fixed costs must be very low |
| Agent takes 25% of that | Platform keeps ETB 1,890 |
| Payment costs, support, guarantee provision consume ~60% | Contribution ~ETB 800 per trade |
| Need ~190,000 trades/year to cover ETB 150 m fixed cost | At 3 trades/farmer, that is ~63,000 farmers |

**The margin is thin because Ethiopian farm-gate prices are low in dollar terms.** This is structural.

**The three ways out:**

1. **Higher-value commodities** (coffee at ETB 400+/kg vs. maize at ETB 28/kg).
2. **Attach finance** (origination fees are much higher margin than transaction fees).
3. **Programme contracts** (fixed fees per beneficiary, not basis points).

**The plan uses all three.** A platform that relies only on transaction fees will not be viable.

---

## 5. Competitive risk

| Competitor type | Threat | Response |
|---|---|---|
| **State platform** | 🔴 Severe | Partner; differentiate on finance and speed |
| **Telco agri-service** | 🟠 High | Be the application layer on their rail |
| **Lersha-style input platform** | 🟠 High | Partner on inputs; compete on output market |
| **Bank-led farmer lending** | 🟡 Medium | Be their origination channel |
| **Trader networks** | 🟡 Medium | Recruit them |
| **International agritech** | 🟡 Medium | Local relationships are the defence |
| **NGO-funded free platform** | 🟠 High | Distorts the market; wait for funding cycle to end |

**The NGO risk is under-appreciated:** a well-funded donor platform offering free services can make a
commercial platform look expensive and take the market, then disappear when the grant ends. The response
is to partner where possible and to differentiate on reliability and finance.

---

## 6. Funding risk

| Scenario | Effect | Response |
|---|---|---|
| Seed round fails | Cannot launch | Reduce scope to 1 region; grants; revenue-based finance |
| Series A fails | Cannot scale beyond Phase 2 | Focus on profitability at 2 regions |
| Investor demands faster growth | Pressure to scale before gates | Hold the line; gates are contractual |
| Grant funding ends abruptly | Public-good functions cut | Separate P&L; commercial revenue covers core |
| DFI due diligence takes 12 months | Cash crunch | Bridge financing; smaller round |

**The most dangerous funding risk is not failing to raise — it is raising too much too early**, which
allows the team to avoid the hard decisions about unit economics for two years.

---

## 7. Pricing and bargaining risk

| Risk | Mechanism | Mitigation |
|---|---|---|
| Government sets a floor price | Platform cannot earn a spread | Fee per transaction, not margin on price |
| Buyer cartel | Bids converge below market | Publish bid dispersion; recruit more buyers |
| Trader retaliation | Traders refuse to sell to platform buyers | Recruit traders as platform buyers |
| Cooperatives demand higher share | Margin compressed | Equity + revenue share structure |
| Agents demand higher commission | Agent cost rises | Tie commission to volume and quality |

---

## 8. The market risk dashboard

Track monthly:

| Indicator | Green | Amber | Red |
|---|---|---|---|
| Net price gain to farmer | ≥8% | 5–8% | <5% |
| Repeat rate | ≥50% | 30–50% | <30% |
| Blended take rate | ≥1.7% | 1.3–1.7% | <1.3% |
| Contribution margin | ≥+0.5% | 0 to +0.5% | <0 |
| Buyer concentration | <30% top buyer | 30–50% | >50% |
| Agent income | ≥ETB 4,000/mo | 2,500–4,000 | <2,500 |
| Dispute rate | ≤1.5% | 1.5–3% | >3% |

**If three or more are red for two consecutive months, the model needs restructuring**, not more
marketing.

---

## 9. The most honest statement in this document

The platform's financial model has an uncomfortable property: **it works well only at scale, and it can
only reach scale if the unit economics work at small scale.** That is the definition of a hard business.

The way through is not to assume the numbers work, but to **test them cheaply and early** — which is
what the pilot gates are for. If the pilot shows a 5% net price gain and a 40% repeat rate, the model is
plausible. If it shows 2% and 15%, no amount of capital will fix it.

**The pilot is the investment thesis. Everything else is elaboration.**
