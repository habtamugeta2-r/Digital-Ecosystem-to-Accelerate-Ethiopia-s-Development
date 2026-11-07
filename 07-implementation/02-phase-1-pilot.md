# 07.2 · Phase 1 — The Pilot (Months 6–18)

*Part of [07 · Implementation](README.md)*

**The most important phase. Everything after it is execution; this phase is proof.**

---

## Objective

Prove, on real transactions with real money, that:
1. A farmer earns **more** by selling through the platform than through the incumbent channel.
2. The platform earns a **positive contribution margin** per transaction.
3. Farmers **come back** for a second season.

If any of the three fails, do not scale. Change the model.

---

## Pilot design

| Element | Choice | Rationale |
|---|---|---|
| **Region** | Oromia — Arsi/Bale (wheat) or North Shewa (maize/teff) | Surplus, road access to Addis, cooperative density, no active conflict |
| **Commodity** | Wheat (winter/irrigated & Meher) or maize | Standard grades, high volume, deep buyer market |
| **Second commodity** | Teff | Highest value staple; strong farmer participation |
| **Buyers** | 3–5 millers/processors in Addis + 1 wholesaler | Committed volume |
| **Cooperatives** | 8–12 primary cooperatives across 3–5 woredas | Organised supply |
| **Farmers** | Target 8,000 registered; ≥4,000 transacting | |
| **Agents** | 50–70, clustered | Density beats coverage |
| **Collection points** | 4–6, at cooperative warehouses | Reduce farmer travel |
| **Duration** | 12 months = 2 harvest cycles (Belg + Meher) | Two chances to learn |

### Explicit exclusions
- No Tigray, no conflict-affected Amhara, no pastoral lowlands.
- No horticulture (perishability), no livestock (weight disputes).
- No cash crops with export restrictions.
- No lending from the platform's own balance sheet.

---

## What is built

| Component | Scope | Notes |
|---|---|---|
| USSD flow | Register, list, check bids, accept, confirm delivery | Primary farmer channel |
| IVR | Price information, bid notification, contract confirmation | For low literacy |
| SMS | Notifications, confirmations, receipts | Universal |
| Agent app | Android, offline-first, ≥7 days queued operations | Agents only |
| Buyer web app | Post requirements, bid, fund escrow, confirm receipt | Buyers |
| Escrow | Bank/PSI custody, release triggers, dispute hold | Never platform-held |
| Ledger | Double-entry, append-only, auditable | Source of truth |
| Registry | Farmer, plot, cooperative, buyer, agent | |
| Grading | Standard-based, sampling, retained sample | |
| Dispatch | Manual-assisted (spreadsheet + phone) | Automation in Phase 2 |
| Admin | Operations console, dispute management | |

**Not built in Phase 1:** credit, insurance, logistics app, developer API, mobile app for farmers,
data products. All are Phase 2+.

---

## The pilot trading cycle (one season)

```
    Month 1-2        Month 3-4          Month 5-6        Month 7-8
  ┌───────────┐   ┌─────────────┐   ┌────────────┐   ┌────────────┐
  │ REGISTER  │──►│   PLANT     │──►│   GROW     │──►│  HARVEST   │
  │ farmers   │   │ (no platform│   │ (advisory  │   │  & SELL    │
  │ plots     │   │  role yet)  │   │  begins)   │   │            │
  └───────────┘   └─────────────┘   └────────────┘   └─────┬──────┘
                                                            │
                        ┌───────────────────────────────────┘
                        ▼
  ┌──────────────┐   ┌──────────────┐   ┌──────────────┐   ┌──────────────┐
  │ LIST on USSD │──►│ RECEIVE BIDS │──►│   ACCEPT     │──►│ FUND ESCROW  │
  │              │   │ (SMS/IVR)    │   │ (PIN+IVR)    │   │ (buyer pays) │
  └──────────────┘   └──────────────┘   └──────────────┘   └──────┬───────┘
                                                                   │
  ┌──────────────┐   ┌──────────────┐   ┌──────────────┐          │
  │  GET PAID    │◄──│   DELIVER    │◄──│   DISPATCH   │◄─────────┘
  │ (same day)   │   │ (weigh,grade)│   │ (truck)      │
  └──────┬───────┘   └──────────────┘   └──────────────┘
         │
         ▼
  ┌──────────────┐
  │ RATE + REPEAT│
  └──────────────┘
```

**Critical insight:** the pilot spends 4 months *before* any transaction. That is 4 months of cost with
no revenue. Budget for it, and use the time to onboard farmers and digitise cooperative records.

---

## Operating model for the first 1,000 transactions

Do not automate. Do this instead:

| Step | Who | Tool |
|---|---|---|
| Farmer calls the agent | Farmer → Agent | Phone |
| Agent creates listing | Agent | Agent app |
| Ops team calls 3 buyers | Ops staff | Phone / WhatsApp |
| Bids entered | Ops staff | Admin console |
| Farmer notified | System | IVR + SMS |
| Farmer accepts | Farmer | USSD or agent |
| Buyer funds escrow | Buyer | Bank transfer / wallet |
| Dispatch arranged | Ops staff | Phone |
| Weighing | Cooperative + agent | Scale, app entry |
| Payment released | Ops staff | Escrow instruction |
| Reconciliation | Finance | Ledger |

**This is deliberately labour-intensive.** The purpose is to learn what needs automating, not to prove
software works.

---

## Metrics that decide the future

| Metric | Target | Kill threshold | Measurement |
|---|---|---|---|
| **Net price gain to farmer** | ≥8% vs. local trader offer | <3% | Baseline survey + matched comparison |
| **Second-season repeat rate** | ≥40% | <20% | Cohort tracking |
| **Contribution margin per transaction** | ≥0 (by month 9) | <−1% of GMV after 1,000 txns | Ledger + cost allocation |
| **Escrow dispute rate** | ≤2% | >5% | Dispute log |
| **Post-harvest loss reduction** | ≥5 pp | <2 pp | Sample measurement at collection |
| **Payment speed** | Same day (≤8 hours) | >48 hours | Timestamp data |
| **Agent income** | ≥ETB 30,000/yr | <ETB 15,000 | Agent survey |
| **Cost to acquire a farmer** | ≤ETB 900 | >ETB 2,000 | Field budget / farmers |
| **USSD completion rate** | ≥70% | <40% | Session logs |
| **Farmer trust score** | ≥4/5 | <3/5 | Quarterly survey |

---

## The price-gain measurement (most important, most often faked)

Claiming a price gain without a proper counterfactual is the single most common analytical failure in
agricultural development reports.

**Design:**

| Group | Description | Size |
|---|---|---|
| Treated | Platform sellers | 300+ |
| Comparison | Neighbouring farmers selling to traders in the same woreda, same crop, same week | 300+ |
| Baseline | Trader price recorded at listing time by the agent | all |

**Compute:**
- Gross price difference (platform vs. comparison)
- Minus platform fee
- Minus additional transport cost
- Minus quality adjustment (grade differences must not be counted as a price gain)
- **= net price gain**

**Report the net figure only.** If the gross is 12% and the fee, transport and grading adjustments eat
9 points, the honest claim is 3% — and 3% is not enough to justify the platform.

---

## Team in Phase 1

| Function | FTE |
|---|---|
| Engineering | 5 |
| Product/design | 2 |
| Field operations | 4 |
| Agronomy | 2 |
| Trading desk (ops) | 2 |
| Finance/reconciliation | 1 |
| Compliance | 1 |
| Management | 2 |
| **Total** | **19** |

---

## Budget (ETB m)

| Category | Amount |
|---|---|
| Salaries | 21.6 |
| Field operations (travel, training, agent support) | 6.0 |
| Agent device subsidy (60 × ETB 14,000) | 0.8 |
| Technology and comms (SMS, USSD, IVR, cloud) | 3.2 |
| Cooperative onboarding (12 × ETB 250,000) | 3.0 |
| Marketing and materials (local, radio) | 1.5 |
| Legal, audit, compliance | 1.8 |
| Office, equipment, admin | 2.4 |
| Contingency | 3.5 |
| **Total** | **43.8** |
| Offset: programme contract | (4.0) |
| **Net** | **39.8** |

---

## Gate 1 → 2

All must be true:

| # | Criterion | Threshold |
|---|---|---|
| 1 | Transactions completed | ≥3,000 |
| 2 | Net price gain | ≥5% (target 8%) |
| 3 | Second-season repeat | ≥40% |
| 4 | Contribution margin | ≥0 for the last quarter |
| 5 | Escrow dispute rate | ≤3% |
| 6 | Payment speed | ≤24 hours median |
| 7 | Agent retention | ≥70% at 12 months |
| 8 | Data completeness | ≥80% of records verified |
| 9 | Regulatory position | No adverse ruling; all four NBE questions settled |
| 10 | Buyer commitment | ≥2 buyers willing to sign for the next season |

**If criteria 1–4 are not met, do not proceed to Phase 2.** Either fix the model or stop. Scaling a
broken unit economic is the most expensive way to learn.

---

## Five ways the pilot fails

| Failure | Early signal | Response |
|---|---|---|
| **Side-selling** | Listings created but not delivered | Escrow on first trade; credit tie-in |
| **Buyers don't bid** | Listings expire without bids | Pay for demand; become principal buyer |
| **Agents can't earn** | Agent income <ETB 2,500/mo | Add input sales; concentrate territory |
| **Price gain is illusory** | Net gain <3% after costs | Re-examine fee; re-examine transport |
| **Operational chaos at harvest** | Missed dispatches, disputes spike | Pre-book trucks; hire seasonal staff |
