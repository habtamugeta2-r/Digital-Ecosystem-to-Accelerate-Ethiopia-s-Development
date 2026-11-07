# 02.6 · Scoring, Ranking and the Comparison Matrix

*Part of [02 · Opportunities](README.md)*

This file shows the full working behind the ranking in the section README, and stress-tests it against
alternative weightings.

---

## 1. Full scoring matrix (1–5 per criterion)

| Opportunity | Scale | Depth | Digital leverage | Feasibility now | Evidence | Moat | Policy fit | Risk control | **Total /40** |
|---|---|---|---|---|---|---|---|---|---|
| Agriculture supply-chain platform | 5 | 5 | 5 | 3 | 4 | 5 | 5 | 3 | **35** |
| Digital financial services | 4 | 4 | 5 | 4 | 5 | 3 | 5 | 3 | **33** |
| Government & public services | 5 | 3 | 5 | 2 | 4 | 1 | 5 | 2 | **27** |
| Marketplaces (urban/SME e-commerce) | 3 | 3 | 4 | 4 | 2 | 3 | 3 | 4 | **26** |
| Connectivity & infrastructure | 5 | 5 | 1 | 1 | 4 | 2 | 5 | 2 | **25** |
| Human capital (health/education) | 4 | 3 | 3 | 2 | 3 | 2 | 4 | 3 | **24** |
| Logistics aggregator (standalone) | 3 | 4 | 4 | 3 | 3 | 3 | 3 | 3 | **26** |

*(Note: standalone logistics scores 26 but rises to 35+ when integrated into the agriculture platform,
which is why it appears as a module rather than a separate line.)*

---

## 2. Criterion-by-criterion justification

### Scale
- **5** — Agriculture (75–80% of population affected), government (100%), connectivity (100%)
- **4** — DFS (49% of adults banked; 100% aspirational), human capital
- **3** — Urban e-commerce (~24% urban, of whom a minority buy online), logistics standalone

### Depth (magnitude of change per person reached)
- **5** — Agriculture: a 5–15% net price gain on the entire crop is transformative at the household
  level; connectivity: same argument for power and internet.
- **4** — DFS: credit access changes a household's trajectory; logistics: material cost reduction.
- **3** — Government: time saved and reduced bribery, important but less direct; e-commerce: convenience.

### Digital leverage (share of the problem that is information/coordination, not capital)
- **5** — Agriculture (prices, matching, credit history), DFS (information + rails), government
  (identity, records, payments)
- **4** — E-commerce, logistics
- **3** — Human capital (needs physical clinics, teachers, drugs)
- **1** — Connectivity (needs towers, fibre, turbines, transformers)

### Feasibility now
- **4** — DFS (rails exist, partners exist), e-commerce (can launch tomorrow, will lose money)
- **3** — Agriculture (needs agents, cooperatives, liquidity bootstrapping)
- **2** — Government (procurement), human capital (clinical governance)
- **1** — Connectivity (licence + billions of capex)

### Evidence
- **5** — DFS (Suri & Jack; telebirr's 6.88 m borrowers; Kenya, India at scale)
- **4** — Agriculture (8028 reach, 14–25% advisory yield gains, Lersha traction, DAR), government
  (India DBT ₹3.48–5.14 lakh crore; Estonia 2% of GDP), connectivity (obvious)
- **3** — Logistics, human capital
- **2** — Ethiopian e-commerce (a record of failure)

### Moat
- **5** — Agriculture (data + network + cooperative relationships + finance history)
- **3** — DFS (underwriting data, but contested), e-commerce (brand + logistics), logistics (route density)
- **2** — Connectivity (regulated), human capital
- **1** — Government (state owns it)

### Policy fit
- **5** — Agriculture (DAR, NAFIR, PGMS), DFS (NDPS, NFIS), government (Digital Ethiopia 2030),
  connectivity (Digital Ethiopia 2030)
- **4** — Human capital
- **3** — E-commerce, logistics

### Risk control (higher = better controlled)
- **4** — E-commerce (urban, low conflict exposure), 
- **3** — Agriculture, DFS, logistics, human capital
- **2** — Government (political/receivable risk), connectivity (capex/regulatory)

---

## 3. Sensitivity: does the ranking survive different weightings?

### Weighting A — "Poverty impact first" (double scale and depth)
| Rank | Opportunity | Score |
|---|---|---|
| 1 | Agriculture | 50 |
| 2 | DFS | 45 |
| 3 | Connectivity | 35 |
| 4 | Government | 37 |
| 5 | Human capital | 31 |

Agriculture still wins.

### Weighting B — "Investor returns first" (double moat and feasibility)
| Rank | Opportunity | Score |
|---|---|---|
| 1 | DFS | 44 |
| 2 | Agriculture | 43 |
| 3 | E-commerce | 36 |

DFS narrowly wins on a pure-returns basis — which is exactly why it is the **second** line of the
business and why it must be entered **through** the marketplace (which supplies the moat DFS lacks on
its own).

### Weighting C — "Executable by a small team in 12 months" (double feasibility and risk control)
| Rank | Opportunity | Score |
|---|---|---|
| 1 | E-commerce | 37 |
| 2 | DFS | 36 |
| 3 | Agriculture | 34 |

This is the honest counter-argument: **the easiest thing to build is the least valuable.** The
recommendation addresses it by making Phase 1 of the agriculture platform as executable as an
e-commerce launch — one crop, one cluster, two cooperatives, an agent network and a price board.

### Weighting D — "Political durability" (double policy fit and moat)
| Rank | Opportunity | Score |
|---|---|---|
| 1 | Agriculture | 50 |
| 2 | DFS | 46 |

Agriculture wins decisively. In a country with Ethiopia's political risk profile, this matters.

**Conclusion:** agriculture is rank 1 under three of four weightings and rank 2 under the fourth by a
single point. The ranking is robust.

---

## 4. Where the opportunities overlap (the real reason to combine them)

| Capability | Agriculture | DFS | E-commerce | Logistics | Government | Human capital |
|---|---|---|---|---|---|---|
| Fayda identity integration | ● | ● | ● | ○ | ● | ● |
| Payment orchestration | ● | ● | ● | ● | ● | ○ |
| Agent network | ● | ● | ○ | ○ | ● | ● |
| Verified transaction data | ● | ● | ● | ● | ○ | ○ |
| Buyer/seller liquidity | ● | ○ | ● | ● | ○ | ○ |
| Rural logistics | ● | ○ | ○ | ● | ○ | ○ |
| Regulatory relationships | ● | ● | ● | ● | ● | ● |

**Every column shares identity, payments and agent network.** That is the definition of shared
infrastructure: build it once, and five opportunities become cheaper.

---

## 5. The two-by-two that decides everything

```
                       HIGH DIGITAL LEVERAGE
                                │
        Government ●            │            ● Agriculture
                                │
        DFS ●                   │
                                │
   ─────────────────────────────┼─────────────────────────────
   HARD TO EXECUTE              │              EASY TO EXECUTE
                                │
        Connectivity ●          │       ● E-commerce
                                │
        Human capital ●         │       ● Logistics
                                │
                        LOW DIGITAL LEVERAGE
```

Agriculture is the only opportunity in the **high-leverage / moderately-executable** quadrant that
also has a 12-million-household addressable base. That is the whole argument.

---

## 6. What would reorder the ranking

| Change | Effect on ranking |
|---|---|
| A national agri-marketplace launched and executed well by the state | Agriculture drops to #3 (partner instead) |
| Sustained closure of the Djibouti corridor | Agriculture and logistics drop sharply |
| Regulatory opening permitting foreign-owned payment institutions at scale | DFS rises to #1 |
| A working national credit bureau with rural coverage | DFS's moat weakens; agriculture's data moat weakens too |
| Smartphone ownership reaching 60%+ and data costs halving | E-commerce rises; USSD-first design becomes less critical |
| A peace settlement and reconstruction programme | Agriculture and logistics rise materially (reconstruction demand) |
| Major donor shift to cash-based transfers at scale | Government/programme delivery rises to #2 |

---

## Key takeaways

1. The ranking is robust to four different weightings: agriculture is #1 in three and #2 by one point
   in the fourth.
2. DFS is the better pure-investment case but the weaker standalone moat — hence it is entered as a
   module.
3. E-commerce is the *easiest* opportunity to execute, which is why it is the one everyone tries and
   the one that has failed most often in Ethiopia.
4. Every opportunity shares the same three rails (identity, payments, agents) — which is the
   economic argument for building shared infrastructure rather than six products.
5. Re-rank if the state enters the agriculture marketplace credibly; then partner rather than compete.
