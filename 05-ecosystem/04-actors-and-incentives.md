# 05.4 · Actors and Incentives

*Part of [05 · Proposed ecosystem](README.md)*

A platform works only if every participant is better off **staying** than leaving. This file states each
actor's costs, benefits, switching costs and reasons to defect — and what the platform must do about
each.

---

## 1. The actor map

| Actor | Count | Current pain | Platform benefit | Switch cost | Defection risk |
|---|---|---|---|---|---|
| Smallholder farmer | 12–15 m households | Blind selling, losses, no credit | Higher price, less loss, credit | Low | **High** (side-selling) |
| Cooperative | ~30,000 | Weak bargaining, manual records | Volume, revenue share, credit for members | Medium | Medium |
| Village trader / aggregator | ~100,000+ | Cash risk, capital constraint | Finance, verified suppliers, larger volumes | Medium | **Very high** (displaced) |
| Miller / processor | thousands | Unreliable supply | Contracted, graded supply | Medium | Low once contracted |
| Exporter | ~1,000+ licensed | Traceability, quality | EUDR-compliant trace, price premium | High | Low |
| Transporter / driver | ~100,000 | Empty backhauls, cash risk | Higher utilisation, guaranteed payment | Low | Medium |
| Agent | thousands | Thin mobile money commissions | Multiple revenue streams | High (device, stock) | Low |
| Bank / MFI | ~30 banks, ~40 MFIs | No rural data or reach | Verified borrowers, origination | High | Low |
| Insurer | ~18 insurers | Distribution cost, basis risk | Plot data, cheap delivery | Medium | Low |
| Government (MoA/ATI/NBE) | — | Leakage, no last mile | Targeting, data, delivery | High | Medium |
| Donor / NGO | many | M&E cost, diversion risk | Verified delivery, real-time data | Low | Medium |
| FaydaVerse | — | Needs relying parties to prove value | Usage, integration | — | Low |
| Ethio Telecom / Safaricom | 2 | Need transaction volume | GMV volume | — | Low |
| Platform | 1 | — | Fees, data, position | — | — |

---

## 2. The farmer's calculus, stated precisely

A farmer deciding whether to sell through the platform weighs:

| Factor | Weight | Platform must deliver |
|---|---|---|
| Price vs. the trader's offer | **Highest** | ≥5–15% net gain after fees |
| Certainty of payment | Very high | Escrow + guarantee |
| Speed of payment | High | Same-day or next-day |
| Effort required | High | Agent does the work; farmer makes one call |
| Trust in the counterparty | Very high | Verified buyer, cooperative endorsement |
| Access to credit | High | Pre-harvest input credit |
| Emergency cash | High | Ability to sell quickly, any quantity |
| Social obligation to a trader | Medium | Do not force a break; allow partial sales |

**Therefore the winning offer is:** *"Sell as much or as little as you want, at a published price,
with the money already held for you, and get credit before next season."* — not *"use our app."*

**The most common mistake:** assuming price is the only factor. Certainty, speed and credit usually
outweigh an extra 5%.

---

## 3. The incumbent trader: displace or recruit?

The village trader is the platform's most important design problem.

| Option | Consequence |
|---|---|
| **Displace** | The trader has relationships, credit leverage and physical presence. Displacement triggers resistance, side-selling and local political opposition |
| **Recruit** | Traders become platform buyers/agents, gaining finance and verified supply. Their working capital need (their biggest constraint) is solved |
| **Bypass** | Work only with cooperatives. Slower, but politically cleaner |

**Recommendation: recruit.** The trader's core constraint is **working capital** — most operate on
thin capital and high turnaround. A platform that offers verified supply, escrow settlement and
working-capital credit gives them something they cannot get elsewhere. In exchange, they bring
relationships and local knowledge the platform cannot build.

**But:** require transparency. A recruited trader must transact on published terms, not extract a
hidden spread. This is enforceable because the farmer sees the price and the fee.

---

## 4. The cooperative: partner, not channel

| Cooperative reality | Implication |
|---|---|
| ~30,000 exist; most are weak, undercapitalised, poorly governed | Do not assume capability; build it |
| Some are politically captured | Screen via audited unions and member verification |
| They control member lists and aggregation | The fastest route to organised supply |
| Members trust them more than banks or government | Borrow that trust |
| Many have buildings, scales and storage | Physical infrastructure the platform needs |

**Recommended structure:** cooperatives become **platform shareholders** (an equity tranche), receive
a share of regional fee revenue, and nominate board or regional committee members. This converts the
relationship from extraction to ownership and is the most durable defence against political and
community opposition.

---

## 5. The agent: the unit economics that decide the business

| Revenue line | Monthly amount (illustrative ⚪) |
|---|---|
| Mobile money float commission | ETB 200–600 |
| Listing and onboarding commission | ETB 300–1,200 |
| Logistics dispatch commission | ETB 200–800 |
| Input sales margin | ETB 500–3,000 (seasonal) |
| Advisory session fee (if any) | ETB 0–200 |
| **Total** | **ETB 1,200–5,800 (US$8–40)** |

Compare against a rural household's cash needs. An agent earning ETB 3,000/month is meaningfully
employed. The same agent earning only mobile money float (ETB 400) will not maintain the device,
the data, the travel or the attention.

**Therefore: agent viability is a design constraint, not an afterthought.** The platform must
deliberately bundle at least three revenue streams per agent, and should actively help agents build
input-sales businesses.

**Agent quality controls:** Fayda identity, cooperative endorsement, security deposit, device binding,
transaction limits scaled by track record, independent SMS to every affected farmer, commission
clawback for fraud.

---

## 6. Buyer incentives and the liquidity problem

Buyers join for **reliable supply and price transparency**. They stay for **credit and traceability**.

| Buyer type | Primary motivation | Secondary |
|---|---|---|
| Miller / processor | Contracted volume; consistent grade | Working capital |
| Exporter | Traceability (EUDR), specialty premium | Volume assurance |
| Wholesaler | Price discovery, lower search cost | Credit |
| Institutional buyer (WFP, schools, army) | Verified supply, food safety | Delivery reliability |
| Retail chain | Consistent quality | Cold chain |

**Bootstrapping liquidity:** the platform must guarantee demand before supply. Practical approach:
1. Sign **3–5 anchor buyers** with committed purchase volumes before farmer onboarding.
2. Onboard **2–3 cooperatives** with committed member supply.
3. Run the first season as a **matched, manually-operated** trading desk with software assistance.
4. Automate once patterns are known.

This is not glamorous, but it is how every marketplace begins.

---

## 7. The bank's calculus

| Bank concern | Platform answer |
|---|---|
| "No collateral" | Cash-flow lending on verified history; first-loss cover from NAFIR/IFC facilities |
| "No rural presence" | Platform originates and services; bank only approves and books |
| "High cost per loan" | Digital origination at a fraction of branch cost |
| "Covariate risk" | Portfolio across regions and commodities; index insurance |
| "Regulatory uncertainty" | Platform acts as LSP; bank holds the licence and the credit risk |
| "Data protection" | Query-based consent; no bulk transfer |
| "Reputation risk" | Transparent pricing; no punitive collections; published dispute outcomes |

**The pitch to a bank:** *"We will bring you pre-verified, pre-scored borrowers with a two-season
trading history and an automatic repayment mechanism at settlement. You will not need a branch, a
loan officer visit, or a collateral valuation."*

---

## 8. The government's calculus

| Government concern | Platform answer |
|---|---|
| Control of a strategic sector | Cooperative equity; data transparency; programme partnership; no exclusivity |
| Tax revenue | Every transaction is recorded; digital trail increases formality |
| Food security | Faster movement from surplus to deficit areas; lower losses |
| Political credit | Visible farmer income gains; programme delivery |
| Data sovereignty | Ethiopian hosting; government access under defined terms |
| Precedent for private infrastructure | Position as an implementation partner for DAR, not a rival |
| Failure risk | Light-asset; can be suspended region by region |

---

## 9. Incentive alignment summary

| Pair | Alignment | Conflict | Resolution |
|---|---|---|---|
| Farmer ↔ Buyer | Both want a completed transaction | Price | Transparent bidding; farmer sets floor |
| Farmer ↔ Trader | Trader needs supply; farmer needs credit and cash | Trader's spread | Recruit traders; publish prices and fees |
| Cooperative ↔ Platform | Both want member income | Fee share | Equity + revenue share |
| Agent ↔ Platform | Both earn from volume | Commission levels | Bundled income; published rate card |
| Bank ↔ Platform | Both want good loans | Risk appetite | First-loss cover; phased scaling |
| Government ↔ Platform | Both want farmer income and food security | Control and data | Cooperative equity; programme contracts |
| Platform ↔ Incumbent telco | Both want volume | Ownership of the customer | Partner as rail; own the agri relationship |

---

## The three incentive failures that sink agricultural platforms

1. **The agent is not paid enough to care.** Fix: three bundled revenue streams.
2. **The buyer is not locked in, so supply is not assured.** Fix: forward contracts with escrow and
   penalties; traceability that the buyer needs.
3. **The farmer can side-sell after being matched.** Fix: escrow on first transactions, credit access
   tied to platform history, and a guarantee that makes the platform safer than the alternative.

Every one of these is a **design problem**, not a market failure to be explained away.
