# 09.3 · What Not to Do

*Part of [09 · Recommendation](README.md)*

Explicit exclusions, with reasons. These are as important as the recommendations — they are the
decisions that prevent the project from dissipating its capital and focus.

---

## 1. Do not build a super-app

| Why it is tempting | Why it fails |
|---|---|
| WeChat and Grab did it | They started with **one high-frequency utility** (messaging; ride-hailing) and expanded from a position of daily habit |
| "One app for everything" sounds compelling | Ethiopian farmers do not need "everything" — they need to sell a harvest at a fair price |
| Investors like the narrative | Investors fund traction, not narratives |

**What to do instead:** build one transaction that matters, make it excellent, and let other services
attach to it.

**The test:** can a farmer name the one thing the platform does for them? If the answer is "many things,"
nothing is working.

---

## 2. Do not start with e-commerce

| Fact | Implication |
|---|---|
| Jumia has lost money for 11+ years and exited 6 markets | The model does not work in African markets at scale |
| 58% of Ethiopian e-commerce platforms earn <US$10k revenue | The sector is not a business yet |
| ~1% of Ethiopian adults have bought online digitally | There is no habit to build on |
| Qefira shut down; Buy2Go merged | Consolidation, not growth |
| Ethiopia's e-commerce market size estimates conflict by orders of magnitude (US$29.78 bn vs ~US$71 m) — the data is unreliable | You cannot plan a business on numbers you cannot trust |

**E-commerce may be a Phase 3 addition to the platform. It is not the wedge.**

---

## 3. Do not build a wallet

| Fact | Implication |
|---|---|
| telebirr: 60.59 m registered users, 320k agents | The wallet market is owned |
| M-Pesa: 5.2 m active users, 30,700+ merchants | The second position is owned |
| EthioPay: >1 m P2P transactions/day | The market is functioning |
| PSI licensing requires substantial capital | Prohibitive for a startup |
| Wallets are becoming a commodity (interoperability via EthSwitch) | No margin, no moat |

**Be a merchant/aggregator on the existing rails. Never compete with the rails.**

This is the single most important exclusion. It distinguishes this plan from the many failed attempts to
build a fintech in Ethiopia.

---

## 4. Do not lend from your own balance sheet

| Why not | Detail |
|---|---|
| No lending licence | NBE requirements are substantial |
| Credit risk on a young balance sheet | A single bad season can wipe out the company |
| Capital inefficiency | Every birr of capital lent could originate 5–10 birr of bank lending |
| DFI facilities exist | NAFIR, IFC, and first-loss structures are designed for this |

**Be the originator and servicer. Let banks and MFIs hold the risk.**

---

## 5. Do not build for smartphones

| Fact | Consequence of ignoring it |
|---|---|
| 58% of adults own a mobile phone (not all smartphones) | An app excludes 40%+ |
| 21.7% internet penetration | An app excludes 78% |
| ~9% rural internet use | An app excludes 91% of the target market |
| 44% Tier-1 electricity | Devices are not reliably charged |
| Literacy ~50–55% | Text-based interfaces exclude half |

**USSD, IVR, SMS and agents are permanent infrastructure, not interim measures.**

An app for agents, buyers and staff is fine. An app for farmers is a Phase 3 or later experiment.

---

## 6. Do not build microservices, ML or blockchain first

| Technology | Why not yet |
|---|---|
| **Microservices** | A modular monolith with 5 engineers will out-deliver 12 microservices with the same team. Split only when measurable pain appears |
| **Machine learning** | You have no data. A rules-based scorecard with 10,000 loans outperforms an opaque model and is far easier to defend to a regulator |
| **Blockchain** | A double-entry ledger with an audit log already provides the immutability you need. Blockchain adds complexity, cost and regulatory ambiguity for no benefit |
| **Big data platform** | You have 500 transactions. Use PostgreSQL |
| **AI/LLM features** | Not until the transaction flow works. Chatbots do not solve market access |

**The correct architecture for the first two years is deliberately boring.**

---

## 7. Do not launch nationwide

| Reason | Detail |
|---|---|
| Trust is local | A national brand means nothing in a woreda |
| Operations are geographic | Warehouses, agents, cooperatives, roads |
| Grading is commodity-specific | Teff ≠ maize ≠ coffee |
| Capital is limited | Spread thin = die slowly |
| Learning is slower | More variables, fewer conclusions |

**One commodity, one region, one season. Then the next.**

---

## 8. Do not monetise basic advisory

| Why not | Detail |
|---|---|
| It excludes the poorest | Exactly the people the platform should serve |
| ATI already provides it free | A paid service cannot compete with a free public good |
| It is the acquisition channel | Charging for it destroys the funnel |
| It costs more to collect than it earns | ETB 1.2–2.0 per SMS is a cost, not a revenue line |

**Advisory is free forever. It is monetised indirectly through transactions and data.**

---

## 9. Do not sell individual farmer data

| Why not | Detail |
|---|---|
| Illegal under Proclamation 1321/2024 | Without explicit consent for that purpose |
| Reputationally fatal | One story in the press ends the platform's legitimacy |
| It destroys trust | Farmers will stop transacting if they think they are the product |
| It is not a real business | The value is in aggregate intelligence and credit scoring, not raw data |

**Sell analysis, not rows. Query access with consent, never bulk export.**

---

## 10. Do not compete with the state

| Why not | Detail |
|---|---|
| The state controls the rails | Fayda, telebirr, EthSwitch, licensing |
| The state controls cooperatives | Political and administrative authority |
| The state can mandate | A directive can end the model |
| The state has more capital | Subsidised competition is unwinnable |

**Partner. Deliver programmes. Take cooperative equity. Be useful.**

If the state launches a platform, become its supplier or its finance layer — not its rival.

---

## 11. Do not hire engineers before field staff

| Typical first 10 hires | Correct first 10 hires |
|---|---|
| 6 engineers | 2 engineers |
| 2 product | 1 product |
| 1 designer | 1 designer |
| 1 CEO | **1 field operations lead** |
| | 1 agronomist, 1 compliance, 1 BD, 1 finance |

**The failure mode:** a beautifully engineered product that solves a problem nobody in Arsi has.

---

## 12. Do not raise too much money too early

| Effect of over-funding | Detail |
|---|---|
| Delays the hard decisions | Unit economics can be ignored for 2 years |
| Inflates burn | More staff, more regions, more features |
| Creates a valuation you must grow into | Down round risk |
| Attracts the wrong investors | Growth expectations incompatible with agriculture's cycle |

**Raise 2× the modelled need — no more.**

---

## 13. Do not scale before the pilot gate

The single most expensive mistake available. If the pilot does not show:
- ≥5% net price gain
- ≥40% second-season repeat
- ≥0% contribution margin

then scaling multiplies the loss. **The gates exist to be enforced, not admired.**

---

## 14. Do not measure the wrong things

| Wrong | Right |
|---|---|
| Registered users | Second-season repeat transactions |
| App downloads | USSD sessions completed |
| GMV alone | Contribution margin per transaction |
| Beneficiaries reached | Verified delivery rate |
| Total loans | PAR-30 and repeat borrowers |
| Press coverage | Agent monthly income |

**Activity metrics feel good; loop metrics tell the truth.**

---

## 15. Do not pretend the risks away

| Temptation | Reality |
|---|---|
| "Ethiopia is stabilising" | Renewed fighting in Amhara from late 2026 |
| "Farmers will adopt quickly" | Only 1% have bought online; 49% have accounts |
| "The unit economics will improve with scale" | Only if the mix changes; fees alone do not |
| "Government will support us" | Government may compete with you |
| "Impact investors will fund us" | Only with evidence of repeat transactions |

**A plan that acknowledges these risks is more likely to be funded and more likely to survive.**

---

## 16. The one thing not to compromise

Whatever else is cut, the platform must:

1. **Hold funds in escrow at a licensed institution.**
2. **Verify identity through Fayda.**
3. **Keep a double-entry ledger that balances.**
4. **Notify the farmer directly of every action taken on their behalf.**

These four are the difference between a platform and a spreadsheet with ambitions.
