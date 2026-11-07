# 03.1 · Kenya and M-Pesa

*Part of [03 · International Models](README.md)*

> **Why study it.** M-Pesa is the closest thing to a proven template for financial inclusion in a
> low-income, agriculture-dependent, agent-based African economy. It is also the source of the only
> rigorous causal estimate of mobile money's effect on poverty.

---

## 1. Scale (FY2026)

| Indicator | Value |
|---|---|
| M-Pesa one-month-active customers (Kenya) | **40.99 million** |
| Transaction value, FY26 | **KSh 41.68 trillion (~US$323 bn)** ≈ 2.4× Kenya's GDP |
| Transaction count, FY26 | 46.4 billion (~136 million/day) |
| M-Pesa revenue | KSh 182.7 bn (~US$1.42 bn) |
| Share of transactions that are free | **57.8%** (~26.8 bn transactions) |
| Agents | **333,011** |
| Merchants | 3.13 million |
| Market share of mobile money subscriptions | ~89% |
| National active mobile money subscriptions | 53.4–54.0 million (penetration 100–101%) |
| Mobile money agents nationally | ~572,000–602,000 |
| Agent commission pool | ~KSh 37.4 bn/year |

---

## 2. The causal evidence on poverty

**Suri & Jack (2016), *Science*:** access to M-Pesa increased per-capita consumption and lifted
**~194,000 households — about 2% of Kenyan households — out of extreme poverty** (below US$1.25/day)
between 2008 and 2014.

Critically, the **mechanism was not credit or savings** — it was **improved risk-sharing**:
- M-Pesa users could receive more remittances, from a wider network, faster.
- After a negative income shock, non-users' consumption fell ~7%; users' consumption did not.
- Effects were **largest for female-headed households**, partly because mobile money gave women a
  private store of value.
- ~185,000 women moved out of subsistence agriculture into business or retail.

**What this means for Ethiopia:** the first-order benefit of digital money is **resilience**, not
entrepreneurship. Do not over-promise that a payment rail creates businesses. Do promise that it
reduces the catastrophic cost of a shock — which, in a country where a single drought or illness
forces asset sales, is the more valuable claim.

**Caveats to hold honestly:**
- This is one observational study using geographic variation in agent rollout, not an RCT.
- The effect is 2% of households, not 20%. Mobile money alone is not a poverty strategy.
- Kenya's context (a dominant operator with aligned incentives, high literacy relative to Ethiopia,
  strong banking sector) differs materially.

---

## 3. What made M-Pesa work

| Factor | Detail | Ethiopia status |
|---|---|---|
| **Agent network density** | 333,011 M-Pesa agents; ~572,000 nationally — roughly one per 100 adults | telebirr 320,000 agents, M-Pesa ~30,000. Comparable in count, lower in rural density and activity |
| **Free/low-cost tiers** | 57.8% of transactions are free — drives habit formation | telebirr and M-Pesa Ethiopia both use free P2P tiers; EthSwitch interoperability reduces cost |
| **Single dominant operator with aligned incentives** | Safaricom had both the network and the licence | Ethiopia has two operators and a state incumbent; competition may accelerate price falls |
| **Regulatory forbearance then formalisation** | Kenya let M-Pesa grow before regulating tightly | Ethiopia regulated first (2020 directives), then opened — a different path |
| **Cash-in/cash-out as the core product** | The killer feature was depositing and withdrawing cash, not paying bills | Identical need in Ethiopia (58% phone ownership, cash economy) |
| **Interoperability** | M-Pesa ↔ banks ↔ Airtel Money | Achieved in Ethiopia via EthSwitch (M-Pesa integrated Oct 2025) |
| **Trust** | Brand + agent relationships + dispute resolution | Still the weakest link in Ethiopia after aid diversion and fraud reports |

---

## 4. What does *not* transfer

| Kenyan condition | Ethiopia's reality | Consequence |
|---|---|---|
| Mobile money penetration >100% of population | 9.5–19.4% of adults have a mobile money account | The market is an order of magnitude less mature |
| Adult literacy near-universal | 90% learning poverty | USSD/IVR and agents are mandatory |
| Agent density built over 19 years | telebirr is 5 years old; M-Pesa Ethiopia 3 | Agent profitability (and therefore density) is not yet proven |
| A single operator with clear incentives | Two operators + a state incumbent + a switch | Coordination costs are higher; interoperability is both blessing and complexity |
| Kenya's banking sector as a partner | Ethiopia's banks are thinner and partly state-directed | Credit partnerships will be slower |
| M-Pesa is a standalone success | Ethiopia's wallets are embedded in telecom operators with other priorities | Agri-specific product development may be slow inside a telco |

---

## 5. The agent economics lesson

M-Pesa pays out roughly **KSh 37.4 bn per year in commissions to 333,011 agents** — about
**KSh 112,000 (~US$870) per agent per year**, or ~US$72/month. That is a modest but real income.

**In Ethiopia**, telebirr's 320,000 agents and M-Pesa's ~30,000+ agents compete for the same
transactions. If commissions per agent fall below a viable threshold, agents become inactive — which
is why **rural agent density lags urban** despite nominal agent counts.

**Design implication for an agriculture platform:** agents must have **more than one revenue stream.**
A cooperative agent who earns from telebirr float, plus platform commissions on listings and
logistics, plus input sales, plus a small advisory fee, is viable. An agent who earns only from
mobile money float in a low-transaction rural area is not. **Bundling is what makes the agent
network economically sustainable** — and the agent network is what makes the platform reach farmers.

---

## 6. Applying the Kenyan playbook to Ethiopia

| Kenyan play | Ethiopian adaptation |
|---|---|
| Launch with P2P transfer as the wedge | Payments are taken; use **marketplace matching** as the wedge instead |
| Build an agent network for cash-in/out | Ride existing telebirr/M-Pesa agents; add a **cooperative agent** tier |
| Keep the base tier free | Free price information and free listings; charge on settlement only |
| Use interoperability as a growth lever | EthSwitch integration from day one (both wallets) |
| Cross-sell credit on transaction history | Same — but only after 2 seasons of data |
| Use a dominant brand for trust | Borrow trust from cooperatives, government programmes and Fayda |

---

## Key takeaways

1. M-Pesa processed ~2.4× Kenya's GDP in a year, with **57.8% of transactions free** — volume, not
   margin per transaction, is the model.
2. The measured poverty effect (~2% of households) runs through **risk-sharing**, and it is largest
   for **female-headed households**.
3. **Agents are the distribution system.** Their viability depends on multiple revenue streams, not
   mobile money float alone.
4. Ethiopia has the rails but not the penetration, literacy or agent density. Do not assume Kenyan
   behaviour; **build the agent economics deliberately.**
5. Take payments as given; the open wedge is **matching, logistics and credit**, not money transfer.
