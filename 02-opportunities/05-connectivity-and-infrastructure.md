# 02.5 · Connectivity and Infrastructure: the Enabling Layer

*Part of [02 · Opportunities](README.md) · Enabler, not an opportunity to enter*

> **Verdict.** Connectivity is the single largest determinant of what is possible — and the single
> worst thing for a software organisation to try to build. This file documents the state of the
> enabling layer, because **every product decision depends on it.**

---

## 1. The connectivity picture

| Indicator | Value | Date | Confidence |
|---|---|---|---|
| Population | ~135.5 m | 2025 | 🟢 |
| Internet users | **29.5 m (21.7%)** | Oct 2025 | 🟡 |
| Cellular connections | 93.2 m (68.4%) | Oct 2025 | 🟡 |
| Social media user identities | ~9.8 m (7.2%) | Oct 2025 | 🟡 |
| Ethio Telecom total customers | 90.12 m | FY2025/26 | 🟡 |
| Ethio Telecom active mobile subscribers | 72.09 m | FY2025/26 | 🟡 |
| Ethio Telecom 4G population coverage | **82.23%** (6,924 sites) | FY2025/26 | 🟡 |
| Ethio Telecom 5G | 340 sites; 33 cities (target 648 sites, 73 cities by Jun 2027) | FY2025/26 | 🟡 |
| Ethio Telecom fixed broadband | 847,100 subscribers (+67.2%) | FY2024/25 | 🟡 |
| Safaricom Ethiopia 90-day active | **15 m+** | Sep 2026 | 🟡 |
| Safaricom 4G population coverage | ~59.2–60% (3,504 sites) | Mar 2026 | 🟡 |
| Safaricom 5G | None — no spectrum allocated | 2026 | 🟡 |
| Rural internet penetration | ~9% | 2021 | 🟠 |
| Urban internet penetration | ~42% | 2021 | 🟠 |
| Average mobile download speed | ~32.8 Mbps | 2025 | 🟡 |
| Cost of a low-consumption 3G basket | ~1.69% of GNI per capita | 2025 | 🟡 |
| Fibre backbone | ~23,000 km (Ethio Telecom, 2023) | 2023 | 🟠 |
| Data centres | 2; 1 active IXP | 2025 | 🟡 |

### 1.1 The numbers disagree — and that matters

Ethiopia has **at least three defensible internet-user counts**: DataReportal (29.5 m, 21.7%),
the Ministry of Innovation and Technology (42 m+), and operator-reported subscriber totals
(57 m internet users cited by Ethio Telecom in late 2025). The differences are definitional:
unique people vs. subscriptions vs. any-use-in-90-days.

**Rule for planning:** use the **lowest** credible number (≈22% of the population, and roughly
**9% in rural areas**) for product design. Use the higher numbers only for market sizing upside.

> ⚠️ **Correction to the source brief.** The brief states "~43 million Ethiopians (~34% of 127M)
> were online as of late 2024 (up from 17M in 2018)" and that "98% use 3G and 33% use 4G". Neither
> figure is supported by current data: the widely cited 2024–25 figures put internet users at
> **28.6–29.5 million (21–22%)**, and Ethiopia's network is now majority **4G by population coverage
> (82.2%)**, with 3G as a residual. Use the corrected figures.

---

## 2. Why connectivity is improving faster than usage

This is the central paradox of Ethiopian digital policy: **network coverage is now high; usage is
not.**

| Coverage | Usage |
|---|---|
| 4G reaches 82% of the population | 22% of people use the internet |
| 93.2 m cellular connections | 29.5 m internet users |
| 60.6 m telebirr accounts | 49% of adults have any account; 21% made a digital payment |

**The gap is explained by:** device cost, electricity access, digital literacy (90% learning
poverty), the cost of data relative to income, and the absence of compelling local-language
services. Coverage was the binding constraint until ~2023; **it is no longer.** The binding
constraints are now **smartphones, power and usable local services.**

The policy target — **70% adult smartphone ownership by 2030** — is an implicit admission that
devices are the current bottleneck.

---

## 3. Electricity: the hidden constraint

| Indicator | Value | Date | Confidence |
|---|---|---|---|
| Households with access to any electricity source | 65% | Jan 2025 | 🟢 |
| Connected to the national grid | 29.3% | Jan 2025 | 🟢 |
| Relying on off-grid solar | 35.7% | Jan 2025 | 🟢 |
| **Access at Tier 1 or above (basic service)** | **44%** | 2025 | 🟢 |
| World Bank electricity access estimate | 56.6% | 2024 | 🟡 |
| 2030 target | 75% (70% grid / 30% off-grid) | policy | 🟢 |
| Installed generation capacity | ~10,000 MW | 2026 | 🟡 |
| Distribution losses | ~20% | 2026 | 🟠 |

> ⚠️ **Correction to the source brief.** The brief says "half the population still lacks reliable
> electricity". The more precise and more useful figures are: **65% have some electricity access**
> (mostly off-grid solar), but only **44% have Tier-1-or-above service**. Both numbers are true; the
> Tier-1 figure is the one that governs whether a phone can be reliably charged.

**Product consequence:** any design that assumes a device is charged every day will fail for ~56% of
the population. Agent devices must be solar-capable and battery-tolerant; farmer-facing flows must be
USSD/IVR (which work on any handset for a short call) rather than app-based.

---

## 4. Devices and affordability

| Indicator | Value | Confidence |
|---|---|---|
| Adult mobile phone ownership | 58% | 🟢 Findex 2024 |
| Smartphone ownership | not officially reported; target 70% by 2030 | 🟠 |
| Data cost, low-consumption basket | 1.69% of GNI per capita | 🟡 |
| ITU affordability threshold | 2% of GNI per capita | 🟢 |
| Local device assembly | Government announced domestic laptop/tablet manufacturing plans | 🟠 |

> **The 58% mobile ownership figure is the most operationally important number in this file.** Four
> in ten Ethiopian adults do not own a phone. Any product that assumes "every farmer has a phone"
> excludes the poorest 40% — precisely the population the intervention is meant to serve. **This is
> why the agent layer is not optional.**

---

## 5. What the platform should do about infrastructure

| Do | Don't |
|---|---|
| Build on USSD, IVR, SMS as first-class channels | Build app-only products |
| Design offline-first field apps with sync | Assume connectivity at the point of transaction |
| Use agents with solar chargers and battery banks | Assume daily device charging |
| Negotiate bulk SMS/USSD rates with Ethio Telecom and Safaricom | Pay retail rates at scale |
| Publish data-light interfaces (text-first, <100 KB) | Ship image-heavy UI |
| Monitor network quality by region and route traffic | Assume uniform performance |
| Use the national cloud / AI Institute for local-language models | Assume English-language NLP |
| Build multi-operator redundancy (Ethio Telecom + Safaricom) | Single-carrier dependency |
| Consider satellite backhaul for remote aggregation points | Assume fibre reaches rural areas |
| Lobby (with others) for device subsidies and zero-rating of advisory | Build your own network |

---

## 6. The policy lever worth watching

Three developments could change the economics of rural digital services materially:

1. **Device financing and local assembly.** If the government's laptop/tablet manufacturing and
   smartphone affordability agenda succeeds, app-based services become viable for a much larger
   share of farmers.
2. **Zero-rating of agricultural and health content.** Common in other African markets; a single
   regulatory decision would multiply the reach of advisory services at no cost to the platform.
3. **5G and fixed-wireless access.** Ethiopia has 340 5G sites (Ethio Telecom) but no Safaricom 5G
   spectrum. Urban 5G will not change rural agriculture, but fixed-wireless in secondary cities will
   improve aggregation-point connectivity.

---

## Key takeaways

1. **Coverage is no longer the binding constraint** — 82% 4G population coverage, 93 m connections.
   Usage is: 22% internet penetration, 58% adult phone ownership.
2. Use the **lowest** credible connectivity figure (~9% rural internet) for design.
3. **44% Tier-1 electricity and 58% phone ownership** make USSD/IVR and agent intermediation
   permanent, not transitional.
4. Data is affordable by ITU standards (1.69% of GNI) but not by household standards in a country
   where 43% live below US$3/day.
5. Do not build networks. Negotiate rates, use national cloud and language models, and build for the
   device people actually have.
