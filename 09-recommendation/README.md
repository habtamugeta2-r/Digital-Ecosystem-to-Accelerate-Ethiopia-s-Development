# 09 · Recommendation

*The answer to the question the whole repository asks: what should be built, and how?*

---

## Files in this section

| File | Contents |
|---|---|
| [`01-the-recommendation.md`](01-the-recommendation.md) | The recommendation, in full |
| [`02-what-to-build-first.md`](02-what-to-build-first.md) | The specific MVP scope |
| [`03-what-not-to-do.md`](03-what-not-to-do.md) | Explicit exclusions and why |
| [`04-decision-checklist.md`](04-decision-checklist.md) | What must be true before starting |

---

## The recommendation in one page

**Build a digital agricultural supply-chain platform for Ethiopian smallholders — agent-anchored,
Fayda-native, escrow-settled, and designed from day one to become the transaction layer that credit,
insurance, logistics and government services plug into.**

### Why this, and not the alternatives

| Option | Score /40 | Verdict |
|---|---|---|
| **Agricultural supply-chain platform** | **35** | **Build this** |
| Digital financial services (standalone) | 33 | Build only as a layer *on* the platform; never compete with telebirr |
| Government services (Irembo model) | 27 | Requires a state mandate; partner instead |
| E-commerce and logistics | 26 | Phase 3 at the earliest; unit economics don't work today |
| Standalone logistics | 26 | Too capital intensive; a feature, not a business |
| Connectivity | 25 | Someone else's business; regulated and capital-heavy |
| Human capital | 24 | Real need, but not a platform business |

**Agriculture wins on three of four weightings** (see [`02-opportunities/06-scoring-and-ranking.md`](../02-opportunities/06-scoring-and-ranking.md)).
It is large, painful, data-generating, and it unlocks the highest-margin business (credit).

### The five design commitments

1. **Narrow before wide.** One commodity, one region, one season, done properly — before anything else.
2. **Agent-anchored.** USSD/IVR for farmers, an offline app for agents, and a human in every transaction.
3. **Identity-native.** Every participant has a Fayda ID. Never store biometrics.
4. **Escrow-settled.** Funds held by a licensed institution; the platform never touches the money.
5. **Data as the asset.** The verified transaction ledger is the business. Everything else is a way of
   generating it.

### The five phases

| Phase | Months | What | Gate |
|---|---|---|---|
| 0 | 0–6 | Licences, partners, design | Escrow + Fayda + 3 buyers |
| 1 | 6–18 | Single-commodity pilot, Oromia | ≥5% net price gain, ≥40% repeat |
| 2 | 18–36 | Advisory, logistics, credit, 3 regions | 2 lenders, PAR-30 <7%, ≥150k farmers |
| 3 | 36–54 | National footprint, 6–7 commodities | EBITDA positive |
| 4–5 | 54–84 | Open API, developer ecosystem, government integration | 20% GMV from third parties |

### The capital requirement

**~ETB 80 m (US$0.5 m) to break-even, ~ETB 200 m (US$1.3 m) raised for safety.** Small for a national
platform — which is both the opportunity (capital efficiency) and the warning (fragility).

### The three things that must be true

| Assumption | Test | If false |
|---|---|---|
| Farmers earn ≥5% net more | Pilot cohort vs. matched comparison | **Stop.** The proposition is false |
| Farmers come back (≥40%) | Second-season cohort | Fix experience or stop |
| Credit repays (PAR-30 <7%) | First 1,000 loans | Stop lending; become a data provider |

**Everything else is adaptation. These three are the thesis.**

---

## What makes this recommendation different from a typical "digital strategy"

| Typical strategy | This recommendation |
|---|---|
| Build a national platform | Build one region's transactions |
| Start with the technology | Start with the licence, the partner and the buyer |
| Assume smartphone adoption | Assume USSD, IVR and agents, permanently |
| Target all commodities | Target one commodity until it works |
| Promise impact in year 1 | Measure impact in year 3 |
| Raise for growth | Raise for survival to break-even |
| Compete with the state | Partner with the state |
| Build a super-app | Build a settlement layer others build apps on |

---

## The honest summary

> Ethiopia's structural problems are not solvable by an app. But there is a specific, tractable,
> valuable problem in the middle of them: **no one in the country can verify what a smallholder
> produced, or whether they repaid a loan.** Building that record — transaction by transaction, season
> by season — is a business. It is also the foundation of every financial service Ethiopian agriculture
> needs and does not have.
>
> The windows for this are open now because Fayda, telebirr, EthSwitch and the national payments
> strategy have built the rails. The window closes when someone else builds the ledger first — and that
> person is most likely the state, a telco, or a bank.
>
> **Build narrow, build agent-anchored, build identity-native, and build for the seventh year, not the
> second.**

---

## Read next

- [`01-the-recommendation.md`](01-the-recommendation.md) — the full argument
- [`02-what-to-build-first.md`](02-what-to-build-first.md) — the MVP
- [`04-decision-checklist.md`](04-decision-checklist.md) — go/no-go
