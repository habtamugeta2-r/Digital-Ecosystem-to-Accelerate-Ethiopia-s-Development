# 01.5 · Shocks: Conflict, Displacement and Climate

*Part of [01 · Context](README.md)*

---

## 1. Conflict: the largest single destroyer of development gains

| Indicator | Value | Period | Confidence |
|---|---|---|---|
| Internally displaced persons (national) | ~3.3 million (some estimates 4.5 m+) | 2024–26 | 🟡 |
| IDPs in Tigray alone | ~2 million | early 2026 | 🟠 |
| Tigray reconstruction need | ~US$5 bn, <30% funded | 2026 | 🟠 |
| Physical damage from northern conflict | US$22.7 bn across six regions | World Bank | 🟡 |
| Estimated reconstruction cost | ~US$19.7 bn | World Bank | 🟡 |
| Estimated lost GDP by 2027 | ~US$125 bn; economy ~19% smaller | Oxford Initiative | 🟠 |
| Monthly export revenue lost during Tigray war | ~US$20 m | 2020–22 | 🟠 |
| Conflict share of displacement causes | 82.1% | 2025 | 🟡 |
| Renewed hostilities | Late Sept 2026 in Tigray, Amhara, Afar; renewed displacement in Nov 2026 | 2026 | 🟡 |

**The 2020–2022 northern war** destroyed factories, health facilities, schools, roads and markets;
displaced millions; and contributed materially to the sovereign default by widening the current
account deficit and draining reserves. The November 2022 Pretoria Agreement ended active fighting but
did not resolve contested territory (notably Western Tigray) or return most displaced people.

**2026 re-escalation.** Renewed fighting from late September 2026 in Tigray, Amhara and Afar has
displaced thousands more, disrupted aid delivery, restricted movement on key roads (e.g. Gonder–
Debark–Metema) and forced previously returned families to flee again. Fitch responded by cutting its
FY27 growth forecast to ~7% and cited "renewed conflict in Tigray and Amhara regions" alongside
El Niño effects.

**Implication for a digital platform — and it is a hard one.** No agricultural marketplace can
operate where roads are contested, buyers cannot travel, and farmers cannot reach fields. The
operating model must therefore be:

- **Region-diversified from Phase 1**, with no single region exceeding ~35% of GMV.
- **Corridor-aware**, with the ability to reroute or suspend without losing the network.
- **Light-asset**, so a suspended region does not strand capital.
- **Cash and USD-hedged** enough to survive a 6-month regional shutdown.
- **Aligned to recovery**, because post-conflict reconstruction (Tigray, Amhara, parts of Oromia) is
  itself a market — input distribution, reconstruction logistics, seed and livestock restocking.

---

## 2. Climate: increasingly the binding agronomic constraint

| Indicator | Value | Period | Confidence |
|---|---|---|---|
| Share of agriculture that is rain-fed | ~95% | 2025 | 🟡 |
| Irrigation coverage | 4–5% | 2025 | 🟡 |
| Drought-related production loss, East Hararghe | −54% | 2026 season | 🟡 |
| Drought-related production loss, West Hararghe | −34% | 2026 season | 🟡 |
| People facing acute food insecurity (mid-2026) | 15–16 m | projection | 🟡 |
| Failed rainy seasons | 4 consecutive (2020–2023) then La Niña/flood cycle | 2020–26 | 🟡 |
| 2024 floods | significant, compounded food insecurity | 2024 | 🟡 |

Ethiopia oscillates between **drought and flood** with increasing amplitude. The 2020–2023 drought
was among the worst in 40 years; 2024 brought destructive flooding; 2025–26 saw a La Niña-influenced
failed *deyr/hagaya* season in the south and east. In the 2026 season, East Hararghe lost 54% of
production and West Hararghe 34%.

**Why the climate cycle makes information valuable.** Yield outcomes are driven by decisions made
before the rain: what to plant, when, which variety, how much fertiliser. Weather-index advisory,
seasonal forecasts and pest alerts (desert locust, fall armyworm, wheat rust) shift those decisions.
Ethiopia already has the delivery channel (8028, 67 million calls) and the modelling capability
(EIAR, ATI, the AI Institute). What is missing is **integration with the transaction** — advice that
is tied to the specific plot, the specific input purchase, and the specific buyer contract.

**Why the climate cycle makes insurance necessary — and hard.** Index-based products (weather index
crop insurance, index-based livestock insurance) have been piloted in Ethiopia since 2015 with
measurable positive effects: insured farmers showed 9.44 percentage points lower incidence of food
insecurity, improved dietary diversity (~9–10%) and reduced vulnerability (~10%). But adoption
remains pilot-scale because of basis risk, weak weather-station density, low willingness to pay and
the absence of a national reinsurance and data backbone. **A platform that already collects plot
location, planting date, input use and yield can reduce basis risk and distribution cost
simultaneously** — one of the strongest arguments for a bundled platform rather than standalone
insurance.

---

## 3. Humanitarian funding contraction

| Development | Effect |
|---|---|
| US foreign assistance restructuring (2025) | Major programmes halted; the main moderate-malnutrition programme stopped nationwide |
| WFP shortfall | US$222 m (Apr–Sep 2025); treatment for 650,000 women and children paused |
| Refugee support | Cash and in-kind assistance for up to 1 m refugees at risk |
| Food aid diversion scandal (2023) | Nationwide pause; shifted donor preference toward cash, targeting and digital delivery |

**Strategic implication.** The collapse of in-kind aid is pushing the humanitarian system toward
**cash-based, digitally delivered, identity-targeted transfers** — exactly the infrastructure a
marketplace platform already operates. There is a realistic revenue line in becoming the delivery
channel for cash transfers and input vouchers, and a realistic social argument for it (cash transfers
through mobile money are cheaper to administer, less divertible, and stimulate local markets).

---

## 4. The compound-shock problem

Ethiopia rarely experiences one shock; it experiences stacked ones. A representative sequence from
the last five years:

```
CONFLICT  →  DISPLACEMENT  →  LOSS OF ASSETS & LAND ACCESS  →  LOWER PLANTING
    ↓                                                                    ↓
FISCAL STRAIN ←  LOWER TAX BASE  ←  LOWER MARKET ACTIVITY  ←  LOWER HARVEST
    ↓                                                                    ↑
REDUCED PUBLIC SERVICES  ────────────────────────►  HIGHER INPUT COSTS
    ↓                                                                    ↑
DROUGHT  ─────────────────────────────────────────►  LOWER YIELDS ──────┘
```

Each shock makes the next one worse because the buffer stock — savings, livestock, social capital,
state fiscal space — has already been consumed. This is why poverty jumped from 33% to 43% in nine
years while GDP still grew at 9%.

**What this means for the platform's theory of change:** the value proposition is not "make farmers
richer in a growing economy." It is **"reduce the number of ways a household can lose."** Faster
sale at a known price, fewer spoiled bags, a payment that arrives by phone instead of after a
three-day journey, a loan that does not require collateral, an insurance payout triggered by
satellite data instead of a claim adjuster — each one removes a specific loss channel. That framing is
more robust to a volatile macro environment than a pure growth story.

---

## 5. Resilience design principles

| Principle | Implementation |
|---|---|
| Geographic diversification | Cap any one region at ~35% of GMV; minimum three regions by Phase 2 |
| Corridor diversification | Support Djibouti, Berbera and domestic routes; maintain route database |
| Asset-light logistics | Contract capacity; no owned fleet until Phase 3 |
| Offline-first | Queue transactions on device; sync on reconnect; SMS confirmation fallback |
| Cash-tolerant | Agents handle cash-in/out; escrow works with cash at agent |
| Identity redundancy | Fayda primary; PIN + agent attestation + community verification fallback |
| Data redundancy | Multi-region hosting and encrypted backups; consider a "data embassy" arrangement |
| Shock-responsive product | Ability to switch to emergency mode (cash transfer delivery, price ceilings, suspension) within 48 hours |
| Staff safety | Regional deployment rules; no field work in active-conflict zones; local agent networks reduce staff exposure |

---

## Key takeaways

1. Conflict has cost Ethiopia an estimated US$125 bn in lost GDP by 2027 and remains live in 2026 —
   it is the **highest-severity risk** to any agricultural platform and must shape geography,
   asset intensity and capital structure.
2. Climate is the binding agronomic constraint; drought and flood now alternate with increasing
   amplitude, and losses in specific zones (e.g. −54% East Hararghe) can be catastrophic.
3. Index insurance and digital advisory both have **proven but small-scale** Ethiopian evidence; the
   missing piece is integration with the transaction and the plot.
4. Humanitarian funding contraction is pushing donors toward digital, targeted, cash-based delivery —
   a real and aligned revenue opportunity.
5. Design for **loss reduction** rather than growth: it is the more defensible value proposition in a
   compound-shock environment.
