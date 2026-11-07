# 07.8 · Operating Playbook (Pilot)

*Part of [07 · Implementation](README.md)*

The practical, week-by-week mechanics of running the pilot. Written so an operations lead can execute
without re-deriving it.

---

## 1. The pilot at a glance

| Item | Value |
|---|---|
| Region | Oromia — 3–5 woredas in Arsi/Bale (wheat) or North Shewa (maize/teff) |
| Cooperatives | 8–12 primary cooperatives |
| Agents | 50–70, clustered |
| Farmers registered | 8,000 |
| Farmers transacting | ≥4,000 |
| Buyers | 3–5 (millers, wholesalers) |
| Collection points | 4–6 |
| Season | 2 harvest cycles (Meher + Belg) |

---

## 2. Pre-launch sequence (weeks −12 to 0)

| Week | Activity | Owner | Output |
|---|---|---|---|
| −12 | Woreda selection; security assessment | Field lead | 5 woredas confirmed |
| −11 | Cooperative shortlist; governance screening | Field lead | 15 candidates |
| −10 | Cooperative meetings; MoU terms | Field lead + legal | 12 MoUs drafted |
| −9 | Buyer meetings; volume commitments | BD | 5 LOIs |
| −8 | Agent candidate identification | Field lead | 100 candidates |
| −7 | Agent selection; background checks | Field lead + compliance | 60 agents |
| −6 | Agent training (3 days) | Field + product | Certified agents |
| −5 | Device distribution; app installation | Ops | 60 devices live |
| −4 | Cooperative record digitisation begins | Field + data | Member lists |
| −3 | Farmer registration campaign (market days, radio) | Field | 2,000 registered |
| −2 | Collection point setup; scales; storage | Ops | 4 points ready |
| −1 | Dry run: 20 farmers, 5 transactions, end-to-end | All | Issues log |
| 0 | **Go / no-go review** | CEO | Launch decision |

---

## 3. The daily operations rhythm

### Morning (07:00–09:00)
- Check overnight escrow settlements and reconcile
- Review new listings and expiring listings
- Confirm truck bookings for the day
- Check IVR/SMS delivery rates
- Review agent support queue

### Midday (09:00–15:00)
- Trading desk: match listings to buyers, confirm bids
- Field: collection point operations, weighing, grading
- Support: farmer and agent calls
- Payments: release settled escrows

### Evening (15:00–18:00)
- Reconcile the day's ledger
- Resolve open disputes
- Update the operations dashboard
- Log incidents

### Weekly (Friday)
- Cohort review: new registrations, first transactions, repeat transactions
- Agent performance review (income, transactions, complaints)
- Buyer satisfaction check
- Price comparison vs. ATI 6077 and local markets
- Escrow reconciliation with the bank partner

### Monthly
- P&L vs. budget
- Unit economics by region and commodity
- Agent income report
- Dispute statistics
- Data quality audit
- Regulatory and compliance check

---

## 4. Standard operating procedures (SOP checklist)

| SOP | Purpose |
|---|---|
| SOP-01 Farmer registration | Identity, plot capture, consent, pin |
| SOP-02 Listing creation | Commodity, grade, quantity, price floor |
| SOP-03 Bid management | Buyer verification, escrow funding, bid validity |
| SOP-04 Contract and confirmation | PIN + IVR recording, terms in local language |
| SOP-05 Weighing and grading | Calibrated scale, sampling protocol, retained sample |
| SOP-06 Dispatch | Truck booking, loading supervision, documentation |
| SOP-07 Delivery and acceptance | Buyer confirmation, quality check, OTP |
| SOP-08 Payment release | Escrow instruction, dual authorisation |
| SOP-09 Dispute resolution | Intake, evidence, adjudication, resolution, appeal |
| SOP-10 Agent management | Onboarding, training, performance, discipline |
| SOP-11 Cash-in/cash-out | Agent float, reconciliation, limits |
| SOP-12 Data quality | Verification rates, correction workflow |
| SOP-13 Incident response | Fraud, theft, injury, data breach |
| SOP-14 Cooperative engagement | Meetings, reporting, grievance |

---

## 5. Dispute resolution procedure

```
  Complaint raised (farmer, buyer, agent, via USSD/phone/agent)
              │
              ▼
  ┌──────────────────────────┐
  │ T+0: Logged & acknowledged│   (automated SMS)
  └────────────┬─────────────┘
               ▼
  ┌──────────────────────────┐
  │ T+1: Evidence gathered    │   weighing ticket, photos, samples, GPS
  └────────────┬─────────────┘
               ▼
  ┌──────────────────────────┐
  │ T+2: First decision       │   ops lead; authority up to ETB 20,000
  └────────────┬─────────────┘
               ▼
        ┌──────┴──────┐
        ▼             ▼
   Accepted      Escalated
        │             │
        ▼             ▼
  T+3 payment   T+5: Panel (ops + agro + finance)
                      │
                      ▼
                T+7: Final decision
                      │
                      ▼
                T+10: Resolution & payment
```

**Service levels:** acknowledgement in 4 hours; first decision in 2 days; final decision in 7 days;
payment within 3 days of decision.

**Principle: the farmer's version of events is the default until contradicted by evidence.** The cost of
occasionally paying a false claim is lower than the cost of losing a community's trust.

---

## 6. Data collection discipline

Every transaction must capture:

| Field | Source | Required |
|---|---|---|
| Farmer FIN (tokenised) | Fayda | ✅ |
| Plot ID | Registry | ✅ |
| Commodity + variety | Listing | ✅ |
| Quantity (farmer-declared) | Listing | ✅ |
| Quantity (verified) | Weighbridge | ✅ |
| Grade | Grading SOP | ✅ |
| Moisture | Meter (where available) | Optional |
| Price per quintal | Contract | ✅ |
| Platform fee | Contract | ✅ |
| Buyer price | Contract | ✅ |
| Transport cost | Dispatch | ✅ |
| Delivery date | Delivery | ✅ |
| Payment date | Ledger | ✅ |
| Dispute (Y/N + reason) | Dispute log | ✅ |
| Farmer satisfaction | Post-transaction IVR | Optional |

**Rule: if it is not recorded at the point of transaction, it did not happen.** Retrospective data entry
is the primary cause of unusable agricultural datasets.

---

## 7. Agent management

### Selection criteria
| Criterion | Weight |
|---|---|
| Existing business or trading activity | 25% |
| Cooperative endorsement | 20% |
| Literacy and numeracy | 15% |
| Smartphone ownership/comfort | 10% |
| Financial standing (no fraud history) | 15% |
| Physical location (proximity to farmers) | 15% |

### Training (3 days)
Day 1: Platform, USSD flows, farmer registration, identity
Day 2: Listings, bidding, contracts, escrow
Day 3: Weighing, grading, dispute handling, fraud awareness, practice role-plays

### Ongoing
- Weekly check-in call
- Monthly in-person visit
- Monthly income statement to agent
- Quarterly refresher
- Annual re-certification

### Discipline
| Issue | Action |
|---|---|
| Data entry error | Coaching |
| Late reporting | Warning |
| Undisclosed fee to farmer | Warning + refund |
| Fraud | Immediate suspension + report to police |
| Any theft from a farmer | Permanent exclusion |

---

## 8. Buyer onboarding

| Step | Detail |
|---|---|
| 1. Verification | Business licence, tax ID, bank account, references |
| 2. Credit check | Bank reference; payment history if available |
| 3. Escrow funding | Pre-fund or fund-on-bid; minimum balance |
| 4. Terms | Contract, quality standards, delivery windows, penalties |
| 5. Platform training | How to bid, confirm, accept |
| 6. Trial | First 2 transactions with enhanced platform supervision |
| 7. Limits | Initially ETB 500k exposure, scaled by performance |

---

## 9. Risk register (operational)

| Risk | Likelihood | Impact | Control |
|---|---|---|---|
| Farmer side-selling | High | High | Escrow; credit tie; guarantee |
| Buyer non-payment | Medium | High | Pre-funded escrow only |
| Agent fraud | Medium | High | Independent farmer SMS; spot audits |
| Quality dispute | High | Medium | Grading SOP; retained samples |
| Truck no-show | High | Medium | 2 transporters per lane; penalty clause |
| Cash shortage at agent | Medium | Medium | Float management; digital-first |
| Data loss | Low | Severe | Backups; offsite; tested restores |
| Theft in transit | Medium | Medium | Tracking; insurance; sealed loads |
| Farmer injury at collection point | Low | High | Safety SOP; first aid; insurance |

---

## 10. The weekly management dashboard (12 numbers)

1. New farmers registered
2. Farmers transacting (first time)
3. Repeat transactions
4. GMV
5. Take rate
6. Contribution margin
7. Median payment time
8. Disputes open / resolved
9. Agent income (average)
10. Escrow balance and reconciliation status
11. Advisory messages delivered
12. Cash burn vs. plan

**If only one number could be tracked, it would be repeat transactions.** Everything else is a leading
indicator to that.
