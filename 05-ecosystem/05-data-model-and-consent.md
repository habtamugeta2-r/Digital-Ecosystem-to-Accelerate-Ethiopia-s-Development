# 05.5 · Data Model and Consent

*Part of [05 · Proposed ecosystem](README.md)*

> This is the part of the design that becomes the moat, the compliance obligation and the public-good
> contribution all at once.

---

## 1. Core entities

```
┌─────────────┐          ┌─────────────┐          ┌──────────────┐
│  FARMER     │──owns────│    PLOT     │──part of─│ COOPERATIVE  │
│  (Fayda FIN)│          │ (GPS/area)  │          │  (registry)  │
└──────┬──────┘          └──────┬──────┘          └──────┬───────┘
       │                        │                        │
       │                   ┌────┴─────┐                  │
       │                   │  CROP /  │                  │
       │                   │ SEASON   │                  │
       │                   └────┬─────┘                  │
       │                        │                        │
       │                   ┌────┴──────┐                 │
       ├────produces──────►│  HARVEST  │                 │
       │                   └────┬──────┘                 │
       │                        │                        │
       │                   ┌────┴──────┐                 │
       ├────lists─────────►│  LISTING  │◄───views────────┤
       │                   └────┬──────┘                 │
       │                        │                        │
       │                   ┌────┴──────┐    ┌──────────┐ │
       │                   │   ORDER   │───►│  BUYER   │ │
       │                   └────┬──────┘    └──────────┘ │
       │                        │                        │
       │              ┌─────────┼─────────┐              │
       │              ▼         ▼         ▼              │
       │        ┌─────────┐┌────────┐┌────────┐          │
       │        │ ESCROW  ││SHIPMENT││ GRADE  │          │
       │        └────┬────┘└───┬────┘└────────┘          │
       │             │         │                          │
       │             ▼         ▼                          │
       │        ┌──────────────────┐                      │
       └───────►│   LEDGER ENTRY   │                      │
                └────────┬─────────┘                      │
                         │                                │
                ┌────────┴─────────┐                      │
                ▼                  ▼                      │
        ┌──────────────┐   ┌──────────────┐               │
        │   CREDIT     │   │   CONSENT    │               │
        │   HISTORY    │   │    GRANT     │               │
        └──────────────┘   └──────────────┘               │
```

---

## 2. Entity specifications

### Farmer
| Field | Type | Source | Sensitivity |
|---|---|---|---|
| `farmer_id` | UUID | Platform | Low |
| `fayda_fin` | 12-digit reference | FaydaVerse | **High** — encrypted, tokenised |
| `name`, `dob`, `sex` | Verified claims | FaydaVerse | **High** |
| `phone_msisdn` | String | Registration | **High** |
| `preferred_language` | Enum (5) | Registration | Low |
| `cooperative_id` | FK | Agent | Low |
| `pin_hash` | Bcrypt | Self-set | **Critical** |
| `kyc_level` | Tier 1–3 | Computed | Low |
| `verification_cached_at` | Timestamp | Platform | Low |

### Plot
| Field | Type | Notes |
|---|---|---|
| `plot_id` | UUID | |
| `farmer_id` | FK | |
| `geometry` | GeoJSON polygon or point + radius | Captured by agent GPS, verified against satellite |
| `area_ha` | Decimal | Derived from geometry, confirmed by farmer |
| `soil_type` | Enum | EthioSIS overlay |
| `altitude_m` | Integer | DEM |
| `irrigation` | Boolean | Registration |

### Crop / Season
| Field | Type | Notes |
|---|---|---|
| `crop_id` | FK to crop catalogue | Must map local names to species |
| `season` | Enum (Meher/Belg) | |
| `planted_date` | Date | Confirmed by input purchase |
| `expected_harvest` | Date range | Model + farmer input |
| `inputs_used` | JSON | Seed, fertiliser, pesticide quantities |

### Harvest
| Field | Notes |
|---|---|
| `quantity_kg` | Farmer-declared then weighbridge-verified |
| `grade` | Per commodity standard |
| `moisture_pct` | If measured |
| `storage_location` | Farm, cooperative, warehouse |

### Listing / Order / Escrow / Shipment
Recorded with the full state machine described in [`01-architecture.md`](01-architecture.md) §3.2.
Every state transition carries `actor_id`, `timestamp`, `evidence` (photo/geotag/OTP/weighbridge).

### Ledger Entry
```
entry_id, transaction_id, account_debit, account_credit, amount_etb,
currency, rail, external_reference, created_at, idempotency_key, evidence_ref
```
**Invariant: for every transaction, sum(debits) = sum(credits).**

### Credit History (derived, not stored as truth)
| Field | Derivation |
|---|---|
| `transactions_completed` | Count of settled orders |
| `total_volume_kg` | Sum of delivered quantities |
| `on_time_delivery_pct` | Delivered within contract window |
| `avg_grade` | Weighted mean grade |
| `repayment_history` | From lender feedback events |
| `tenure_seasons` | Seasons since first transaction |

**Design note:** keep this **derived** from the ledger, not stored as a mutable score. Derived data can
be recomputed and audited; a stored score becomes a disputed artefact.

---

## 3. The consent model

### 3.1 Consent grant object

```json
{
  "consent_id": "cns_01HX...",
  "subject_id": "frm_01HX...",
  "grantee_id": "bank_dashen",
  "grantee_type": "lender",
  "purpose": "credit_assessment",
  "scope": ["transactions.volume", "transactions.grade", "transactions.timeliness"],
  "excluded": ["identity.dob", "plot.geometry"],
  "granted_at": "2026-11-07T09:14:00Z",
  "expires_at": "2027-02-05T09:14:00Z",
  "channel": "ussd",
  "evidence": { "session_id": "ussd_...", "ivr_recording_ref": "ivr_..." },
  "revocable": true,
  "revoked_at": null
}
```

### 3.2 Consent lifecycle rules

| Rule | Rationale |
|---|---|
| Explicit, affirmative, recorded | Proclamation 1321/2024 requires lawful basis |
| Given in the farmer's language, on the farmer's channel | Consent must be informed |
| Per-purpose, per-grantee | A farmer consenting to credit assessment has not consented to marketing |
| Time-bound (default 90 days) | Limits the blast radius of any leak |
| Revocable at any time, effective immediately | Legal right; also a trust signal |
| Visible to the farmer | USSD: "Who has seen my data?" |
| Audited on every access | Enables dispute resolution and regulator reporting |
| Not a condition of service | Cannot refuse a farmer market access for declining credit data sharing |

### 3.3 Access patterns

| Pattern | Allowed | Not allowed |
|---|---|---|
| Single-subject query with valid consent | ✅ | |
| Field-limited response (only consented scope) | ✅ | |
| Aggregate statistics over ≥50 subjects | ✅ (de-identified) | |
| Bulk export of subject data | ❌ | |
| Re-use for a different purpose | ❌ | |
| Re-sharing with a fourth party | ❌ | |

---

## 4. Data quality as a product requirement

Bad data destroys credit models and farmer trust. Controls:

| Control | Implementation |
|---|---|
| Plot verification | GPS polygon cross-checked against satellite imagery and cooperative land records |
| Quantity verification | Weighbridge ticket at aggregation point |
| Grade verification | Sampling protocol; retained sample for 30 days |
| Price verification | Cross-check platform prices against ATI 6077 daily; flag divergence >15% |
| Duplicate detection | Fayda FIN uniqueness; phone number; name + cooperative + plot similarity |
| Completeness scoring | Every farmer record has a completeness score; agents incentivised on completeness |
| Correction workflow | Farmer-initiated correction via USSD/agent; audited; never silent edits |
| Provenance tagging | Every field records its source (farmer-declared, agent-captured, verified, derived) |

**The provenance tag is important:** a bank will lend on verified data and will not lend on
farmer-declared data. Distinguishing them is what makes the dataset bankable.

---

## 5. Public good: what the platform should publish openly

A private platform that publishes public-good data earns legitimacy and shapes policy.

| Dataset | Cadence | Licence |
|---|---|---|
| Commodity prices by market | Daily | Open (CC-BY) |
| Volume traded by commodity and region | Weekly | Aggregated, open |
| Post-harvest loss estimates | Seasonal | Open |
| Logistics lane costs | Monthly | Aggregated, open |
| Smallholder credit performance (aggregate) | Quarterly | Aggregated, open |
| Crop area and yield estimates | Seasonal | Open, to MoA first |

**What must never be published:** individual farmer data, plot geometries, credit defaults by name,
or anything that could enable targeting of individuals or groups.

---

## 6. The moat, stated precisely

| Asset | Copyable? | Time to replicate |
|---|---|---|
| Marketplace UI | Yes | Weeks |
| Advisory content | Yes (public) | Months |
| Logistics network | Partly | 12–24 months |
| Agent network | Hard | 18–36 months |
| Cooperative relationships | Hard | 24–48 months |
| **Verified transaction ledger** | **No** | **2+ seasons, irreversible** |
| **Consent registry with lender trust** | **No** | **24+ months** |
| **Credit performance data** | **No** | **2+ years** |

**The defensible core is time-based**: you cannot buy two seasons of verified repayment history. That is
why the platform should start transacting as early as possible, even manually, even at low margin.

---

## 7. Data protection impact assessment (DPIA) checklist

Required before launch under Proclamation 1321/2024:

- [ ] Purpose and legal basis for each processing activity
- [ ] Categories of data and data subjects
- [ ] Necessity and proportionality assessment per field
- [ ] Data flows mapped, including every processor and sub-processor
- [ ] Retention schedule per data category
- [ ] Security measures (technical and organisational)
- [ ] Risk assessment: likelihood × severity per identified risk
- [ ] Mitigations and residual risk
- [ ] Consultation with the data protection authority where residual risk is high
- [ ] Consent mechanisms and evidence capture
- [ ] Data subject rights procedures (access, rectification, erasure, portability, objection)
- [ ] Breach response plan (72-hour notification)
- [ ] Cross-border transfer assessment (assume none)
- [ ] Review schedule (annual, and on any material change)

---

## Decisions recorded

| Decision | Choice |
|---|---|
| Farmer identity key | Fayda FIN (tokenised), never biometrics |
| Credit score | Derived from ledger, recomputable, explainable |
| Consent | First-class entity; per-purpose; revocable; visible |
| Data sharing | Query-based only; never bulk export |
| Data provenance | Every field tagged by source type |
| Open data | Prices, aggregates, loss rates — published |
| DPIA | Mandatory pre-launch and per module |
