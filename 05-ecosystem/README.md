# 05 · The Proposed Digital Ecosystem

*A modular platform: thin shared core, many attachable services*

---

## Files in this section

| File | Contents |
|---|---|
| [`01-architecture.md`](01-architecture.md) | Layered architecture, tech stack, integration points, non-functional requirements |
| [`02-core-layers.md`](02-core-layers.md) | Identity, payments, data & API layer — the shared infrastructure |
| [`03-application-modules.md`](03-application-modules.md) | Marketplace, advisory, logistics, finance, government services |
| [`04-actors-and-incentives.md`](04-actors-and-incentives.md) | Every participant's costs, benefits and reason to stay |
| [`05-data-model-and-consent.md`](05-data-model-and-consent.md) | Entities, consent architecture, data governance |
| [`06-feedback-loops.md`](06-feedback-loops.md) | Why the ecosystem compounds, and where it can stall |

---

## The one-paragraph architecture

A **thin core** (identity, payments orchestration, data/API) supports **six application modules**
(marketplace, advisory, logistics, finance, government services, developer platform). The core is
built once and never duplicated; modules are added, removed or replaced without touching the core.
Farmers interact through **USSD, IVR and agents**; buyers, transporters and staff through
**smartphone and web apps**. All money moves through **licensed partners**; all identity through
**Fayda**; all sensitive data through a **consent layer**.

---

## The diagram

```
╔══════════════════════════════════════════════════════════════════════════════╗
║                          APPLICATION MODULES                                 ║
║                                                                              ║
║  ┌────────────┐ ┌────────────┐ ┌────────────┐ ┌────────────┐ ┌────────────┐  ║
║  │ MARKETPLACE│ │ ADVISORY & │ │ LOGISTICS  │ │ EMBEDDED   │ │ GOVERNMENT │  ║
║  │  & TRADE   │ │    DATA    │ │COORDINATION│ │  FINANCE   │ │ & PROGRAMS │  ║
║  │            │ │            │ │            │ │            │ │            │  ║
║  │ listings   │ │ prices     │ │ load board │ │ input      │ │ vouchers   │  ║
║  │ bids       │ │ weather    │ │ booking    │ │ credit     │ │ transfers  │  ║
║  │ contracts  │ │ pests      │ │ tracking   │ │ insurance  │ │ e-permits  │  ║
║  │ grading    │ │ agronomy   │ │ proof-del. │ │ savings    │ │ M&E        │  ║
║  │ escrow     │ │ 5 langs    │ │ freight pay│ │ mechanise  │ │ analytics  │  ║
║  └─────┬──────┘ └─────┬──────┘ └─────┬──────┘ └─────┬──────┘ └─────┬──────┘  ║
╚════════╪══════════════╪══════════════╪══════════════╪══════════════╪═════════╝
         │              │              │              │              │
╔════════╧══════════════╧══════════════╧══════════════╧══════════════╧═════════╗
║                          SHARED CORE (BUILD ONCE)                            ║
║                                                                              ║
║  ┌──────────────────────────────────────────────────────────────────────┐   ║
║  │  IDENTITY & AUTHENTICATION                                            │   ║
║  │  Fayda eKYC · eSignet/OIDC · role credentials · agent binding        │   ║
║  │  biometric fallback hierarchy · SIM-swap detection                   │   ║
║  └──────────────────────────────────────────────────────────────────────┘   ║
║  ┌──────────────────────────────────────────────────────────────────────┐   ║
║  │  PAYMENTS ORCHESTRATION                                               │   ║
║  │  routing · escrow instructions · split settlement · bulk disbursement │   ║
║  │  telebirr · M-Pesa · bank APIs · EthSwitch · agent cash ledger        │   ║
║  └──────────────────────────────────────────────────────────────────────┘   ║
║  ┌──────────────────────────────────────────────────────────────────────┐   ║
║  │  DATA, CONSENT & API LAYER                                            │   ║
║  │  farmer & plot registry · transaction ledger · consent registry       │   ║
║  │  price & weather data · public API · partner API · developer sandbox │   ║
║  └──────────────────────────────────────────────────────────────────────┘   ║
╚════════╤══════════════╤══════════════╤══════════════╤══════════════╤═════════╝
         │              │              │              │              │
╔════════╧══════════════╧══════════════╧══════════════╧══════════════╧═════════╗
║                       EXTERNAL RAILS (INTEGRATE, DON'T BUILD)                ║
║                                                                              ║
║  FaydaVerse    EthSwitch      telebirr     M-Pesa       Banks      EthioMet  ║
║  (identity)    (switch)       (wallet)     (wallet)     (credit)   (weather) ║
║                                                                              ║
║  ATI 8028/6077   ECX grading    MoA DAR      AI Institute   Ethio Telecom    ║
║  (advisory)      (warehouse)   (programs)   (language AI)   (USSD/SMS)       ║
╚══════════════════════════════════════════════════════════════════════════════╝

╔══════════════════════════════════════════════════════════════════════════════╗
║                             ACCESS CHANNELS                                  ║
║                                                                              ║
║   USSD        IVR          SMS        Agent app      Buyer app/web           ║
║   (farmer)    (farmer)     (farmer)   (smartphone)   (smartphone/web)        ║
║                                                                              ║
║   Driver app  Staff console  Public price board  Open API                    ║
╚══════════════════════════════════════════════════════════════════════════════╝
```

---

## Why this architecture and not a monolith

| Requirement | Monolithic app | Modular platform |
|---|---|---|
| Add a new commodity | Rebuild flows | Configure |
| Add a region | Rebuild | Configure |
| Partner with a bank | Custom integration | API |
| Change payment rail | Rewrite | Swap adapter |
| Regulator asks for an audit trail | Scramble | Already logged |
| Third party builds a mini-app | Impossible | Sandbox + API |
| One module fails | Everything fails | Isolate and fix |

---

## The six non-negotiable design rules

1. **Never build a rail.** Identity, payments, connectivity and the switch are provided. Integrate.
2. **Never hold customer money.** Use a licensed custodian. Instruct, don't custody.
3. **Never store biometrics.** Verify through FaydaVerse; keep the result and reference only.
4. **USSD/IVR/agent is the primary channel.** Apps are for the literate and equipped minority.
5. **Consent is a first-class entity**, not a checkbox: stored, versioned, revocable, auditable.
6. **Every transaction is double-entry and idempotent.** Payment correctness is a hard requirement.

---

## Build-versus-buy decisions

| Capability | Build | Buy / integrate | Why |
|---|---|---|---|
| Identity verification | — | FaydaVerse | National, free to citizens, mandatory |
| Payments | — | telebirr, M-Pesa, EthSwitch, banks | Licensed, ubiquitous |
| SMS/USSD gateway | — | Ethio Telecom, Safaricom | Only they can deliver |
| Weather data | — | EthioMet, ATI, satellite providers | Public good |
| Advisory content | Co-develop | ATI, EIAR, 8028 | Do not reinvent agronomy |
| Grading standards | — | ECX, MoA | Standards are public |
| Marketplace logic | **Build** | — | Core IP |
| Consent registry | **Build** | — | Differentiator and compliance |
| Credit scoring | **Build** | — | Core IP |
| Logistics dispatch | **Build** | — | Core IP |
| Voice AI for local languages | Integrate | AI Institute | National capability |
| Core ledger | **Build** (or proven open-source) | — | Correctness matters |

**The rule of thumb:** build what encodes your data and relationships; integrate everything that is
provided by a licensed or public entity.

---

## What this ecosystem becomes at maturity

At Phase 4–5, the platform is no longer an app. It is:

- the **identity-verified registry** of millions of farmers and their plots;
- the **transaction ledger** of Ethiopian agriculture;
- the **underwriting substrate** for the rural credit market;
- the **delivery channel** for state and donor programmes;
- the **traceability layer** for export compliance;
- the **API** that other companies build on.

That is national digital infrastructure — and the reason the state should want it to succeed, even if
it did not build it.

---

## Read next

- [`01-architecture.md`](01-architecture.md) — the technical blueprint
- [`05-data-model-and-consent.md`](05-data-model-and-consent.md) — the part that becomes the moat
