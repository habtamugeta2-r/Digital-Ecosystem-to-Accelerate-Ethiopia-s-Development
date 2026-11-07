# 08.2 · Conflict and Political Risk

*Part of [08 · Risks](README.md)*

**This is the single largest risk to the project, and the one that cannot be engineered away.** This file
treats it with the seriousness it deserves.

---

## 1. The current security picture (as of late 2026)

| Region | Status | Implication |
|---|---|---|
| **Tigray** | Post-war recovery; fragile peace | Excluded from Phases 1–3 |
| **Amhara** | Renewed fighting from late Sep 2026; Fano insurgency | High risk; selective woredas only |
| **Afar** | Sporadic conflict; pastoral economy | Deferred |
| **Oromia** | Insurgency in parts; **pilot region must be carefully selected** | Core, but woreda-level screening essential |
| **Somali** | Al-Shabaab activity; security operations | Deferred |
| **Benishangul-Gumuz** | Episodic violence | Low priority |
| **Gambella** | Episodic; very low Fayda coverage | Low priority |
| **Addis Ababa** | Stable | Safe hub |
| **Dire Dawa / Harari** | Relatively stable | Medium priority |

**Economic cost of conflict:** the World Bank estimated US$22.7 bn in damage; Oxford Economics projected
US$125 bn of lost GDP by 2027. Fitch projects FY27 growth around 7% (down from the 9.2% headline).

---

## 2. What conflict does to the platform, specifically

| Mechanism | Effect |
|---|---|
| **Road closure** | Trucks cannot move; deliveries fail; disputes spike |
| **Market closure** | Buyers stop bidding; liquidity collapses |
| **Displacement** | Farmers and agents leave; records become meaningless |
| **Bank branch closure** | Cash-in/cash-out breaks; escrow settlement delayed |
| **Connectivity shutdown** | Internet and mobile data cut; USSD may survive, apps do not |
| **Currency/asset seizure** | Working capital lost |
| **Staff risk** | Injury, kidnapping, trauma |
| **Insurance withdrawal** | Cargo and asset cover becomes unavailable |
| **Reputational** | Association with one side of a conflict |

**Historical precedent:** the 2020–22 Tigray war shut down banking, telecoms and roads for over a year.
Any platform operating there would have lost its entire operation.

---

## 3. The design responses

### 3.1 Geographic diversification (the primary defence)

| Phase | Regions | Max share of GMV from one region |
|---|---|---|
| 1 | 1 | 100% (accepted risk) |
| 2 | 2–3 | 60% |
| 3 | 4–6 | 40% |
| 4–5 | 6–8 | 30% |

**Rule: no single region should exceed 40% of GMV after Phase 2.** This is a hard portfolio constraint,
not an aspiration.

### 3.2 Asset-light structure

| Asset | Treatment |
|---|---|
| Warehouses | Leased, short-term, multiple locations |
| Trucks | Contracted, not owned |
| Offices | Serviced or leased monthly |
| Equipment | Mobile, insured, recoverable |
| Cash | Held in escrow at a bank, not in the field |
| Data | Replicated to a second site (Addis + secondary) |

**If a region is lost, the loss should be a few months of revenue, not a balance sheet.**

### 3.3 The regional suspension switch

A feature flag per region that can:
- Stop new listings
- Freeze open escrows (funds held safely, not released)
- Notify all affected farmers and agents by SMS
- Redirect buyers to other regions
- Preserve records for eventual reopening

**Tested quarterly, not written once.**

### 3.4 Staff safety protocol

| Level | Trigger | Action |
|---|---|---|
| **Green** | Normal | Standard operations |
| **Amber** | Incidents within 50 km | Travel restrictions; local staff only; daily check-in |
| **Red** | Active fighting in the woreda | Evacuate non-local staff; suspend operations; remote support |
| **Black** | Region-wide conflict | Full suspension; staff relocation; asset protection |

**Non-negotiable: no staff member is asked to remain in an unsafe area for business reasons.** This is a
board-level commitment, not an operational preference.

### 3.5 Connectivity resilience

| Scenario | Response |
|---|---|
| Internet shutdown | USSD continues (operators); SMS continues; agent app queues offline |
| Mobile network shutdown | Operations halt; no workaround |
| Data centre outage | Secondary site in a different region |
| Payment rail outage | Fall back to the second rail (telebirr ↔ M-Pesa) |

**Note:** Ethiopia has a history of internet shutdowns. The design must assume they happen, not hope
they do not. **USSD and SMS are the only channels that reliably survive.**

### 3.6 Cash resilience

| Mechanism | Purpose |
|---|---|
| Escrow at a bank with branches outside the conflict zone | Funds remain accessible |
| Multiple bank relationships | If one is shut, another operates |
| Agent cash limits and insurance | Limit exposure |
| Physical cash minimisation | Digital by default |

---

## 4. Political risk: the state as partner, competitor and regulator

The platform will interact with the state in three ways simultaneously:

| Role | Example | Platform posture |
|---|---|---|
| **Partner** | Delivering the DAR input programme | Collaborate; deliver well; be useful |
| **Competitor** | A ministry launching its own platform | Differentiate; avoid direct confrontation |
| **Regulator** | NBE on escrow, lending, data | Comply early; seek written positions |

### The four possible state postures

| Posture | Description | Platform response |
|---|---|---|
| **Enabling** | State builds rails, invites private applications (current trajectory) | Build fast; integrate deeply |
| **Neutral** | State does little; private sector fills gap | Build; expect slow government sales |
| **Competing** | State builds a platform with a mandate | Partner; seek a supplier role; avoid a fight |
| **Restrictive** | State limits private platforms or requires data sharing | Comply; reduce exposure; consider licensing the tech to the state |

**Assessment (⚪):** the current trajectory is **enabling-to-neutral**, with the Digital Ethiopia 2030
strategy and the National Digital Payments Strategy explicitly favouring private participation. But
policy can shift quickly.

---

## 5. Political risk mitigations, ranked

| Mitigation | Effectiveness | Cost |
|---|---|---|
| Cooperative equity ownership | High | 5–10% dilution |
| Government programme delivery (make yourself useful) | High | Margin concession |
| Multiple ministries/donor relationships | Medium | BD time |
| Local incorporation and local employment | Medium | None |
| DFI co-investment (IFC, BII) | Medium-High | Dilution; slower |
| Published public-good data | Medium | Low |
| Open-source fallback commitment | Medium | Some IP risk |
| Avoiding association with any political faction | High | Discipline |
| Cash reserves outside the country | Medium | Cost of capital |

**The strongest single protection is being operationally useful to the government.** A platform that
delivers the input subsidy programme for 200,000 farmers is much harder to shut down than one that only
trades grain.

---

## 6. What the platform must never do

| Never | Why |
|---|---|
| Take a side in a conflict | Loses half the market and invites retaliation |
| Pay "security" money to armed groups | Legal exposure; reputational catastrophe |
| Operate in an area where staff safety cannot be assured | Unacceptable risk to people |
| Assume a government commitment survives a minister's departure | Institutionalise every agreement |
| Put a single person at risk to protect revenue | Nothing justifies it |
| Publicly predict political outcomes | Neither competent nor safe |

---

## 7. Scenario: the platform loses its core region

**Suppose Amhara becomes inaccessible for 18 months.**

| Effect | Magnitude |
|---|---|
| GMV loss | 25–35% |
| Revenue loss | ETB 40–60 m/yr at Phase 2 scale |
| Staff | 8–12 relocate or are furloughed |
| Assets | Warehouses leased (limited loss); data replicated (no loss) |
| Buyers | Redirect to Oromia supply |
| Lenders | Portfolio concentration risk; first-loss cover used |
| Morale | Severe |

**Response:**
1. Suspend, do not close — preserve the entity and relationships.
2. Redeploy staff to other regions where possible.
3. Accelerate the next region to replace volume.
4. Communicate transparently to investors and lenders.
5. Re-enter when security permits; the relationships and data survive.

**This scenario should be planned for, not discovered.**

---

## 8. The honest conclusion

**Conflict is the reason this plan may fail, and no amount of good design changes that.** What good
design can do is ensure that:

- The failure is **survivable** (light assets, diversified regions, cash reserves).
- The **people are safe** (clear protocols, no heroism).
- The **assets that matter survive** (data, relationships, software).
- The **organisation can restart** (legal continuity, staff retention, buyer relationships).

A platform that plans for conflict is more likely to be trusted by investors, staff and partners than one
that pretends the risk away.
