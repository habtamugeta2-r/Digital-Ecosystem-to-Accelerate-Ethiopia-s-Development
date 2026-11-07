# 07 · Implementation: Five Phases from Pilot to Platform

*How the ecosystem is actually built, sequenced, gated and staffed*

---

## Files in this section

| File | Contents |
|---|---|
| [`01-phase-0-foundations.md`](01-phase-0-foundations.md) | Months 0–6: legal, licences, partners, design |
| [`02-phase-1-pilot.md`](02-phase-1-pilot.md) | Months 6–18: single-commodity, single-region pilot |
| [`03-phase-2-services.md`](03-phase-2-services.md) | Months 18–36: advisory, finance, logistics, 2–4 regions |
| [`04-phase-3-scale.md`](04-phase-3-scale.md) | Months 36–54: national footprint, multi-commodity |
| [`05-phase-4-5-platform.md`](05-phase-4-5-platform.md) | Months 54–84: open platform and ecosystem |
| [`06-team-and-organisation.md`](06-team-and-organisation.md) | Hiring plan, structure, capability gaps |
| [`07-gates-and-kill-criteria.md`](07-gates-and-kill-criteria.md) | The evidence required to advance or stop |
| [`08-operating-playbook.md`](08-operating-playbook.md) | Week-by-week pilot operations |

---

## 1. The sequence at a glance

```
PHASE 0        PHASE 1         PHASE 2          PHASE 3         PHASE 4-5
Foundations →  Pilot       →   Services     →   Scale       →   Platform
M0–M6          M6–M18          M18–36           M36–54          M54–84
   │              │               │                │               │
   │              │               │                │               │
Licences        Wheat/maize     Advisory       6-7 regions     Open APIs
Partners        Oromia cluster  Logistics      7 commodities   Developer
Design          Manual trading  Credit          National brand  ecosystem
Identity        8k farmers      180k farmers    750k farmers    Gov integration
```

**Total timeline to a functioning national ecosystem: 7 years.** Any plan claiming 2–3 years is
describing a pilot, not an ecosystem.

---

## 2. Why this order and not another

| Alternative sequence | Why rejected |
|---|---|
| **Build the platform first, then find users** | The graveyard of African agri-tech. Users first, software second |
| **Launch nationwide immediately** | Operations collapse; no data; no trust; no liquidity |
| **Start with financial services** | No data to underwrite with; no licence; no trust |
| **Start with e-commerce for all goods** | Jumia's 11 years of losses; wrong unit economics; no wedge |
| **Start with government services (Irembo model)** | Wrong actor for a startup; requires state mandate |
| **Start with connectivity** | Capital-intensive; not a software business; regulated |
| **Build a super-app** | Requires a high-frequency wedge the platform does not have |

**The chosen wedge — agricultural trade settlement — has four properties that make it correct:**
1. It is **frequent enough** (2–4 times per farmer per season) to build data.
2. It is **high value** (ETB 28–46k per transaction) so basis-point fees are meaningful.
3. It is **painful** (price opacity, payment risk, post-harvest loss) so there is willingness to change.
4. It **generates the data** needed to unlock the highest-margin business (credit).

---

## 3. Critical path

```
Licences/partnerships ──┐
                        ├──► Escrow live ──► First settled trade ──► Repeat trade
Fayda integration ──────┘                          │
                                                   ▼
                          Agent network ──► Volume ──► Ledger ──► Credit ──► Margin
```

**The critical path runs through three things that are all external:**
1. A **licensed escrow/custody partner** (bank or PSI).
2. **Fayda** integration via FaydaVerse.
3. **Anchor buyers** willing to commit volume.

All three are negotiation-dependent. **Start all three in month 1**, because each takes 3–6 months and
they gate everything else.

---

## 4. Phase summary table

| Phase | Duration | Regions | Farmers | GMV | Team | Key output | Gate to proceed |
|---|---|---|---|---|---|---|---|
| 0 | 6 mo | 0 | 0 | 0 | 8 | Licences, partners, design, pilot plan | Signed MoU + escrow partner + 3 buyers |
| 1 | 12 mo | 1 | 8,000 | ETB 134 m | 18 | Working marketplace, proven unit economics | ≥40% repeat, ≥8% price gain, positive CM |
| 2 | 18 mo | 3 | 180,000 | ETB 11 bn | 45 | Advisory, logistics, credit live | 2 lenders, loss reduction proven, break-even path |
| 3 | 18 mo | 6 | 400,000 | ETB 36 bn | 90 | National footprint, multi-commodity | Profitable, lender-independent |
| 4 | 15 mo | 7 | 700,000 | ETB 70 bn | 130 | Open API, third-party apps | Ecosystem GMV >20% of total |
| 5 | 15 mo | 8+ | 1 m+ | ETB 100 bn+ | 160 | Full ecosystem, gov integration | — |

---

## 5. The five things that must be true at every phase

| Principle | Meaning in practice |
|---|---|
| **Transact early** | Manual trades in month 4 are better than automated trades in month 14 |
| **Narrow before wide** | One commodity, one region, done well |
| **Agent-anchored** | Humans in the loop, always, not as an interim measure |
| **Identity-native** | Every actor has a Fayda ID from day one |
| **Settle in escrow** | Never mediate a payment you do not control |

---

## 6. What "done" looks like at each phase

**Phase 1 done:** a farmer in Arsi can list wheat by USSD, receive three bids, accept one, deliver to a
collection point, and be paid the same day — with the platform earning a fee and the farmer earning more
than the trader offered.

**Phase 2 done:** the same farmer gets a planting-date advice SMS, buys fertiliser on credit that is
repaid automatically at harvest, and receives a payout when rainfall is insufficient.

**Phase 3 done:** the platform operates in six regions with a national brand, a lender panel of three,
and a positive EBITDA.

**Phase 4 done:** a third-party developer builds a soil-testing app on the platform's API and reaches
50,000 farmers without the platform doing the work.

**Phase 5 done:** a government ministry runs its entire input subsidy programme through the platform's
identity, voucher and settlement rails.

---

## 7. The uncomfortable truths about this timeline

| Truth | Implication |
|---|---|
| Agriculture runs on a 6–12 month cycle | You get ~2 feedback loops per year, not 12 |
| Trust is built in person, in local languages | Field operations are permanent, not transitional |
| The first 1,000 transactions are hand-held | Staff them with your best people |
| Every new region resets trust to zero | Regional expansion is not replication; it is repetition |
| Government timelines are 3–6 months longer than promised | Buffer every dependency on the state |
| Two harvests per year means two chances to be wrong | Plan interventions around Meher and Belg |

---

## Read next

- [`07-gates-and-kill-criteria.md`](07-gates-and-kill-criteria.md) — the evidence thresholds
- [`02-phase-1-pilot.md`](02-phase-1-pilot.md) — the most detailed and most important phase
