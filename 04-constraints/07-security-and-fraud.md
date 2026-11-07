# 04.7 · Security, Fraud and Integrity

*Part of [04 · Constraints](README.md)*

> **The constraint in one line.** A platform that moves money for semi-literate users in a
> low-trust, high-conflict environment is a **fraud target by construction**. One significant breach
> ends the business.

---

## 1. The threat model

| Threat | Likelihood | Impact | Primary victim |
|---|---|---|---|
| **SIM swap / account takeover** | High | High | Farmer, agent |
| **Agent fraud** (fake transactions, float misuse) | High | High | Platform, farmer |
| **Fake listings / non-existent supply** | High | Medium | Buyer |
| **Quality substitution** (good sample, poor delivery) | High | High | Buyer |
| **Weight/quantity manipulation** | High | High | Either |
| **Payment interception / social engineering** | High | High | Farmer |
| **Insider fraud** (staff approving fictitious transactions) | Medium | Very high | Platform |
| **Data breach** (Fayda data, transaction data) | Medium | Very high | Everyone; regulatory |
| **Escrow fund theft** | Low | Catastrophic | Everyone |
| **Collusion between agent and buyer** | Medium | High | Farmer |
| **Armed robbery of agents / transporters** | Medium | High | Agents |
| **State or political interference in records** | Low–Medium | High | Platform credibility |
| **Ransomware / DDoS** | Medium | High | Operations |
| **Physical security of staff in conflict zones** | Medium | High | Staff |

---

## 2. Identity-level controls

| Control | Implementation |
|---|---|
| Strong onboarding | Fayda eKYC (biometric) + liveness + cooperative attestation for farmers |
| Tiered KYC | NBE tiered KYC: low-value accounts with lighter checks; higher limits require full verification |
| PIN + OTP | Never PIN alone; OTP to the registered MSISDN |
| Device binding | Bind agent devices; require re-verification on device change |
| SIM-swap monitoring | Detect recent SIM swaps; freeze high-value actions for 48 h after a swap |
| Biometric fallback | Agent attestation + community verification when biometrics fail (never lock out) |
| Role-based access | Farmers, agents, buyers, transporters, staff, auditors — separate permissions |
| Agent limits | Maximum transaction size and daily volume per agent, scaled by track record |

### The biometric-failure problem

Fayda uses fingerprint, iris and face. In practice, manual labourers' fingerprints degrade; elderly
users and women in some contexts face enrolment barriers. **India's Aadhaar experience shows that
biometric failure is a real exclusion mechanism.**

**Mandatory fallback hierarchy:**
1. Biometric authentication (Fayda)
2. OTP to registered phone
3. Agent visual verification + OTP + recorded attestation
4. Cooperative officer attestation + 24-hour cooling period

Never make a benefit or a payment contingent on a single biometric success.

---

## 3. Transaction-level controls

| Control | Implementation |
|---|---|
| **Double-entry accounting** | Every movement recorded as debit and credit; balances must reconcile to zero |
| **Idempotency keys** | Prevents duplicate payment on retry — the most common payment bug in low-connectivity environments |
| **Escrow segregation** | Custodian-held, segregated accounts; platform instructs, never holds |
| **Dual approval** | Manual releases above a threshold require two staff |
| **Delivery evidence** | Photo + geotag + timestamp + receiver OTP + weighbridge ticket |
| **Certified weighing** | Platform-operated or third-party certified scales at aggregation points; photographed ticket |
| **Grading protocol** | Standard grade definitions; sampling protocol; retained sample for dispute |
| **Anomaly detection** | Rules + ML on: transaction size vs. history, velocity, repeat counterparties, geographic implausibility, agent error rates |
| **Cooling period** | High-value first transactions held for review |
| **Dispute fund** | Reserved pool to settle contested transactions quickly |
| **Audit trail** | Append-only logs; tamper-evident; retained per NBE record requirements |

---

## 4. Agent integrity

Agents handle cash and are the primary fraud vector in every agent-based system. Controls:

| Control | Detail |
|---|---|
| Vetting | Fayda verification, cooperative endorsement, reference checks, credit check where available |
| Bonding / deposit | Small security deposit or guarantee; scaled to volume |
| Float monitoring | Real-time float balance; alerts on unusual movements |
| Commission clawback | Fraudulent transactions reverse the agent's commission |
| Customer confirmation | Farmer receives an SMS for *every* agent-initiated transaction and can dispute via IVR |
| Mystery shopping | Periodic unannounced audits |
| Two-agent rule | High-value cash-out requires a second agent or a supervisor |
| Public scorecard | Agent reliability score visible at the cooperative |
| Exit protocol | Device wipe, float settlement, customer reassignment |

**The single most effective control: every agent action triggers an independent SMS to the farmer.**
It costs almost nothing and it makes silent fraud nearly impossible.

---

## 5. Data security

| Requirement | Implementation |
|---|---|
| Data residency | Ethiopia-hosted (Proclamation 1321/2024 constraints) |
| Encryption at rest | AES-256; key management with rotation |
| Encryption in transit | TLS 1.3; certificate pinning on mobile |
| PII minimisation | Collect only what is needed; never store raw biometrics — use Fayda's verification API |
| Tokenisation | Store Fayda references, not biometric data |
| Access control | Least privilege; just-in-time access; break-glass with logging |
| Logging | Centralised, immutable, 24-month retention minimum |
| Backups | Encrypted, geographically separate, tested restore |
| Penetration testing | Pre-launch and annually |
| Incident response | Documented plan; 72-hour breach notification (per Proclamation 1321/2024) |
| Staff training | Quarterly; phishing simulation |
| Vendor risk | Security assessment for all processors; contractual data protection clauses |

**The critical architectural decision: never store biometric templates.** Use FaydaVerse's
verification API and keep only the result and the reference number. This reduces both breach impact
and liability.

---

## 6. Physical and field security

| Risk | Mitigation |
|---|---|
| Kidnapping/robbery in some regions | No fixed-location cash holdings; agents keep minimal float; movement tracked |
| Conflict-zone staff safety | Do not deploy staff to active-conflict zones; use local agents under separate agreements |
| Cargo theft in transit | Tracked vehicles; photo POD; in-platform freight payment reduces cash carried |
| Social unrest | Suspension protocol; regional autonomy to pause operations |
| Insurance | Cash-in-transit, cargo, cyber, professional indemnity, political violence where available |

---

## 7. Integrity of the market itself

Less obvious but equally important:

| Risk | Control |
|---|---|
| Platform is used to launder money | AML monitoring; report suspicious activity to NBE/FIC |
| Price manipulation by a large buyer | Publish bid dispersion; minimum buyer count per region |
| Collusive bidding | Anomaly detection on bid patterns; rotate buyer visibility |
| Fake cooperatives | Verify cooperative registration with the regional bureau |
| Government pressure to alter records | Immutable logs; independent audit; board reporting |
| Data used for ethnic targeting | Do not collect ethnicity; enforce purpose limitation; publish access transparency |

---

## 8. Security budget guidance

For planning purposes (⚪ illustrative), a platform of this type should expect:

| Stage | Annual security spend | Focus |
|---|---|---|
| Pilot (1 region) | ~US$40–80k | Core controls, pen test, insurance |
| Phase 2 (3 regions) | ~US$120–250k | SOC-lite, fraud analytics, compliance |
| Phase 3 (national) | ~US$400k–1 m | Full SOC, dedicated security team, third-party audits |

That is roughly **3–6% of operating expenditure** — the normal range for fintech-adjacent businesses,
and not optional.

---

## Decisions forced

| Decision | Choice |
|---|---|
| Biometrics | Fayda verification only; never store templates |
| Fallback | Four-level fallback; never single-factor biometric gate |
| Escrow | Segregated custodian accounts; the platform never holds funds |
| Payment integrity | Double-entry + idempotency from day one |
| Agent control | Independent SMS to the farmer for every agent action |
| Delivery proof | Photo + geotag + OTP + weighbridge ticket |
| Data residency | Ethiopia |
| Insurance | Cyber, professional indemnity, cash-in-transit, cargo |
| Security spend | 3–6% of opex |
