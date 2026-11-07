# 07.7 · Gates and Kill Criteria

*Part of [07 · Implementation](README.md)*

Gates are how a plan stays honest. Each phase ends with measurable thresholds; if they are not met, the
default is **stop, do not scale**.

---

## 1. Why gates matter more than projections

In agricultural technology, the most common way to lose money is to **scale a product that has not been
proven**, because growth masks unit-economic failure for 18–24 months. Gates force the evidence to
arrive before the spending does.

---

## 2. The gate framework

| Gate | Phase | Decision |
|---|---|---|
| **G0** | 0 → 1 | Are we legally and operationally able to transact? |
| **G1** | 1 → 2 | Do farmers earn more and come back? |
| **G2** | 2 → 3 | Do services work and does credit repay? |
| **G3** | 3 → 4 | Are we a viable national business? |
| **G4** | 4 → 5 | Is the ecosystem real (third-party GMV)? |
| **G5** | 5 | Is the ecosystem self-sustaining and governed? |

---

## 3. Gate 0 — Ready to transact

| Criterion | Threshold | Evidence |
|---|---|---|
| Escrow partner | Signed agreement | Executed contract |
| Identity | Fayda verification working | Test verification log |
| Payments | ≥1 rail live in production | Test transaction |
| Demand | ≥3 anchor buyers with volumes | Signed LOIs |
| Supply | ≥2 cooperatives with commitments | Signed MoUs |
| NBE questions | 4 written answers | Correspondence |
| DPIA | Complete | Signed document |
| Funding | ≥ETB 20 m committed | Bank statement |

**Fail action:** delay 3 months and re-test. Do not launch without escrow and identity.

---

## 4. Gate 1 — The pilot works

| # | Criterion | Threshold | Kill threshold |
|---|---|---|---|
| 1 | Transactions settled | ≥3,000 | <1,000 |
| 2 | **Net price gain to farmer** | **≥5%** | **<3%** |
| 3 | **Second-season repeat rate** | **≥40%** | **<20%** |
| 4 | Contribution margin | ≥0% | <−1% |
| 5 | Escrow dispute rate | ≤3% | >6% |
| 6 | Payment speed | ≤24h median | >72h |
| 7 | Agent retention at 12 months | ≥70% | <50% |
| 8 | Data completeness | ≥80% verified | <60% |
| 9 | Regulatory standing | No adverse ruling | Any prohibition |
| 10 | Buyer re-commitment | ≥2 for next season | None |

### Decision rules

| Pattern | Interpretation | Action |
|---|---|---|
| Criteria 2, 3, 4 all met | Model works | Proceed to Phase 2 |
| 2 and 3 met, 4 not | Value created but monetisation wrong | Fix pricing/cost; re-test in 1 season |
| 2 met, 3 not | Value created but experience poor | Diagnose retention; re-test |
| 2 not met | **Value proposition false** | **Stop or change the model fundamentally** |
| 1 far below | Operational capability failing | Fix operations; do not scale |

**If the net price gain is below 3% after 3,000 transactions, stop.** No amount of scale fixes a
proposition that does not pay the farmer.

---

## 5. Gate 2 — Services and credit work

| # | Criterion | Threshold | Kill threshold |
|---|---|---|---|
| 1 | Active farmers | ≥150,000 | <60,000 |
| 2 | GMV annualised | ≥ETB 8 bn | <ETB 3 bn |
| 3 | Blended take rate | ≥1.7% | <1.3% |
| 4 | Lenders live | ≥2 | 0 |
| 5 | **Loan repayment (PAR-30)** | **<7%** | **>15%** |
| 6 | Input attach rate | ≥20% | <8% |
| 7 | Loss reduction | ≥5 pp | <2 pp |
| 8 | EBITDA | ≥−10% of revenue | Worse than −25% |
| 9 | Agent retention | ≥75% | <55% |
| 10 | Regions contribution-positive | ≥2 | 0 |

### Decision rules

| Pattern | Interpretation | Action |
|---|---|---|
| 1, 2, 5 met | Scale engine works | Proceed |
| 5 fails (defaults >15%) | Underwriting is broken | Stop lending; rebuild the model; do not scale |
| 4 fails (no lender) | Finance thesis unproven | Proceed as fee-only business; reduce ambition |
| 2 fails | Liquidity not forming | Re-examine demand-side; consider principal trading |

**The credit criterion is the most consequential.** A 15%+ default rate means the data is not predictive
or the collections are broken. Lending into that is how platforms die.

---

## 6. Gate 3 — National viability

| # | Criterion | Threshold |
|---|---|---|
| 1 | Active farmers | ≥350,000 |
| 2 | GMV annualised | ≥ETB 25 bn |
| 3 | EBITDA | Positive 4 consecutive quarters |
| 4 | Regions contribution-positive | ≥4 of 6 |
| 5 | Lender concentration | No lender >50% |
| 6 | Repeat rate | ≥55% |
| 7 | PAR-30 | <4% |
| 8 | Dispute rate | ≤1.5% |
| 9 | Data completeness | ≥90% verified |
| 10 | API v1 public | Published and used by 3 partners |

**Fail action at Gate 3:** the business is viable but not national. Consider focusing on 3 profitable
regions rather than pursuing breadth. **A profitable regional platform is a good outcome; an
unprofitable national one is not.**

---

## 7. Gate 4 — Ecosystem

| Criterion | Threshold |
|---|---|
| Third-party GMV share | ≥20% |
| Live third-party integrations | ≥15 |
| Developers registered | ≥200 |
| API uptime | ≥99.5% |
| Revenue from APIs/partners | ≥10% of total |

---

## 8. The three "stop" conditions (regardless of gate)

| Condition | Why it is terminal |
|---|---|
| **Net price gain <3% sustained for 2 seasons** | The core promise is false; no pivot within this model fixes it |
| **PAR-30 >20% after 2 seasons of lending** | The data does not predict repayment; the credit thesis collapses |
| **Regulatory prohibition of escrow model** | The transaction mechanism is illegal; requires a different business |

---

## 9. The pivot options if a gate fails

| Failure | Pivot |
|---|---|
| Farmers don't sell through platform | Become a **buyer** (principal), remove their risk |
| Price gain too small | Target **higher-value commodities** (coffee, horticulture) |
| Agents uneconomic | Go **direct to cooperatives** as the only channel |
| Credit defaults high | Become a **data provider** to lenders rather than an originator |
| Lenders won't lend | Focus on **programme contracts** and fee revenue |
| Security untenable | Operate **one region** only; wait |

**Every pivot keeps the same core asset: the ledger of verified transactions.**

---

## 10. Gate review process

| Element | Requirement |
|---|---|
| Timing | End of each phase, not mid-phase |
| Evidence | Data, not narrative; audited where possible |
| Independent input | One external reviewer per gate |
| Decision | Go / Conditional go / Pivot / Stop — recorded |
| Communication | Written to the board and investors |
| Consequence | Funding tranches tied to gate outcomes |

**A gate that has never failed is not a gate.** If the platform passes every gate on the first attempt,
the thresholds were set too low.
