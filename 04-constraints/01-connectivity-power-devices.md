# 04.1 · Connectivity, Power and Devices

*Part of [04 · Constraints](README.md)*

> **The constraint in one line.** Coverage is solved; **usage, devices and electricity are not.**

---

## 1. The numbers that matter

| Indicator | Value | Date | Why it matters |
|---|---|---|---|
| Internet users | 29.5 m (**21.7%**) | Oct 2025 | Defines the addressable digital population |
| Rural internet penetration | ~9% | 2021 (latest) | The target population is largely offline |
| Adult mobile phone ownership | **58%** | 2024 | 42% of adults cannot receive an SMS |
| Cellular connections | 93.2 m (68.4%) | Oct 2025 | Connections ≠ people |
| 4G population coverage (Ethio Telecom) | 82.23% | FY2025/26 | Coverage is no longer binding |
| 4G population coverage (Safaricom) | ~59–60% | Mar 2026 | Second operator adds redundancy |
| Electricity, any source | 65% of households | Jan 2025 | Mostly off-grid solar |
| Electricity, Tier 1+ | **44%** | 2025 | Reliable charging is a minority experience |
| Average mobile download speed | ~32.8 Mbps | 2025 | Adequate where available |
| Data cost | 1.69% of GNI per capita | 2025 | Just under the ITU 2% threshold |
| Speakers of the top 5 languages | Amharic, Afaan Oromo, Tigrinya, Somali, Afar — the languages 8028 supports | — | Determines MVP language set |

---

## 2. What this forces

| Constraint | Product decision | Consequence if ignored |
|---|---|---|
| 42% of adults have no phone | **Agent intermediation is mandatory** | The poorest 40% are excluded — the exact population the intervention targets |
| 78% of the population is not online | **USSD, IVR and SMS are primary channels** | App-only products reach <20% of the intended users |
| 56% lack Tier-1 electricity | **Agent devices must be solar/battery-capable**; short sessions; no video | Devices die; agents stop working; data goes stale |
| Data costs 1.69% of GNI | **Text-first UI; <100 KB per session; no images on farmer flows** | Users abandon on cost |
| Rural coverage is patchier than national | **Offline-first field apps with queue-and-sync** | Data loss at point of transaction |
| Literacy is low (90% learning poverty) | **Voice-first IVR in five languages** | Misuse, errors, abandonment |
| Network outages are common | **Idempotent transactions; SMS confirmation fallback; no dependency on real-time connectivity** | Duplicate or lost payments — unrecoverable trust damage |

---

## 3. The channel architecture

```
┌─────────────────────────────────────────────────────────────────────┐
│  FARMER-FACING CHANNELS (no smartphone required)                    │
│                                                                     │
│  USSD short code    → list, check price, confirm sale, check balance │
│  IVR toll-free      → advisory, price quote, pest alerts             │
│  SMS push           → daily prices, weather, contract confirmations  │
│  Cooperative agent  → assisted registration, cash-in/out, dispute    │
└─────────────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────────────┐
│  AGENT / BUYER / TRANSPORTER APPS (smartphone, offline-tolerant)     │
│                                                                     │
│  Agent app: onboarding, listing entry, cash ledger, commission       │
│  Buyer app/web: search, bid, contract, pay                           │
│  Driver app: trip accept, POD capture, tracking                      │
└─────────────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────────────┐
│  BACK END (cloud, Ethiopia-hosted)                                   │
└─────────────────────────────────────────────────────────────────────┘
```

**The single most important design rule:** the *default* farmer experience is a **30-second USSD
session or a phone call to an agent.** Everything else is an enhancement.

---

## 4. USSD: the constraints within the constraint

USSD is universal but technically hostile:

| Limitation | Design response |
|---|---|
| 182-character session limit per screen | Numbered menus; ≤6 options; no free text where avoidable |
| Session timeouts (typically 20–120 s) | Multi-step flows must resume; state stored server-side by MSISDN |
| No rich display | Numeric codes for commodities/regions; printed code cards at cooperatives |
| Per-session charges to the user | Negotiate toll-free/zero-rated USSD with Ethio Telecom and Safaricom |
| Concurrent session limits on the operator side | Batch and queue high-volume campaigns |
| Text-only | Pair with IVR for anything explanatory |

**Negotiation priority:** a **zero-rated USSD short code** is worth more than any feature in the
first year. It is the difference between 22% reach and 68% reach.

---

## 5. Electricity and the agent

An agent with a dying phone is a broken distribution channel. Practical specification:

| Requirement | Specification |
|---|---|
| Power | Solar panel + battery bank sized for 2 days of autonomy, or a grid connection with UPS |
| Device | Rugged Android, ≥4,000 mAh, ≥Android 8, works at 2G/3G fallback |
| Session model | Short, batched; sync when connected |
| Connectivity | Dual SIM (Ethio Telecom + Safaricom) for redundancy |
| Data plan | Bulk data bundle negotiated centrally, not per agent |
| Spares | Swap-out program so a failed device does not stop an agent |

**Cost implication:** roughly US$250–450 per agent kit (device + solar + battery + SIM). For 5,000
agents that is US$1.25–2.25 m — a material but bounded capital line, and one that can be financed or
donated separately from the operating budget.

---

## 6. The connectivity trend that changes the model

| Trend | Implication | Horizon |
|---|---|---|
| 4G coverage → 95% (Ethio Telecom target) | Rural data becomes usable | 2027 |
| 5G expansion to 73 cities | Secondary-city aggregation points get fast links | 2027 |
| Smartphone target 70% of adults | App-based flows become viable for the majority | 2030 |
| Local device assembly plans | Device cost falls | 2027–2030 |
| Potential zero-rating of agri/health content | Advisory reach multiplies at zero marginal cost | Policy-dependent |

**Planning rule:** build the USSD/IVR/agent system now, but architect for a smartphone future. Do not
build two products; build one service layer with multiple channels.

---

## Decisions forced

| Decision | Choice | Rationale |
|---|---|---|
| Primary farmer channel | USSD + IVR + agent | 58% phone ownership, 90% learning poverty |
| Secondary channel | SMS push | Cheap, universal, asynchronous |
| App usage | Agents, buyers, transporters, staff only | They are literate, motivated and equipped |
| Device procurement | Solar-capable agent kits | 44% Tier-1 electricity |
| Connectivity posture | Offline-first, idempotent, multi-SIM | Outages are routine |
| Cost to farmer | Zero-rated USSD and toll-free IVR (negotiated) | 1.69% of GNI for data is unaffordable at scale |
| Language set | 5 at MVP | Matches 8028's proven set |
