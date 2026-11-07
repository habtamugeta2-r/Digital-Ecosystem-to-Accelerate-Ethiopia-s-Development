# 10.1 · Methodology

*Part of [10 · Sources](README.md)*

---

## 1. The approach

| Stage | Activity | Output |
|---|---|---|
| 1. Receive | Source brief: a ~4,000-word draft on a digital ecosystem for Ethiopia | Framing and hypotheses |
| 2. Decompose | Split into claims that can be verified | ~60 factual claims |
| 3. Verify | Search for each claim against authoritative sources | Corrections log |
| 4. Extend | Research the questions the brief raised but did not answer | 39 searches across 8 topics |
| 5. Structure | Organise into a 10-part repository with a consistent analytical frame | This repository |
| 6. Test | Apply scoring, sensitivity analysis and scenario planning to the conclusions | Ranking and scenarios |
| 7. Bound | State confidence, gaps and limitations | This section |

---

## 2. Research sources by tier

### Tier 1 — Official statistics (grade 🟢 A)

| Source | Used for |
|---|---|
| National Bank of Ethiopia (NBE) | Inflation, FX, credit, payment system |
| Ministry of Finance (MoF) | Budget, debt, GDP |
| Central Statistical Service (CSA) | Population, agriculture, employment |
| Ethiopian Statistics Service household surveys | Poverty, consumption |
| World Bank / IMF | GDP, poverty, electricity, Findex, WDI |
| ITU / GSMA | Connectivity, mobile penetration |
| Transparency International | Corruption Perceptions Index |
| UNDP | Human development, UHC index |
| ECTA / Ministry of Trade | Export values |
| National ID Program (NIDP) | Fayda registration |
| Ethio Telecom / Safaricom | Subscribers, coverage, telebirr/M-Pesa |

### Tier 2 — Reputable secondary (grade 🟡 B)

| Source | Used for |
|---|---|
| DataReportal | Digital adoption statistics |
| Shega | Ethiopian startup and tech ecosystem |
| Addis Standard / Capital Ethiopia / The Reporter | Policy and business reporting |
| Birr Metrics / Ecofin | Economic analysis |
| CGIAR / IFPRI / AICCRA | Agricultural research |
| CGSPACE / DAR Playbook | Digital agriculture programme design |
| World Bank Irembo case study | Rwanda comparison |
| e-Estonia | X-Road and digital government |
| Suri & Jack (Science) | M-Pesa poverty impact |

### Tier 3 — Single-source or interested party (grade 🟠 C)

| Source | Caution |
|---|---|
| Company press releases | Self-reported; favourable framing |
| Market research firms (IMARC, ecdb) | Estimates vary by orders of magnitude |
| Advocacy reports | Directional, not precise |
| Startup self-disclosures | Unaudited |

### Tier 4 — Author's analysis (grade ⚪ D)

All projections, unit economics, scores, scenario probabilities and recommendations.

---

## 3. Verification rules applied

| Rule | Application |
|---|---|
| **Two-source rule** | Any figure central to a conclusion must appear in ≥2 independent sources |
| **Recency rule** | Figures >3 years old are flagged; macro figures >1 year old are flagged |
| **Conflict disclosure** | Where sources disagree materially, both are shown (e.g. e-commerce market size) |
| **Source-of-source** | Where a news article cites an official figure, the official figure is preferred |
| **Interest disclosure** | Where the source benefits from the number, the grade drops |
| **No precision without a source** | Avoid false precision (e.g. "exactly 2,632 kg/ha" → "~2.6 t/ha") |

---

## 4. What was searched (topic list)

| Topic | Questions |
|---|---|
| Macroeconomy | GDP, growth, inflation, FX, debt, FDI, rebasing |
| Poverty and human capital | Poverty rates, food insecurity, IDPs, education, health |
| Digital adoption | Internet, mobile, smartphones, 4G/5G, electricity |
| Identity | Fayda registration, pricing, coverage, FaydaVerse |
| Payments | telebirr, M-Pesa, EthSwitch, EthioPay, NBE strategy, licensing |
| Agriculture | Production, yields, losses, cooperatives, DAR, ATI, 8028, Lersha, ECX, EUDR |
| Finance | Account ownership, credit demand/supply, NAFIR, collateral, insurance |
| Trade and logistics | Roads, corridor, freight costs, Djibouti dependency |
| Competition | Jumia, e-commerce platforms, startup funding |
| Conflict | Tigray, Amhara, Afar, economic cost |
| International models | Kenya, India, Rwanda, Estonia, China, SEA, Nigeria, Ghana, Tanzania |

**Total searches: 39.** Documented in the source register.

---

## 5. Analytical framework

| Framework | Where used |
|---|---|
| **System-of-constraints diagnosis** | `01-context/` — identifying the binding constraint |
| **8-criterion weighted scoring** | `02-opportunities/` — ranking opportunity areas |
| **Sensitivity analysis** | `02-opportunities/06` — testing rank stability |
| **Comparative case analysis** | `03-international-models/` — transfer principles |
| **Constraint-to-decision mapping** | `04-constraints/` — forcing design choices |
| **Layered architecture** | `05-ecosystem/` — separation of concerns |
| **Unit economics** | `06-business-model/` — viability |
| **Stage-gate process** | `07-implementation/` — controlled commitment |
| **Risk register + scenarios** | `08-risks/` — preparedness |

---

## 6. Confidence grading in practice

Examples of each grade as used in this repository:

| Grade | Example | Why |
|---|---|---|
| 🟢 A | "Fayda registered 53.4 m" | Official NIDP figure, widely reported |
| 🟡 B | "Internet penetration 21.7%" | DataReportal, derived from ITU/operator data |
| 🟠 C | "E-commerce market US$29.78 bn" | Single commercial source; conflicts with other estimates by 400× |
| ⚪ D | "ETB 986 m revenue at ETB 40 bn GMV" | Author's model |

---

## 7. What the methodology cannot do

| Limitation | Consequence |
|---|---|
| **No fieldwork** | Behavioural claims are inferences |
| **No access to proprietary data** | Bank, telco and platform internal data unavailable |
| **No government interviews** | Policy intentions inferred from documents |
| **Fast-moving environment** | Figures dated late 2026; superseded within months |
| **English-language bias** | Amharic-language sources under-represented |
| **Desk research** | Cannot observe what people actually do, only what they say or what is reported |

**The most important gap: this research knows what the data says, but not what a farmer in Arsi would
actually do.** Only a pilot can answer that.

---

## 8. How to update this repository

| Trigger | Update |
|---|---|
| New official statistic | `data/indicators.csv` + affected files |
| Policy change (NBE, NIDP, payments) | `04-constraints/03`, `05-ecosystem/02` |
| Security change | `08-risks/02` |
| Pilot results | `07-implementation/02`, `06-business-model/02` |
| Competitor entry | `02-opportunities/06`, `06-business-model/05` |
| Funding round | `06-business-model/04` |

**Suggested cadence: quarterly for figures, annual for the analysis.**
