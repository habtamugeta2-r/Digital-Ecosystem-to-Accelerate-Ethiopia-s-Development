# 03.5 · Super-apps: China and Southeast Asia

*Part of [03 · International models](README.md)*

> **Why study it.** WeChat, Alipay, Grab and Gojek are the most-cited "platform" examples in strategy
> documents — and the most frequently misapplied to Africa. This file sets out what actually
> transfers, and why the super-app model is largely unavailable to Ethiopia.

---

## 1. The four models

| Model | Origin | Wedge | Expansion path |
|---|---|---|---|
| **WeChat** | China, 2011 | Messaging | Mini-programs, payments, services, commerce |
| **Alipay** | China, 2004 | Escrow for e-commerce (Taobao) | Wallet → wealth → credit → services → super-app |
| **Grab** | Malaysia, 2012 | Ride-hailing | Payments, food, delivery, financial services |
| **Gojek** | Indonesia, 2010 | Ride-hailing (ojek) | Payments, food, logistics, services |

---

## 2. What actually made them work

### 2.1 A high-frequency wedge

Every one started with a **daily-use transaction**:
- WeChat: messaging (dozens of times a day)
- Alipay: escrow on Taobao purchases (frequent, high-trust-requiring)
- Grab/Gojek: transport (several times a week)

High frequency → habit → default payment method → permission to attach services.

**Ethiopian translation:** what is the daily-use wedge for a smallholder? Not transport (too sparse),
not messaging (telecom-owned), not e-commerce (1% purchase rate). The realistic wedges are **(a) the
sale transaction, which happens a few times a season, and (b) price/weather information, which can be
daily.** The information wedge is what builds the daily habit; the transaction is what builds the
business.

### 2.2 Owning the payment moment

Alipay's origin is instructive: it existed to solve **trust** in a distance transaction (buyer and
seller who never meet). It held the money until delivery. That is precisely the escrow function an
Ethiopian agricultural marketplace needs.

**Ethiopia already has this solved at the rail level (EthSwitch, wallets), but not at the product
level.** "Escrow on delivery confirmation, for a grain trade between a farmer in Bale and a miller in
Addis" is not a service anyone offers today.

### 2.3 Mini-programs / open platform

WeChat's mini-programs let third parties build inside the app without app-store friction. This is
how a messaging app became an operating system.

**Ethiopian translation:** too early. Data costs, device limits and 22% internet penetration make a
rich mini-program ecosystem unrealistic before Phase 4. But an **API layer** that lets third parties
integrate without a full partnership is realistic from Phase 2–3.

---

## 3. Why the super-app model does not transfer

| Requirement | China/SEA (2015–2020) | Ethiopia (2026) |
|---|---|---|
| Rising disposable income | Rapidly rising middle class | 43% below US$3/day; GDP per capita ~US$1,300–1,500 |
| Smartphone penetration | 60–70% at take-off | ~30% (extrapolated); 58% own any phone |
| Cheap, ubiquitous data | Aggressive price competition | 22% internet penetration |
| Venture capital willing to subsidise losses for years | Enormous (Grab raised >US$10 bn) | Very thin; Ethiopian startups earn <US$20k/yr in 70% of cases |
| Dense urban geography | Jakarta, Shanghai, Beijing | Only Addis approaches density |
| Addressable delivery economics | High order values, short distances | Low order values, long distances, poor roads |
| Regulatory space to operate payments | Varied | Tightly regulated by NBE |

**The arithmetic that kills the super-app in Ethiopia:** a super-app needs a customer to transact
frequently at a value where a 1–3% take rate covers service cost. In a market where the average
digital consumer purchase is small and 1% of adults buy online, the transaction frequency is not
there. **The agricultural B2B transaction, by contrast, is ETB 750,000 per truckload.**

---

## 4. What *does* transfer

| Transferable | Application |
|---|---|
| **Start with one high-frequency, trust-critical transaction** | Escrowed grain trade; the trust requirement is the product |
| **Attach services to the payment moment** | At settlement, offer credit, insurance, savings, logistics — all contextually relevant |
| **Design for the lowest-end device first** | Alipay and WeChat both worked on cheap Android; Ethiopia needs USSD-level |
| **Own the customer relationship, not the rail** | Be the app the farmer trusts, not the wallet they hold |
| **Use agents for onboarding** | Gojek's driver fleet and Grab's driver network are agent networks in another form |
| **Build a two-sided liquidity engine** | Subsidise one side (buyers or farmers) until the other arrives — this is the core marketplace discipline |

---

## 5. The Alipay escrow lesson, in detail

Alipay's founding problem (2004): Chinese e-commerce was stalled because buyers would not pay first
and sellers would not ship first. Alipay held the money.

**Ethiopia's version of the same problem:**
- A farmer in a rural woreda will not ship 80 quintals of grain to a miller in Addis on a promise.
- A miller will not send ETB 2 million to a farmer he has never met.
- Today this is solved by **physical intermediation**: the trader travels, inspects, pays cash, and
  arranges transport — capturing a spread of 10–30%.

**The escrow product is therefore not a payments feature; it is the removal of a middleman's
economic raison d'être.** That is the highest-value single feature in the proposed platform, and it
requires: verified identity (Fayda), held funds (a licensed partner), delivery confirmation (photo +
geotag + OTP), and a dispute process.

---

## 6. Grab/Gojek's logistics lesson

Both built **driver fleets** that later became general logistics networks. The fleet is the asset.

**Ethiopian translation:** do not build a fleet. Contract owner-operators and cooperative trucks, but
**own the dispatch, the payment and the reliability data.** The data is the asset; the trucks are
commodity.

---

## Key takeaways

1. Super-apps were built on **daily-use wedges, rising incomes, cheap smartphones, and enormous VC
   subsidy** — three of those four are absent in Ethiopia.
2. The transferable core is **escrow on a trust-critical transaction**, then attaching services at the
   payment moment.
3. Alipay's escrow is the single most relevant product analogy for an Ethiopian agricultural
   marketplace: it removes the middleman's reason to exist.
4. Own the **customer relationship and the data**, not the rail and not the fleet.
5. A super-app for Ethiopia is a Phase 5+ question at best; the near-term product is a **bulk B2B
   transaction engine with an escrow at its centre.**
