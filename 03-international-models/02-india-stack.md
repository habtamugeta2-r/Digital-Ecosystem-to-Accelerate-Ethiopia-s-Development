# 03.2 · India Stack

*Part of [03 · International models](README.md)*

> **Why study it.** India Stack is the only fully realised example of the architecture Ethiopia is
> currently assembling (Fayda ≈ Aadhaar, EthSwitch/EthioPay ≈ UPI, Open Data ≈ DEPA, DAR ≈ ONDC-analogue).
> It is the blueprint most likely to be right — and the one most likely to be applied carelessly.

---

## 1. The five layers (2026 state)

| Layer | Component | Scale (2026) | What it moves |
|---|---|---|---|
| **Identity** | Aadhaar (UIDAI) | 1.4+ billion enrolments; 24.5 bn eKYC transactions; 2,707 crore authentications/yr | Verification and KYC data |
| **Payments** | UPI, BBPS, AePS | **21.7 bn transactions/month** (Jan 2026); 241.6 bn in FY2025/26; 703 live banks; ~49% of global real-time payments | Real-time interoperable payments |
| **Documents** | DigiLocker, eSign | ~10 bn documents issued/verified; 685 m citizens | Paperless credentials |
| **Consent / data** | Account Aggregator (DEPA) | 2.61 bn enabled accounts; ₹1.47 lakh crore in loans (H1 FY26) | Consent-based financial data sharing |
| **Commerce / credit protocols** | ONDC, OCEN | ONDC: 150 m cumulative orders, 1,200+ cities; OCEN: ~70,000 loans | Open commerce discovery and contextual credit |

---

## 2. The Direct Benefit Transfer result

| Metric | Value |
|---|---|
| Cumulative savings attributed to DBT | **₹3.48 lakh crore** (MeitY/BlueKraft, 2025) to **₹5.14 lakh crore** (government data, FY15–FY25) |
| Total DBT transfers | ₹43.3–43.95 lakh crore |
| Beneficiaries | Up from 11 crore to 176 crore |
| Fake ration cards removed | 58.7–63.6 million |
| Fake/duplicate MGNREGS job cards removed | 12.6–13.2 million |
| Ineligible PM-KISAN beneficiaries removed | 21.17 million (₹22,106 crore saved) |
| Welfare Efficiency Index | 0.32 → 0.91 |

**What actually drives the savings:** de-duplication (one person, one ID, one benefit), elimination of
ghost beneficiaries, and direct crediting (no intermediary cash handling). It is **not** primarily a
technology effect — it is a **de-duplication and disintermediation** effect that technology makes
possible.

**Caution on the number:** the ₹3.48 vs ₹5.14 lakh crore discrepancy reflects different periods and
methodologies, and some analysts argue DBT savings are partly definitional (money not spent because
beneficiaries were excluded, rather than fraud prevented). Cite the mechanism, not the headline.

---

## 3. What India got right

### 3.1 The layer separation

The single most important design decision: **each layer is separately owned, separately governed, and
usable by anyone.**

```
   IDENTITY (Aadhaar)  ──►  can be used by any bank, telecom, or app
   PAYMENTS (UPI)      ──►  can be accessed by any licensed PSP
   DATA (AA/DEPA)      ──►  consent-based, portable, revocable
   COMMERCE (ONDC)     ──►  any buyer app can talk to any seller app
```

This is why hundreds of companies could build on it. It is the exact opposite of a single
all-in-one super-app.

### 3.2 Mandated interoperability with private competition on top

UPI is run by NPCI (a public-private entity), but the *front end* is fiercely competitive (PhonePe,
Google Pay, Paytm, and hundreds of others). The rail is neutral; the apps compete.

**Ethiopia's version:** EthSwitch plays the NPCI role; telebirr and M-Pesa compete on the front end.
The structure is already correct — it just needs volume and merchant acceptance.

### 3.3 ONDC: the closest analogue to an open agri-marketplace

ONDC is an **open network protocol**, not a platform. Any buyer app can transact with any seller app.
Key features relevant to Ethiopia:

| ONDC feature | Agricultural application |
|---|---|
| Open protocol, no gatekeeper | Any cooperative or trader can list; no single platform controls access |
| Interoperable catalogue | A farmer's listing is visible across multiple buyer apps |
| Standardised order and fulfilment | Grade, quantity, delivery terms are machine-readable |
| Network-level trust (ratings, verification) | Verified seller badges without a central marketplace owner |
| Logistics as a separate provider on the network | Third-party transporters plug in |

**However:** ONDC's own search quality is still maturing, and 150 million cumulative orders over
several years is small relative to India's retail. The lesson is architectural, not operational.

### 3.4 Account Aggregator: consent as infrastructure

The AA framework lets a user grant a lender revocable, purpose-limited access to their financial data
through a standard protocol. **This is exactly the mechanism an agricultural platform needs** to let
banks underwrite farmers using platform transaction history without the platform "giving away" data.

Ethiopia's Proclamation 1321/2024 provides the legal basis (consent, portability, purpose limitation)
but **no equivalent technical framework yet exists**. Building a working consent-and-data-sharing
layer for agricultural transactions would be a genuine contribution — and a defensible one.

---

## 4. What India got wrong (or has not solved)

| Problem | Detail | Lesson for Ethiopia |
|---|---|---|
| **Data silos persisted** | A 2026 Tony Blair Institute study found Indian government data remains siloed across departments and states despite the infrastructure — "collected to satisfy one department's reporting requirement" | Building rails is not the same as building usable data. Plan the data governance explicitly |
| **Exclusion through biometric failure** | Authentication failures have denied benefits to genuine beneficiaries, particularly the elderly and manual labourers | **Always provide a non-biometric fallback** (agent attestation, OTP, community verification) |
| **Digital divide in usage** | Wealthier users capture more UPI benefit; average merchant transaction is ~₹592 (~US$7) | Usage inequality follows income inequality; design for the bottom |
| **Privacy concerns** | Centralised biometrics, breach risks, and the interoperability of UPI with identity data create surveillance-adjacent risks | Ethiopia's Proclamation 1321/2024 is stricter than India's pre-DPDP regime; use it |
| **Over-reliance on a single operator** | NPCI is a single point of failure and policy risk | EthSwitch is small; build multi-rail resilience |
| **Financial sustainability** | UPI is free to users; the economics are subsidised by banks and government | Do not assume a free rail forever; price your own layer |

---

## 5. Direct mapping to Ethiopia

| India | Ethiopia equivalent | Status | Gap |
|---|---|---|---|
| Aadhaar | **Fayda** | 53.4 m registrations; 208 m verifications; mandatory for banking by Dec 2026 | Rural coverage (~19.2 m Oromia + 8.3 m Amhara + 8.1 m Addis concentrated; Gambella ~28,300) |
| UPI | **EthioPay / EthSwitch** | Live; >1 m P2P/day | Merchant acceptance, rural usage |
| DigiLocker / eSign | **FaydaVerse credentials, eSign (planned)** | Sandbox launched Oct 2026 | Not yet in production |
| Account Aggregator | **None** | — | **The most valuable missing layer** |
| ONDC | **None** (ATI's Digital Market Linkage Platform is a closed platform) | — | Open agri commerce protocol |
| OCEN | **NAFIR credit lines + platform data** | In design | Lending orchestration |
| DBT | **Fayda-linked vouchers + G2P** | NDPS targets 80% digital G2P by 2030 | Distribution layer |

**The strategic insight:** Ethiopia has built the first three layers (identity, payments, credentials-in-
progress) and **none of the last four** (consent, open commerce, credit orchestration, benefits
delivery). Those four are precisely where a private operator can create and capture value.

---

## 6. What to copy, precisely

1. **Copy the layer separation.** Build systems that other organisations can call, not a monolith.
2. **Copy the consent architecture.** Implement a user-controlled, purpose-limited, revocable data
   sharing mechanism for agricultural credit — before any bank asks for it.
3. **Copy the open protocol idea, adapted.** A standard for agricultural listings (commodity,
   grade, quantity, location, delivery window) that any buyer app can consume is more valuable than a
   proprietary marketplace.
4. **Copy the G2P mechanism** — Fayda-verified vouchers with biometric de-duplication and a
   non-biometric fallback.
5. **Do not copy** the subsidy economics, the single-operator dependency, or the assumption of
   foundational literacy.

---

## Key takeaways

1. India Stack works because each layer is separately owned and openly usable — **composability, not
   consolidation.**
2. UPI at 21.7 bn transactions/month and Aadhaar at 1.4 bn enrolments are the scale targets; they took
   10–15 years.
3. DBT savings (₹3.48–5.14 lakh crore) come from **de-duplication and disintermediation**, not from
   technology per se.
4. India's **unbuilt layers** — Account Aggregator, ONDC, OCEN — are exactly Ethiopia's missing
   layers, and exactly where a private operator should build.
5. Always provide a **non-biometric fallback** in any identity-gated benefit; biometric failure is a
   known exclusion mechanism.
