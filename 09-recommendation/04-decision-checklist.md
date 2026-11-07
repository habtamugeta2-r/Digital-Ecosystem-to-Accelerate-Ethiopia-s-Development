# 09.4 · Decision Checklist

*Part of [09 · Recommendation](README.md)*

A go/no-go instrument. Complete it honestly before committing capital beyond Phase 0.

---

## A. Legal and regulatory readiness

| # | Question | Evidence required | Status |
|---|---|---|---|
| A1 | Is the entity incorporated, with clean ownership? | Registration certificate; cap table | ☐ |
| A2 | Is there a **written** NBE position on escrow via bank/PSI? | Correspondence | ☐ |
| A3 | Is there a written position on multi-wallet agency? | Correspondence | ☐ |
| A4 | Is there a written position on data sharing with lenders? | Correspondence | ☐ |
| A5 | Is there a written position on LSP lending/origination? | Correspondence | ☐ |
| A6 | Is the DPIA complete and approved? | Signed document | ☐ |
| A7 | Are terms of service available in the languages used in the pilot? | Documents | ☐ |
| A8 | Is a commodity trading licence required (if acting as principal)? | Decision recorded | ☐ |
| A9 | Is there an insurance distribution agreement (if selling insurance)? | Contract | ☐ |

**A2–A5 are blocking.** Ambiguity here is more dangerous than refusal, because it invites a
build-then-prohibit outcome.

---

## B. Infrastructure readiness

| # | Question | Evidence | Status |
|---|---|---|---|
| B1 | Is Fayda verification working in production? | Successful test at scale | ☐ |
| B2 | Is a USSD shortcode live? | Verified session | ☐ |
| B3 | Is an SMS gateway live with delivery reporting? | Delivery logs | ☐ |
| B4 | Is IVR live in at least 2 languages? | Test call recording | ☐ |
| B5 | Is at least one payment rail live in production? | Test transaction | ☐ |
| B6 | Is a second rail available for redundancy? | Contract or test | ☐ |
| B7 | Is there an escrow account at a licensed institution? | Account opening + agreement | ☐ |
| B8 | Is the ledger reconciled against a bank statement? | Reconciliation record | ☐ |

---

## C. Market readiness

| # | Question | Evidence | Status |
|---|---|---|---|
| C1 | Is the pilot region selected with a named woreda list? | Document | ☐ |
| C2 | Is the security situation acceptable in all pilot woredas? | Security assessment | ☐ |
| C3 | Are ≥2 cooperatives signed with member lists? | Signed MoUs | ☐ |
| C4 | Are ≥3 anchor buyers committed with volumes? | Signed LOIs | ☐ |
| C5 | Are collection points identified with agreements? | Contracts | ☐ |
| C6 | Are grading standards agreed? | EQA or equivalent | ☐ |
| C7 | Is the crop calendar confirmed? | Season plan | ☐ |
| C8 | Is there a transport partner for each lane? | Contract | ☐ |

---

## D. Operational readiness

| # | Question | Evidence | Status |
|---|---|---|---|
| D1 | Are ≥50 agents recruited and trained? | Training records | ☐ |
| D2 | Are devices distributed and tested? | Asset register | ☐ |
| D3 | Is the dispute procedure written and staff trained? | SOP + training log | ☐ |
| D4 | Is the reconciliation procedure operational? | Daily process evidenced | ☐ |
| D5 | Is there a cash-in/cash-out procedure with limits? | SOP | ☐ |
| D6 | Is there insurance for cargo and collection points? | Policy | ☐ |
| D7 | Is there a business continuity plan? | Document | ☐ |
| D8 | Is there an incident response plan? | Document | ☐ |

---

## E. Team readiness

| # | Question | Evidence | Status |
|---|---|---|---|
| E1 | Is the CTO hired and architecturally aligned? | Signed offer / contract | ☐ |
| E2 | Is the **field operations lead** hired? | Signed offer | ☐ |
| E3 | Is there an agronomist with content credibility? | Contract | ☐ |
| E4 | Is there compliance/legal capability? | Internal or retained | ☐ |
| E5 | Is there a credit/risk capability (for Phase 2)? | Plan to hire | ☐ |
| E6 | Is there a named owner for every risk in the register? | Register | ☐ |

---

## F. Financial readiness

| # | Question | Evidence | Status |
|---|---|---|---|
| F1 | Is ≥ETB 20 m committed for Phases 0–1? | Bank statement | ☐ |
| F2 | Is there 18 months of runway at planned burn? | Financial model | ☐ |
| F3 | Is the budget built in birr with FX assumptions? | Model | ☐ |
| F4 | Is there a contingency of ≥10%? | Budget | ☐ |
| F5 | Are funding tranches tied to gates? | Term sheet | ☐ |
| F6 | Is there a plan for the 2× safety margin? | Document | ☐ |

---

## G. Strategic readiness

| # | Question | Evidence | Status |
|---|---|---|---|
| G1 | Is the opportunity scoring still valid? | Re-scored | ☐ |
| G2 | Has a state platform been announced? | Checked | ☐ |
| G3 | Has a well-funded competitor entered? | Checked | ☐ |
| G4 | Is there a partnership strategy for the state? | Document | ☐ |
| G5 | Is there a plan if the state competes? | Scenario B plan | ☐ |
| G6 | Is the cooperative equity tranche reserved? | Shareholder agreement | ☐ |
| G7 | Is the brand name tested in the pilot region? | Test results (MeroMero is a placeholder) | ☐ |

---

## Scoring

| Section | Items | Minimum to proceed |
|---|---|---|
| A. Legal | 9 | **All A1–A8 yes** |
| B. Infrastructure | 8 | **All yes** |
| C. Market | 8 | **≥6 yes, including C3 and C4** |
| D. Operational | 8 | ≥6 yes |
| E. Team | 6 | **All E1, E2 yes** |
| F. Financial | 6 | **F1, F2, F5 yes** |
| G. Strategic | 7 | ≥5 yes |

**If any blocking section fails, delay. Delaying a launch is cheap; launching without escrow is not.**

---

## The five questions that matter most

If everything else is ambiguous, these five determine whether to proceed:

1. **Can the platform settle in escrow legally and practically?**
   *(If no: the model does not work.)*

2. **Do farmers earn measurably more, net of fees and transport?**
   *(If no: nothing else matters.)*

3. **Will they come back a second season?**
   *(If no: acquisition cost destroys the economics.)*

4. **Can an agent earn a living from this?**
   *(If no: the distribution network collapses.)*

5. **Is capital available for 3 years without revenue dominating?**
   *(If no: the timeline is impossible.)*

---

## The stop rule

**If, after one full season and ≥3,000 transactions, the net price gain is below 3% and the repeat rate
is below 20%, stop.** Reallocate the team, return remaining capital, and publish what was learned.

**A well-documented failure is worth more to Ethiopian agriculture than an undignified decline.**
