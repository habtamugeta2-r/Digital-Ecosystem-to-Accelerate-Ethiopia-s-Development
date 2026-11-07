# 07.4 · Phase 3 — Scale (Months 36–54)

*Part of [07 · Implementation](README.md)*

From a regional platform with services to a national platform with a brand.

---

## Objective

| Target | Value |
|---|---|
| Regions | 6–7 |
| Commodities | 6–7 (add sorghum, pulses, coffee, horticulture) |
| Active farmers | 400,000 |
| GMV (annualised) | ETB 36 bn |
| EBITDA | Positive |
| Lenders | 3–4 |
| Third-party integrations | 5+ |

---

## What changes in Phase 3

| Change | Why it matters |
|---|---|
| **From push to pull** | Farmers start referring others; acquisition cost falls |
| **From manual to automated ops** | Dispatch, settlement and dispute handling become self-service |
| **From single-commodity to portfolio** | Seasonality is smoothed; revenue is less lumpy |
| **From fee-only to fee+finance** | Blended margin rises above 1.2% |
| **From project to institution** | Brand, governance, audited accounts, regulator relationships |

---

## The national expansion map

| Region | Commodities | Priority | Constraint |
|---|---|---|---|
| Oromia | Wheat, maize, teff, coffee | Core | None |
| Amhara (secure) | Teff, wheat, sesame, pulses | High | Conflict risk |
| Sidama/SNNPR | Coffee, maize, pulses, horticulture | High | Coffee quality infrastructure |
| Addis Ababa | Demand hub | Core | None |
| Dire Dawa / Harari | Sorghum, livestock (later) | Medium | Corridor dependency |
| Benishangul-Gumuz | Maize, sorghum, sesame | Low | Infrastructure |
| Gambella | Maize, sorghum | Low | Very low Fayda coverage (~28,300 registered) |
| Somali | Livestock, maize | **Deferred** | Security; pastoral systems |
| Tigray | Teff, sesame | **Deferred** | Post-conflict recovery |
| Afar | Livestock, salt | **Deferred** | Pastoral; security |

**Rule:** defer any region where (a) active conflict, (b) Fayda coverage <30%, or (c) road access
unreliable in the rainy season.

---

## Adding commodity verticals

| Commodity | Value | Complexity | Fee potential | Start |
|---|---|---|---|---|
| Wheat | High volume | Low | 1.0–1.5% | Phase 1 |
| Maize | High volume | Low | 1.0–1.5% | Phase 1 |
| Teff | Highest value staple | Medium (quality) | 1.5–2.5% | Phase 1–2 |
| Sorghum | Volume, feed | Low | 1.0–1.5% | Phase 3 |
| Pulses (chickpea, haricot) | Export | Medium (grade) | 2–3% | Phase 3 |
| Sesame | Export | Medium | 2–3% | Phase 3 |
| Coffee (cherry) | Very high value | High (wet mill, quality) | 2–4% + traceability | Phase 3 |
| Horticulture | High value | Very high (cold chain) | 3–5% | Phase 4 |
| Livestock | High value | Very high (weight, health) | 2–4% | Phase 4–5 |

**The commodity sequence matters more than the region sequence.** Each new commodity requires new
grading standards, new buyers, new advisory content and new logistics — roughly 6–9 months of work.

---

## The coffee opportunity (Phase 3, high priority)

| Fact | Implication |
|---|---|
| Coffee is Ethiopia's largest export (~US$2.65 bn FY2024/25) | Huge value pool |
| EUDR requires plot-level traceability by end-2025/2026 | **Mandatory compliance market** |
| Farmgate price ~60% of FOB vs. Vietnam's 92% | Enormous margin captured upstream |
| Farmers captured +62% vs. exporters' +218% (2019–23) | Value distribution is badly skewed |
| 5+ million households depend on coffee | Largest single smallholder cohort |

**The EUDR traceability service is the clearest paid use case in Ethiopian agriculture.** Exporters
must prove the geolocation of the plot, the chain of custody, and the absence of deforestation. A
platform with plot polygons, transaction records and cooperative relationships can sell this as a
compliance service — and the buyer (exporter) has no choice but to pay.

**Model:** ETB 2–5 per kg certified, or a fixed fee per container. At 300,000 tonnes exported, even
partial capture is significant.

---

## Organisational maturation

| Dimension | Phase 2 | Phase 3 |
|---|---|---|
| Structure | Functional, flat | Regional P&Ls with regional leads |
| Decision rights | CEO decides most things | Delegated budgets; regional autonomy |
| Governance | Founder board | Independent chair; audit committee |
| Reporting | Monthly management accounts | Quarterly audited; IFRS |
| Risk | Informal | Formal risk register; internal audit |
| HR | Hiring by network | Structured recruiting; performance system |
| Culture | Mission-driven, informal | Mission + process; documented playbooks |

**The hardest transition in this phase is from "we" to "the company."** Founders who cannot delegate
regional operations will cap the platform at two regions.

---

## Technology debt in Phase 3 (a real risk)

The modular monolith from Phase 1 will come under strain:

| Symptom | Threshold | Response |
|---|---|---|
| Deploy times | >30 min | Split build pipeline |
| Report query times | >10 s | Read replica; materialised views |
| Single database size | >1 TB | Partitioning; archival |
| Deployment failures | >10% of releases | Test coverage; staging environment |
| On-call incidents | >5/month | SLOs; incident process |
| Team blocked on monolith | >3 teams editing same module | Extract a service (only then) |

**Do not split into microservices on schedule. Split when the pain is measurable.** Premature
distribution is a bigger risk than a large monolith.

---

## Team in Phase 3

| Function | FTE |
|---|---|
| Engineering | 20 |
| Product/design | 7 |
| Data/analytics | 5 |
| Field operations | 22 |
| Agronomy | 8 |
| Credit and risk | 9 |
| Trading desk | 8 |
| Finance | 7 |
| Compliance/legal | 4 |
| HR/admin | 5 |
| Management | 5 |
| **Total** | **100** |

---

## Budget (ETB m, 18 months)

| Category | Amount |
|---|---|
| Salaries | 138.0 |
| Field operations | 30.0 |
| Technology and comms | 24.0 |
| Cooperative and agent onboarding | 18.0 |
| Credit operations | 30.0 |
| Marketing and brand | 15.0 |
| Legal, audit, compliance | 9.0 |
| Office, equipment, admin | 12.0 |
| Contingency | 15.0 |
| **Total** | **291.0** |
| Revenue offset | (362.0) |
| **Net** | **+71.0 (cash positive)** |

---

## Gate 3 → 4

| # | Criterion | Threshold |
|---|---|---|
| 1 | Active farmers | ≥350,000 |
| 2 | GMV | ≥ETB 25 bn annualised |
| 3 | EBITDA | Positive for 4 consecutive quarters |
| 4 | Regions contribution-positive | ≥4 of 6 |
| 5 | Lender panel | ≥3, no single lender >50% |
| 6 | Repeat rate | ≥55% |
| 7 | Loan repayment | PAR-30 <4% |
| 8 | Dispute rate | ≤1.5% |
| 9 | Data completeness | ≥90% verified |
| 10 | API readiness | Public v1 spec published and tested |

---

## Risks specific to Phase 3

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| National conflict expansion | Medium | Severe | Region-level suspension; light assets |
| Commodity price collapse | Medium | High | Fee in % not fixed; programme revenue |
| Lender concentration | Medium | High | 3+ lenders; diversify products |
| Change in government policy | Medium | Severe | Cooperative equity; partnership posture |
| Quality incident (food safety) | Low | Severe | Grading standards; supplier audit; recall plan |
| Key-person departure | Medium | High | Equity retention; documented processes |
| Competitor with deep pockets | Medium | Medium | Data moat; cooperative lock |
