# 10 · Sources, Method and Confidence

*What this repository is based on, how it was verified, and how much to trust each figure*

---

## Files in this section

| File | Contents |
|---|---|
| [`01-methodology.md`](01-methodology.md) | How the research was done; confidence grading |
| [`02-source-register.md`](02-source-register.md) | Full source list by topic |
| [`03-figures-and-corrections.md`](03-figures-and-corrections.md) | Every headline figure with its source and correction history |
| [`04-gaps-and-unknowns.md`](04-gaps-and-unknowns.md) | What we could not verify |

> Machine-readable versions: [`../data/indicators.csv`](../data/indicators.csv) and
> [`../data/fact-ledger.md`](../data/fact-ledger.md).

---

## Confidence grading (defined in the root README)

| Grade | Meaning | Typical sources |
|---|---|---|
| 🟢 **A** | Official statistic, published, dated, from the responsible authority | NBE, MoF, CSA, World Bank, IMF, ITU |
| 🟡 **B** | Reputable secondary source citing an official figure; or a well-established industry estimate | News reporting of official data, operator disclosures, established research |
| 🟠 **C** | Single-source, or from a party with an interest in the number; directionally reliable | Company statements, advocacy reports, market research |
| ⚪ **D** | Author's estimate, model output, or judgement; not externally verifiable | Projections, unit economics, scenarios in this repository |

**Rule used throughout:** no figure is presented as fact without a grade. Where sources conflict, both
figures are shown.

---

## The corrections applied to the source brief

The original draft contained several outdated or incorrect figures. All were corrected:

| Claim in draft | Verified figure | Source | Grade |
|---|---|---|---|
| Internet users 43 m (34%) | **29.5 m (21.7%)** | DataReportal 2026 | 🟡 |
| telebirr 21.8 m users | **60.59 m registered** | Ethio Telecom 2026 | 🟡 |
| Fayda 37 m registered | **53.4 m registered** (53.4 m; ~52.4 m in some sources) | NIDP 2026 | 🟡 |
| Corruption rank ~99 | **CPI 2025: 38/100, rank 96/182** | Transparency International | 🟢 |
| Electricity access ~50% | **65% any access; 44% Tier 1+; 29.3% grid** | World Bank / ESMAP | 🟢 |
| Account ownership ~35% | **49% of adults** | Global Findex | 🟢 |
| M-Pesa Ethiopia "just launched" | **5.2 m active users** (Oct 2026) | Safaricom | 🟡 |
| GDP growth 6.5% | **9.2% (FY2025/26 est.)** | IMF | 🟡 |
| Inflation ~20% | **15.3% (Jul 2026)** | IMF/NBE | 🟡 |
| Exchange rate ~57 birr/USD | **~161 birr/USD** | Market/NBE | 🟡 |
| Poverty ~24% | **43% below $3/day**; ~$2.15/day rate lower | World Bank | 🟡 |
| Coffee exports $1.4 bn | **$2.653 bn (FY2024/25)** | ECTA | 🟡 |
| "Digital Ethiopia 2025" | **Digital Ethiopia 2030** (adopted Dec 2025) | Government | 🟡 |

**Additionally, several figures in the draft were directionally right but imprecise** — e.g. "agriculture
is about 40% of GDP" (actual: 31.6–34.9% depending on base year).

---

## What the research added beyond the brief

| Area | What was added |
|---|---|
| Payments | NBE licensing framework, escrow options, PSI capital requirements, EthSwitch roles |
| Identity | Fayda pricing (US$0.05–0.10/verification), bank-link mandate, coverage gaps by region |
| Connectivity | 4G coverage vs. usage gap; USSD/IVR as permanent channels |
| Agriculture | DAR 2032 targets, 8028 performance, site-specific fertiliser evidence, Lersha's scale |
| Finance | Credit demand vs. supply (2% of ETB 2.58 trn), NAFIR, collateral constraints |
| Trade | ECX online trading, Directive 1106/2025, EUDR traceability, coffee value distribution |
| Competition | Jumia's failure pattern, e-commerce platform revenue distribution, startup funding levels |
| Conflict | Renewed fighting (late 2026), World Bank damage estimate, Oxford GDP projection |
| Macroeconomy | Rebased GDP, FX trajectory, inflation, FDI, external debt |

---

## How to read this repository

| If you want… | Read… |
|---|---|
| The argument in 10 minutes | [`../EXECUTIVE-SUMMARY.md`](../EXECUTIVE-SUMMARY.md) |
| The diagnosis | [`../01-context/`](../01-context/) |
| Why agriculture | [`../02-opportunities/`](../02-opportunities/) |
| What other countries did | [`../03-international-models/`](../03-international-models/) |
| What will go wrong | [`../04-constraints/`](../04-constraints/) |
| The architecture | [`../05-ecosystem/`](../05-ecosystem/) |
| The money | [`../06-business-model/`](../06-business-model/) |
| The plan | [`../07-implementation/`](../07-implementation/) |
| The risks | [`../08-risks/`](../08-risks/) |
| The answer | [`../09-recommendation/`](../09-recommendation/) |
| The numbers | [`../data/`](../data/) |

---

## Limitations, stated up front

1. **No primary fieldwork was conducted.** No farmers, agents, buyers or officials were interviewed for
   this research. Every claim about behaviour is an inference from secondary evidence.
2. **Several key figures are contested.** E-commerce market size, agricultural credit demand, and
   post-harvest loss rates vary by an order of magnitude across sources.
3. **The security situation is fluid.** Figures and assessments reflect late 2026 and will change.
4. **Financial projections are illustrative.** All ⚪ figures are modelled, not observed.
5. **The source brief was a draft, not a study.** It contained errors that have been corrected, but its
   framing (a modular national ecosystem) has been retained and tested rather than replaced.

**This is a research synthesis for decision support, not an investment prospectus, a feasibility study,
or a substitute for due diligence.**
