# 03 · International Models

*What Ethiopia can borrow, what it cannot, and what the evidence actually says*

---

## Files in this section

| File | Model | Core lesson |
|---|---|---|
| [`01-mobile-money-kenya.md`](01-mobile-money-kenya.md) | **M-Pesa, Kenya** | Agents beat branches; interoperability and free tiers drive volume; poverty effects run through risk-sharing |
| [`02-india-stack.md`](02-india-stack.md) | **India Stack** (Aadhaar, UPI, ONDC, AA, DBT) | Composable layers; mandated rails; open commerce protocol |
| [`03-rwanda-irembo.md`](03-rwanda-irembo.md) | **Rwanda, Irembo** | PPP e-government; the agent layer is what makes it inclusive |
| [`04-estonia-xroad.md`](04-estonia-xroad.md) | **Estonia, X-Road** | Once-only principle; decentralised exchange; start with government itself |
| [`05-super-apps-china-sea.md`](05-super-apps-china-sea.md) | **WeChat, Alipay, Grab, Gojek** | One high-frequency wedge, then attach services; own the payment moment |
| [`06-jumia-african-ecommerce.md`](06-jumia-african-ecommerce.md) | **Jumia** | The cautionary tale: control logistics, refuse negative-margin GMV |
| [`07-african-comparators.md`](07-african-comparators.md) | **Nigeria BVN, Ghana, Tanzania, Rwanda e-Soko** | What peer African markets got right and wrong |
| [`08-synthesis.md`](08-synthesis.md) | — | The transferable design principles, ranked by relevance to Ethiopia |

---

## Why these models and not others

The selection criterion is **structural similarity**, not prestige:

| Model | Similar to Ethiopia because | Different because |
|---|---|---|
| Kenya | Mobile-first, agent-based, low-income, agriculture-heavy, informal retail | 100%+ mobile money penetration; 19 years of network building; single dominant operator with strong incentives |
| India | Federal, low-income at the start, huge, rural, agriculture-dependent | 1.4 bn people; a mandated single switch operator (NPCI); a mature banking system; strong state implementation capacity |
| Rwanda | Small, low-income, post-conflict, PPP-friendly, agriculture-heavy | Very high state capacity; political continuity; smaller and easier to digitise |
| Estonia | Post-Soviet legacy institutions, small, resource-constrained | 1.3 m people; pre-existing digital banking; EU legal framework |
| China/SEA | Mobile-first, underbanked at the start, dense informal commerce | Rising incomes; enormous VC subsidies; either a messaging monopoly or a ride-hailing wedge |
| Jumia | Same continent, same constraints, same ambitions | Pan-African spread diluted focus |

---

## The synthesised principles (full reasoning in [`08-synthesis.md`](08-synthesis.md))

| # | Principle | Primary source | Transfer confidence to Ethiopia |
|---|---|---|---|
| 1 | **Shared infrastructure beats vertical apps** — identity, payments and data lower the cost of every downstream service | India, Estonia | 🟢 High — Fayda + EthSwitch already exist |
| 2 | **Physical agent networks are the actual distribution system** for low-literacy, cash-based, low-connectivity markets | Kenya, Rwanda, India | 🟢 High — Lersha's 4,000+ agents prove it |
| 3 | **Interoperability and free/low cost tiers drive volume**, not per-transaction margin maximisation | Kenya (57.8% of M-Pesa transactions are free), India (UPI) | 🟢 High |
| 4 | **Start with one high-frequency wedge**, then attach services | China/SEA, India | 🟢 High |
| 5 | **Anchor on the state's plan; do not fight it** | Rwanda, India | 🟢 High |
| 6 | **Privacy and legal equivalence must be designed in, not retrofitted** | Estonia (Digital Signatures Act 2000) | 🟡 Medium — Proclamation 1321/2024 exists but is untested |
| 7 | **Traceability pays** — origin, grade and provenance command a premium and are now regulatory requirements (EUDR) | Coffee, India ONDC | 🟢 High |
| 8 | **Do not chase GMV**; narrow to profitable core | Jumia | 🟢 High — Ethiopia's startups already demonstrate this |
| 9 | **Cash remains king for years**; design cash-in/cash-out, not cashless | Kenya (agents), Rwanda (Irembo cash payments) | 🟢 High — 1% of Ethiopian adults buy online |
| 10 | **Super-apps require either a monopoly or a subsidy**; do not attempt in a low-ARPU market | China/SEA | 🟢 High |

---

## A note on evidence quality

Where this section cites impact figures, it distinguishes:

- **Causal estimates** (Suri & Jack's 2% poverty reduction — a quasi-experimental panel study);
- **Official aggregates** (UPI transaction counts, Aadhaar enrolments — administrative data);
- **Self-reported or advocacy figures** (some DBT savings estimates, some vendor statistics);
- **Modelled projections** (market-size forecasts, which are the least reliable).

Ethiopian planning should weight causal estimates and official aggregates heavily and treat vendor
statistics and market forecasts as directional at best.

---

## Read next

- The synthesis and the ten design principles: [`08-synthesis.md`](08-synthesis.md)
- How the principles turn into an architecture: [`../05-ecosystem/`](../05-ecosystem/README.md)
