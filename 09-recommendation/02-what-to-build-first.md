# 09.2 · What to Build First (The MVP)

*Part of [09 · Recommendation](README.md)*

A precise scope for the first production system. Anything not on this list is deferred.

---

## 1. The MVP in one sentence

**A farmer in Arsi can list wheat by USSD, receive bids, accept one, deliver to a collection point, and
be paid the same day — with the money held in escrow by a bank and every step recorded in an auditable
ledger.**

That is it. No advisory, no credit, no logistics app, no API, no app.

---

## 2. In scope

| # | Capability | Detail |
|---|---|---|
| 1 | **Farmer registration** | Fayda verification, plot capture, language preference, PIN |
| 2 | **Listing via USSD** | Commodity, grade, quantity, price floor, collection point |
| 3 | **Bid management** | Buyers submit bids; farmer sees 3 best; accepts one |
| 4 | **Contracting** | Terms confirmed in local language; IVR recording; both sides bound |
| 5 | **Escrow** | Buyer funds; bank holds; release on delivery confirmation |
| 6 | **Delivery** | Weighing at collection point; grade recorded; digital receipt |
| 7 | **Settlement** | Same-day payment to farmer's wallet or agent cash |
| 8 | **Ledger** | Double-entry, append-only, reconciled daily |
| 9 | **Notifications** | SMS to farmer at every stage; independent of the agent |
| 10 | **Agent app** | Android, offline-first, 7 days queued |
| 11 | **Buyer web app** | Post requirements, bid, fund escrow, confirm receipt |
| 12 | **Dispute handling** | Intake, evidence, adjudication workflow |
| 13 | **Admin console** | Operations team manages everything manually if needed |
| 14 | **Price API** | Read-only public endpoint for observed prices |

---

## 3. Out of scope (deliberately)

| Excluded | Why | When |
|---|---|---|
| Advisory content | Not needed to transact | Phase 1, month 3 |
| Credit | No data yet; no licence | Phase 2 |
| Insurance | Needs credit data + insurer | Phase 2 |
| Logistics app | Manual dispatch is fine | Phase 2 |
| Farmer mobile app | Excludes the target market | Phase 3 at earliest |
| Developer API (write) | Needs stable core first | Phase 4 |
| Multi-language beyond 2 | Speed | Phase 2 |
| Multi-commodity | Focus | Phase 2 |
| Multi-region | Focus | Phase 2 |
| Data products | No data yet | Phase 2 |
| Government services | Not core | Phase 1 (vouchers only) |
| Loans, savings, wallet | Not licensed | Phase 2 |
| Chat/messaging | Not the problem | Never core |
| Social features | Not the problem | Never |

---

## 4. The farmer's experience, screen by screen

### USSD: `*800#`

```
1. Agriculture Platform
   1. Prices today
   2. Sell my harvest
   3. My transactions
   4. Language

> 2

Select crop:
   1. Wheat
   2. Maize
   3. Teff

> 1

Quantity (in quintals):
> 40

Your quality grade:
   1. Grade 1
   2. Grade 2
   3. Grade 3
   ? What is this?

> 2

Collection point:
   1. Arsi Robe
   2. Tiyo
   3. Digelu

> 1

Minimum price per quintal (birr):
> 2800

You are selling 40 qt Grade 2 wheat
at Arsi Robe, minimum 2,800 birr/qt.
Enter PIN to confirm.

> ****

Listing created. You will receive
bids by SMS within 24 hours.
Ref: W-4821
```

### The bid SMS (in Amharic and Oromiffa)

```
Agricultural Platform
3 bids for your 40qt wheat:
1) 2,950 birr/qt - Robe Millers
2) 2,880 birr/qt - Adama Trading
3) 2,820 birr/qt - Tiyo Union
Reply 1, 2 or 3 to accept.
Reply 9 for details by voice call.
```

### Acceptance and settlement

```
Contract confirmed.
Buyer: Robe Millers
Price: 2,950 birr/qt
Total: 118,000 birr
Delivery: Arsi Robe, 3 days
Fee: 1,770 birr
Net: 116,230 birr
Money is held in escrow.
Delivery code: 7412
```

```
Payment sent: 116,230 birr
to your telebirr account.
Thank you. Rate this buyer:
1=bad 5=good
```

**Total effort for the farmer: one USSD session, one SMS reply, one delivery trip.**

---

## 5. The agent's experience

| Step | Action |
|---|---|
| 1 | Agent opens app (offline) |
| 2 | Selects farmer from list or registers new |
| 3 | Verifies Fayda (online or cached) |
| 4 | Captures plot with GPS or draws boundary |
| 5 | Creates listing with farmer |
| 6 | App queues if offline |
| 7 | Farmer receives SMS confirmation directly |
| 8 | Agent earns commission on listing + delivery |

**Key design rule:** the agent never enters a transaction that the farmer has not confirmed by PIN and
has not been notified about directly.

---

## 6. The buyer's experience

| Step | Action |
|---|---|
| 1 | Log in to web app |
| 2 | View open listings filtered by commodity/region/grade |
| 3 | Place bid (with escrow funding commitment) |
| 4 | Get notified when bid is accepted |
| 5 | Fund escrow via bank transfer/wallet |
| 6 | Receive delivery, confirm quality and quantity |
| 7 | Escrow releases automatically |

---

## 7. Technical scope

| Component | Technology | Complexity |
|---|---|---|
| USSD gateway | Operator integration (Ethio Telecom; Safaricom later) | Medium |
| IVR | Asterisk/FreeSWITCH + local voice talent | Medium |
| SMS | Operator or aggregator | Low |
| Backend | Modular monolith (Python/Node), PostgreSQL | Medium |
| Ledger | Event-sourced double-entry | High |
| Escrow integration | Bank API or SFTP file exchange | High |
| Fayda integration | FaydaVerse API | Medium |
| Agent app | Flutter or React Native, offline-first (SQLite + sync) | High |
| Buyer web | React/Vue | Low |
| Admin console | React/Vue | Medium |
| Hosting | Ethiopian data centre (primary) + backup | Medium |

**Estimated build: 5–7 months with 5 engineers.**

---

## 8. What must exist before the first transaction

- [ ] Escrow account open with a licensed bank; legal agreement signed
- [ ] Fayda verification working in production
- [ ] USSD shortcode live
- [ ] SMS gateway live
- [ ] IVR live with at least Amharic and Oromiffa
- [ ] Agent app tested offline for 7 days
- [ ] Ledger reconciled against the bank's statement
- [ ] Dispute procedure written and staff trained
- [ ] Grading standards agreed with EQA or an equivalent
- [ ] 3 cooperatives with member lists
- [ ] 3 buyers with committed volume and funded escrow
- [ ] 50 agents trained
- [ ] Terms of service in local languages
- [ ] Insurance for cargo and collection points
- [ ] Data protection registration complete

---

## 9. MVP success criteria (first 90 days)

| Metric | Target |
|---|---|
| Farmers registered | 2,000 |
| Transactions completed | 500 |
| Average transaction value | ≥ETB 25,000 |
| Median time to payment | ≤24 hours |
| Disputes | ≤5% |
| Agent income (month 3) | ≥ETB 1,500 |
| USSD completion rate | ≥70% |
| Farmer would recommend (NPS) | ≥20 |

**If these are met, expand. If not, diagnose before expanding.**

---

## 10. The first day of operations

| Time | Activity |
|---|---|
| 06:00 | Ops team reviews queued listings |
| 07:00 | Trading desk contacts buyers for bids |
| 09:00 | Bids entered; farmers notified by SMS/IVR |
| 10:00 | First acceptances; escrow funding requests sent |
| 12:00 | Dispatch arranged; trucks booked |
| 14:00 | Delivery at collection point; weighing; grading |
| 16:00 | Buyer confirmation; escrow release instruction |
| 17:00 | Payments to wallets; SMS receipts |
| 18:00 | Ledger reconciliation |
| 19:00 | Daily standup: what broke? |

**The first 100 transactions will be hand-held. That is correct.**
