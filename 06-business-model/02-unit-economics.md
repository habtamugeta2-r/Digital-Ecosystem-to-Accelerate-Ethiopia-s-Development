# 06.2 · Unit Economics

*Part of [06 · Business model](README.md)*

All figures **illustrative (⚪)** and denominated in Ethiopian birr at a working rate of ~160 ETB/USD.
They are order-of-magnitude planning assumptions, not observed data.

---

## 1. The unit: one settled transaction

Take a representative grain trade: **30 tonnes of maize, 60 quintals, at ETB 2,800/quintal = ETB
168,000** — the equivalent of about two truckloads at 15 t each (we use a mid-size trade for realism).

| Item | Amount (ETB) | % of GMV |
|---|---|---|
| **Revenue** | | |
| Marketplace commission (1.5%) | 2,520 | 1.50% |
| Payment/escrow share (0.4%) | 672 | 0.40% |
| **Total revenue** | **3,192** | **1.90%** |
| **Variable costs** | | |
| Agent commission (25% of marketplace fee) | 630 | 0.38% |
| Payment provider cost (0.35%) | 588 | 0.35% |
| SMS/IVR (~12 messages, ETB 1.5 each) | 18 | 0.01% |
| Logistics coordination cost (dispatcher time allocated) | 320 | 0.19% |
| Verification / grading cost (amortised) | 150 | 0.09% |
| Support and dispute handling (allocated) | 180 | 0.11% |
| Guarantee fund provision (0.3% of GMV) | 504 | 0.30% |
| **Total variable cost** | **2,390** | **1.42%** |
| **Contribution margin** | **802** | **0.48%** |

**Contribution margin: ~25% of revenue, ~0.5% of GMV.**

### What this means

A 0.48% contribution margin on GMV means the platform needs **very large GMV** to cover fixed costs.

| Annual fixed cost | GMV needed at 0.48% |
|---|---|
| ETB 50 m | ETB 10.4 bn |
| ETB 150 m | ETB 31.3 bn |
| ETB 400 m | ETB 83.3 bn |

The base-case Year 5 GMV of ETB 40 bn supports about ETB 190 m of fixed cost — which is realistic for
a lean national organisation but leaves little room for error.

**The strategic conclusion: the transaction fee alone cannot carry the business.** The finance and
input lines (higher margin, no logistics cost) are what make the model work. This is not a flaw in the
plan; it is the reason the plan has six revenue lines.

---

## 2. Improving the unit economics

| Lever | Effect | Difficulty |
|---|---|---|
| Raise take rate from 1.5% to 2.0% | +33% marketplace revenue | Medium (competitive limits) |
| Reduce guarantee fund provision to 0.15% | +0.15% of GMV margin | Medium (needs data) |
| Reduce agent commission to 20% | +0.08% of GMV | Low (but risks agent income) |
| Automate support (IVR self-service) | −0.05% of GMV | Medium |
| Increase average transaction size (bulk, not retail) | Fixed costs amortise across larger value | **High leverage** |
| Attach finance to the transaction | +2–3% of transaction value in origination fee | High leverage, needs time |
| Attach input sales | +4% margin on a separate purchase | High leverage |
| Reduce payment cost via direct operator agreements | −0.1–0.2% of GMV | Medium |

**The most powerful lever is product mix, not cost cutting.** A 30-tonne grain trade with an attached
input loan and insurance is worth perhaps 4–6× a bare trade. This is why the modules must eventually
coexist.

---

## 3. The unit: one farmer, per year

| Item | Year 1 | Year 2 | Year 3 |
|---|---|---|---|
| Transactions per year | 1.2 | 2.5 | 3.5 |
| Average GMV per transaction | ETB 28,000 | ETB 35,000 | ETB 45,000 |
| Annual GMV per farmer | ETB 33,600 | ETB 87,500 | ETB 157,500 |
| Marketplace + payments revenue (1.9%) | ETB 638 | ETB 1,663 | ETB 2,993 |
| Finance revenue (origination share) | 0 | ETB 350 | ETB 900 |
| Input margin | 0 | ETB 260 | ETB 650 |
| **Revenue per farmer** | **ETB 638** | **ETB 2,273** | **ETB 4,543** |
| Cost to acquire (agent onboarding, training, device share) | ETB 900 | — | — |
| Cost to serve (support, SMS, agent share) | ETB 420 | ETB 750 | ETB 1,100 |
| **Contribution per farmer** | **−ETB 682** | **+ETB 1,523** | **+ETB 3,443** |
| Cumulative | −682 | +841 | +4,284 |

**Payback: ~2 years per farmer.** That is a long payback for a low-ARPU market — which means
acquisition must be cheap (cooperative-mediated, not advertising-driven) and retention must be high
(multi-season, multi-service).

**Critical insight:** a farmer who transacts once is a loss. A farmer who transacts for three seasons
with finance attached is a very good customer. **Everything depends on repeat rate.**

---

## 4. The unit: one agent, per year

| Item | Amount |
|---|---|
| Onboarding and training cost (platform) | ETB 4,000 |
| Device + solar kit (platform-subsidised at 50%) | ETB 18,000 |
| **Platform cost per agent** | **ETB 22,000** |
| Agents per region (Year 1) | 150–300 |
| Agent cost per region | ETB 3.3–6.6 m |

| Agent revenue (agent's own income) | Year 1 | Year 3 |
|---|---|---|
| Marketplace commission share | ETB 4,800 | ETB 18,000 |
| Float commission | ETB 4,200 | ETB 7,200 |
| Logistics dispatch | ETB 2,400 | ETB 9,600 |
| Input sales margin | ETB 6,000 | ETB 24,000 |
| **Total agent income** | **ETB 17,400 (US$109)** | **ETB 58,800 (US$368)** |

**Year 1 agent income is ~US$9/month — too low to retain an agent.** This is the single most common
failure point in agent-based models.

**Fix:**
- Concentrate agents (150 per cluster, not 500 spread thin).
- Guarantee a minimum income in Year 1 (a subsidy, transparently labelled).
- Prioritise agents who already have a trading or input business — the platform adds to an existing
  income, not creates one.
- Reduce the device cost via grant funding or a device financing partner.

**Revised target:** agents should reach ≥ETB 30,000/year (~US$16/month) by month 12. Below that,
expect >40% attrition.

---

## 5. The unit: one cooperative

| Item | Amount |
|---|---|
| Onboarding cost (record digitisation, training, equipment) | ETB 180,000–350,000 |
| Members | 400–1,500 |
| Year-1 GMV through platform | ETB 1.5–4 m |
| Platform revenue at 1.9% | ETB 28,500–76,000 |
| Payback | 3–8 years |

**Cooperatives are a customer-acquisition channel, not a profit centre.** The payback is long, but the
alternative (direct-to-farmer acquisition) costs more per farmer and yields worse trust and worse data.

**Treat cooperative onboarding as marketing spend**, funded partly by programme grants — which is
exactly what the DAR/ATI budget line can cover.

---

## 6. Break-even analysis

| Fixed cost category | Monthly (ETB) | Annual (ETB m) |
|---|---|---|
| Engineering (12 FTE avg at Phase 2) | 3.0 m | 36 |
| Product, design, data (4 FTE) | 1.0 m | 12 |
| Field operations (5 regions × 4 staff) | 2.4 m | 28.8 |
| Agronomy and content (3 FTE) | 0.6 m | 7.2 |
| Compliance, legal, finance (4 FTE) | 1.2 m | 14.4 |
| Management (4 FTE) | 1.8 m | 21.6 |
| Offices, equipment, travel | 1.0 m | 12 |
| Cloud, SMS, USSD, IVR | 0.8 m | 9.6 |
| Marketing and cooperative onboarding | 0.8 m | 9.6 |
| **Total** | **~12.6 m** | **~151 m** |

**Break-even at ~ETB 151 m annual fixed cost and 0.48% contribution margin requires ~ETB 31.5 bn GMV.**
At the base-case trajectory that is reached in **Year 4**.

**Reducing the break-even:**
- Keep the fixed team lean (20–25 people until Year 3).
- Use programme contracts to cover field operations (a common and legitimate structure).
- Mix in higher-margin finance and input revenue (raises blended margin from 0.48% to ~1.2% → break-
  even at ETB 12.6 bn GMV, reached in Year 3).

---

## 7. Blended margin by phase

| Phase | Revenue mix | Blended margin on GMV |
|---|---|---|
| 1 | Programmes dominant; small marketplace | n/a (negative overall) |
| 2 | Marketplace + inputs + first finance | ~0.8% |
| 3 | Marketplace + finance + inputs + logistics | ~1.2–1.5% |
| 4 | All lines + data + API | ~1.5–2.0% |

**The path to profitability is margin mix, not cost reduction.** This is the most important sentence in
this file.

---

## 8. Sensitivity table

Base-case Year 5 revenue = ETB 1,083 m. How it moves:

| Variable | −20% | Base | +20% |
|---|---|---|---|
| GMV | 866 | 1,083 | 1,300 |
| Take rate | 942 | 1,083 | 1,224 |
| Finance attachment | 1,056 | 1,083 | 1,110 |
| Input attach rate | 1,052 | 1,083 | 1,114 |
| Agent cost | 1,083 | 1,083 | 1,083 (absorbed by agent, not platform) |

**GMV and take rate dominate.** Everything else is secondary. This is why the strategy is obsessed with
liquidity and with the 1–3% fee band.

---

## 9. The three numbers to watch weekly

| Metric | Target |
|---|---|
| **Contribution margin per transaction** | Positive from month 6 |
| **Second-season repeat rate** | ≥40% by month 18 |
| **Blended take rate** | ≥1.5% by month 24 |

If any of these three is below target for two consecutive quarters, the model needs a structural change,
not operational tinkering.
