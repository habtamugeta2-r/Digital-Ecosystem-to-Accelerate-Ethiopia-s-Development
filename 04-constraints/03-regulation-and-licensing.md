# 04.3 · Regulation and Licensing

*Part of [04 · Constraints](README.md)*

> **The constraint in one line.** The rules are modern and clear on identity and payments, and
> **ambiguous precisely where a marketplace sits.** Resolve that in writing before you write code.

---

## 1. The instruments that govern the platform

| Instrument | Year | Governs | Practical impact |
|---|---|---|---|
| **Digital Identification Proclamation 1284/2023** | 2023 | Fayda, digital identity, data quality, locking/revocation | Legal basis for eKYC; defines how identity data can be used |
| **Personal Data Protection Proclamation 1321/2024** | 2024 (in force 24 Jul 2024) | All personal data processing: consent, rights, DPIAs, breach notification, cross-border transfers | **The binding constraint on every data flow** |
| **Payments Instrument Issuers Directive** | 2020 | Mobile money, wallets, tiered KYC | Determines whether you can hold value |
| **Licensing Directive for Payment Operators** | 2020–21 | Switching, POS, ATM, gateway, payment initiation | Determines whether you can route payments |
| **National Digital Payments Strategy 2026–2030** | 2025 | Targets and interoperability expectations | Alignment document; also signals future rules |
| **National Financial Inclusion Strategy (NFIS-II)** | 2021–25 | Inclusion targets | Policy context |
| **National Agri-Finance Implementation Roadmap (NAFIR) 2025–2030** | 2025 | Agri-credit targets, risk-sharing, agri bank | Funding and partnership pathway |
| **Digital Agriculture Roadmap (DAR) 2032** | 2025 | Digital agriculture priorities and governance | Policy cover; PMU counterpart |
| **Directive 1106/2025 (coffee)** | 2025 | Vertical integration, direct delivery, traceability | Confirms direction toward disintermediation |
| **Post-Harvest Management Strategy 2024–2030** | 2024 | Loss reduction | Aligned programme funding |
| **Digital Ethiopia 2030** | 2025 | National digital strategy | Umbrella alignment |
| **Commercial Code / cooperative law** | — | Corporate form, cooperative governance | Determines partner structure |

---

## 2. The four open questions (get these in writing)

### Q1 — Does escrow require a payment instrument issuer licence?

**The problem:** the platform wants to hold a buyer's money until delivery. Holding customer funds is
a regulated activity almost everywhere.

**Options:**
| Option | Structure | Pros | Cons |
|---|---|---|---|
| A. Custodian model | Licensed bank/PSI holds funds; platform instructs release | Simplest, fastest | Partner risk; fee sharing; less control |
| B. Own PSI licence | Platform becomes a licensed payment instrument issuer | Full control; new revenue | Capital, compliance, 6–18 months |
| C. Agent of a PSI | Platform operates as an agent | Fast | Limited scope; brand exposure |

**Recommendation:** **Option A for Phases 0–2**, then evaluate B if volumes justify it.

### Q2 — Can the platform act as agent for multiple wallets?

**The problem:** telebirr and M-Pesa are competitors. Being an agent for both may require separate
agreements and separate float accounts.

**Recommendation:** structure as a **merchant/aggregator**, not as a wallet agent, and route payments
through EthSwitch where possible. Confirm with NBE.

### Q3 — How can transaction data be shared with lenders?

**The problem:** credit underwriting requires sharing farmer transaction history with a bank or MFI.
Proclamation 1321/2024 requires explicit, purpose-limited, revocable consent.

**Recommendation:** build a **consent management service** (the Account Aggregator analogue) before
any lender integration:
- per-lender, per-purpose, time-bound consent;
- farmer-visible consent ledger via USSD/SMS;
- revocation that takes effect immediately;
- audit log of every data access;
- no bulk data export — query-based access only.

This is both a compliance requirement and a **competitive asset**: it is the piece no one else has.

### Q4 — Can the platform originate or service loans?

**The problem:** lending requires a licence. Origination and servicing (as an LSP) may not.

**Recommendation:** operate as a **licensed lending service provider / agent** of a bank or MFI, or
under a partnership where the lender is the legal creditor. Never describe yourself as a lender
without a licence.

---

## 3. Data protection: the operating rules

Proclamation 1321/2024 is GDPR-shaped. The practical obligations:

| Obligation | Implementation |
|---|---|
| Lawful basis (consent, contract, legal obligation) | Consent captured at registration, in local language, with recorded affirmation |
| Purpose limitation | Separate consent per use: credit assessment, advisory, government reporting, research |
| Data minimisation | Collect plot size and location — not household income or ethnicity |
| Data subject rights (access, rectification, erasure, portability, objection) | Self-service via USSD + agent; 30-day SLA |
| Data protection impact assessment (DPIA) | Complete before launch; repeat per new module |
| Breach notification | Documented 72-hour process; incident response plan |
| Cross-border transfer restrictions | Host in Ethiopia; any offshore processing requires a legal basis and documentation |
| Extraterritorial reach | Applies to foreign processors handling Ethiopian residents' data |
| Rights survive 10 years after death | Include in policy; unusual but explicit |
| Automated decision-making objection | Explain credit decisions; provide human review |

**Design decision:** treat compliance as a **product feature** — "your data, your consent, visible to
you" — rather than a legal overhead. It is a differentiator in a market where trust in institutions is
low after the 2023 aid diversion scandal.

---

## 4. Sector-specific regulatory exposure

| Area | Rule / risk | Mitigation |
|---|---|---|
| **Commodity price controls** | Government has periodically capped prices or banned exports | Commodity-level suspension switch; no long-term fixed-price commitments |
| **Coffee marketing** | ECX membership, direct specialty licensing, Directive 1106/2025 | Partner with licensed exporters; do not become a trader without a licence |
| **Input (fertiliser/seed) regulation** | MoA registration and quality standards | Only list accredited suppliers; verify certificates |
| **Phytosanitary / export certification** | Ministry of Agriculture, ECTA | Digitise the paperwork; partner, don't replace |
| **Weights and measures** | Legal metrology requirements | Certified scales; independent verification; photo evidence |
| **Insurance** | Insurance licence or broker licence required | Partner with a licensed insurer |
| **Employment / agent classification** | Agents may be employees or contractors | Written agent agreements; tax withholding |
| **Tax** | VAT 15%; withholding; digital service tax rules evolving | Local accounting; clarify treatment of platform fees |
| **Competition** | Emerging framework; SOE privileges | Document fair dealing; avoid exclusive arrangements that invite scrutiny |

---

## 5. Corporate structure options

| Structure | Advantages | Disadvantages | Best for |
|---|---|---|---|
| **Ethiopian private limited company** | Local control; eligible for government contracts; simpler FX treatment for local operations | Capital controls on repatriation; limited foreign investment routes | Operating entity (recommended) |
| **Ethiopian PLC with cooperative shareholders** | Political durability; member alignment; trust | Governance complexity; slower decisions | The recommended long-term structure |
| **Foreign holding + Ethiopian subsidiary** | Investor familiarity; staged capital | Repatriation approval; regulatory scrutiny | If foreign VC is involved |
| **PPP / concession** | Policy alignment; co-funding; state contracts | Procurement; political risk; slower | Programme delivery lines |
| **Foundation / NGO** | Grant eligibility | Cannot raise equity or distribute | Pilot funding only |

**Recommendation:** an **Ethiopian PLC with a cooperative equity tranche** as the operating entity,
with a clearly documented dividend policy and a foreign investment structure only if the capital
requires it.

---

## 6. The compliance build sequence

| Phase | Action | Owner |
|---|---|---|
| 0 | Written NBE position on escrow, multi-wallet agency, data sharing, lending | Legal + CEO |
| 0 | Incorporate; register for tax; open corporate bank account | Finance |
| 0 | DPIA; privacy policy in 5 languages; consent flows | Legal + Product |
| 0 | FaydaVerse developer sandbox integration; eSignet/OIDC | Engineering |
| 1 | Agent agreements; AML/KYC procedures; record retention | Compliance |
| 1 | Insurance (cyber, professional indemnity, cash-in-transit) | Finance |
| 2 | Lending partnership agreement; consent service live | Legal + Product |
| 2 | Data sharing agreements with each lender (per-purpose) | Legal |
| 3 | Licensing review for own PSI, if volumes justify | CEO |

---

## Decisions forced

| Decision | Choice |
|---|---|
| Custody | Licensed partner, not the platform |
| Data hosting | Ethiopia; no offshore processing without documented basis |
| Consent | Per-purpose, revocable, visible to the farmer |
| Lending | Originate for licensed partners; do not lend on own book in Phase 1–2 |
| Corporate form | Ethiopian PLC with cooperative equity participation |
| Regulatory posture | Written clarifications before build; proactive engagement with NBE, MoA, FaydaVerse |
