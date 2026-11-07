# 08.5 · Reputational and Ethical Risk

*Part of [08 · Risks](README.md)*

A platform that handles farmers' money, data and credit decisions has ethical obligations that are not
optional extras. This file covers the ways it can cause harm — and what to do about it.

---

## 1. The exclusion problem

Digital platforms systematically exclude the people who most need help: those without IDs, phones,
literacy, or collateral.

| Group | Size | Why excluded | Risk |
|---|---|---|---|
| Women | ~50% of farmers | Lower phone ownership (42% vs 57%); less land title; mobility constraints | Platform widens the gender gap |
| Youth | large | Less land; less cooperative membership | Excluded from agricultural services |
| Pastoralists | millions | Mobile, non-geolocated production | No product fit |
| Illiterate farmers | ~40–50% of adults | Cannot use USSD menus with text | Channel exclusion |
| ID-less | ~80 m unregistered (declining) | Cannot be verified | Hard exclusion |
| Remote/rural | majority | No agent nearby | Coverage exclusion |
| Displaced people | ~3.3 m | No land, no address, no records | Complete exclusion |

**The ethical risk:** a platform that only serves the top 20% of farmers — the ones with land, phones,
literacy and cooperative membership — will *increase* inequality while claiming to reduce it.

### Mitigations

| Measure | Target |
|---|---|
| Women among registered farmers | ≥40% by Phase 2 |
| Women among agents | ≥30% by Phase 2 |
| Female-focused products (group lending, savings) | Phase 2 |
| IVR in all five major languages | Phase 1 |
| Registration without a smartphone | Always |
| Fayda-less fallback (assisted registration) | Phase 1 |
| Explicit measurement and reporting of inclusion gaps | Quarterly |
| Deliberate inclusion of youth (mechanisation, logistics roles) | Phase 3 |

**The test:** if the platform's customer base mirrors the existing distribution of advantage, it has
failed the inclusion test regardless of its impact numbers.

---

## 2. Data ethics

| Risk | Scenario | Mitigation |
|---|---|---|
| **Consent theatre** | Farmers "consent" without understanding | Plain-language consent; IVR explanation; revocation easy |
| **Function creep** | Data collected for trade later used for credit scoring or marketing | Purpose limitation enforced in code |
| **Re-identification** | Aggregate data de-anonymised | Minimum 50 subjects per cell; no plot geometry in aggregates |
| **Surveillance** | Platform becomes a monitoring tool for the state | Data minimisation; contractual limits; public statement |
| **Data as leverage** | Platform withholds data to pressure farmers or lenders | Published data access policy |
| **Breach** | Farmer data leaked | Security programme; 72-hour notification; liability fund |

### The consent principle, stated strongly

Consent must be:
- **Informed** — the farmer understands what, why, to whom, for how long.
- **Specific** — per purpose, per recipient.
- **Revocable** — immediately, without penalty.
- **Visible** — the farmer can see who accessed their data and when.
- **Not coerced** — access to the market cannot depend on granting credit-data consent.

**If a farmer must consent to credit data sharing to sell grain, the consent is not valid.** This is a
design constraint, and it must be enforced in the consent registry, not just in the policy.

---

## 3. Credit ethics

| Risk | Harm | Mitigation |
|---|---|---|
| **Over-indebtedness** | Farmer borrows from platform + MFI + informal lender | Debt exposure check; borrowing caps; credit bureau reporting |
| **Predatory pricing** | Effective APR exceeds informal rates | Publish APR; cap at a stated maximum |
| **Aggressive collection** | Social harm; reputational damage | Collections policy; no public shaming; no asset seizure; grievance mechanism |
| **Exclusion by algorithm** | Women, youth, remote farmers systematically scored low | Fairness testing; human review; alternative data |
| **Insurance misselling** | Farmer pays for cover that doesn't pay out | Basis risk disclosure; simple products; payout statistics published |
| **Debt bondage via input credit** | Farmer must sell to platform to repay | Allow repayment by other means; no forced sale |

### The collections rule

```
Repayment is enforced by:
  1. Automatic deduction at settlement (agreed in advance)
  2. Future access to platform services (a consequence, not a threat)
  3. Cooperative guarantee mechanisms (social, not coercive)
  4. Legal process, as a last resort, for large exposures only

Never:
  - Public disclosure of default
  - Seizure of assets or land
  - Contacting neighbours or employers
  - Harassment of any kind
  - Denying access to advisory or price information
```

---

## 4. Market ethics

| Risk | Harm | Mitigation |
|---|---|---|
| **Displacing traders without alternatives** | Rural unemployment | Recruit traders as buyers/agents |
| **Monopsony power** | Platform becomes the only buyer; can set prices | Publish bid dispersion; guarantee multiple buyers |
| **Price manipulation** | Platform uses its data advantage to trade against farmers | No proprietary trading in Phase 1–2; separation of data and trading |
| **Quality fraud** | Misgrading reduces farmer income | Standard grading; retained samples; farmer right to re-grade |
| **Cooperative capture** | Local elites control the platform's access | Member verification; multiple cooperatives; grievance channel |

**The monopsony risk is the most serious long-term one.** If the platform becomes the dominant buyer in
a region, it has the power to suppress prices — exactly the behaviour it was created to eliminate.

**Structural safeguard:** publish the distribution of winning bids, and require at least three active
buyers per commodity per region. If fewer than three exist, the platform must not operate as the sole
buyer.

---

## 5. Labour and supply chain ethics

| Issue | Risk | Mitigation |
|---|---|---|
| Child labour in supply chains | Reputational; legal | Supplier code; audits where feasible |
| Forced labour | Reputational | Code; grievance mechanism |
| Unsafe transport | Injury; liability | Transport standards; insurance; driver vetting |
| Fair treatment of agents | Precarity | Minimum income support; clear contracts |
| Worker safety at collection points | Injury | Safety SOP; equipment; first aid; insurance |

---

## 6. Reputational risks

| Scenario | Impact | Prevention |
|---|---|---|
| Farmer loses money because of platform error | Severe local trust damage | Guarantee fund; fast resolution; transparency |
| Credit product causes distress | Media coverage; regulator attention | Responsible lending policy; caps; grievance |
| Data breach covered in the press | Loss of trust; regulatory | Security; disclosure; accountability |
| Association with a political actor | Market loss in other regions | Neutrality policy |
| Perceived as a foreign extraction project | Resistance | Local ownership; cooperative equity; local hiring |
| Accused of displacing women traders | Backlash | Include women as agents and buyers |

---

## 7. The ethics of impact claims

| Bad practice | Why it is harmful |
|---|---|
| Claiming yield gains without a counterfactual | Misleads funders; corrupts policy |
| Counting registered users as beneficiaries | Inflates impact |
| Reporting gross price gains (not net) | Overstates farmer benefit |
| Claiming poverty reduction from a pilot | Statistically unsupportable |
| Using "impact" language to justify weak economics | Hides commercial failure |

**Commitment:** all impact claims will use **net** figures, **matched** comparison groups, and **confidence
grades** (A/B/C/D) as defined in the root README.

---

## 8. Governance of ethics

| Mechanism | Frequency | Owner |
|---|---|---|
| Inclusion metrics reported to board | Quarterly | CEO |
| Data protection audit | Annual | DPO |
| Credit fairness testing | Annual | CRO |
| Grievance mechanism review | Quarterly | COO |
| Ethics committee (board-level) | Semi-annual | Board |
| Farmer satisfaction and trust survey | Quarterly | Research |
| Independent impact evaluation | Phase 2 and Phase 4 | External |

---

## 9. The standard to hold

> **Would a farmer who understood exactly what this platform does — the fees, the data, the loans, the
> terms — still choose to use it?**

If the answer requires the farmer not to understand something, the design is wrong.
