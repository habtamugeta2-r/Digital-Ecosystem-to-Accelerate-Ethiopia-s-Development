# 04.4 · Language and Literacy

*Part of [04 · Constraints](README.md)*

> **The constraint in one line.** You are building for someone who **cannot reliably read**, speaks
> one of 80+ languages, and has been failed by nine years of schooling.

---

## 1. The language landscape

| Language | Approximate speakers (L1+L2) | Script | Status in digital services |
|---|---|---|---|
| Amharic | ~35–40 m | Ethiopic (Ge'ez) | Best supported; working language of federal government |
| Afaan Oromo | ~35–40 m | Latin (Qubee) | Supported by 8028; growing app support |
| Tigrinya | ~7–9 m | Ethiopic | Supported by 8028 |
| Somali | ~6–8 m | Latin | Supported by 8028 |
| Afar | ~2–3 m | Latin | Supported by 8028 |
| Sidama, Wolaytta, Gurage, Hadiyya, etc. | 1–3 m each | Latin/Ethiopic | Largely unsupported |
| English | Elite/urban | Latin | Official secondary language; not a farmer language |
| Arabic | Border/religious | Arabic | Niche |
| Total languages | **80+** | mixed | — |

**The 8028 precedent matters:** Ethiopia's national farmers' hotline already operates in **five
languages** (Amharic, Afaan Oromo, Tigrinya, Somali, Afar). That is a proven, government-endorsed MVP
language set. Any new platform should adopt it rather than inventing its own.

---

## 2. The literacy reality

| Indicator | Value | Implication |
|---|---|---|
| Learning poverty (cannot read a simple text at age 10) | **90%** | Text-based UI is not a viable primary channel |
| Net primary enrolment | ~89% | Enrolment is not the problem; learning is |
| Grade 12 students failing to reach 50% | 97% (2024) | Even secondary graduates have weak foundation skills |
| Adult literacy (self-reported) | ~52% (varies) | Roughly half of adults |
| Numeracy | Low; especially for multi-step calculations | Price per quintal vs. per kg conversions are error-prone |

**Design consequence:** the median user may be able to **recognise a number, a price and a name**, but
may not read a sentence, understand a percentage, or convert units. Every screen and every IVR menu
must be designed to that standard.

---

## 3. What this forces, concretely

### 3.1 Channel design

| Channel | Language capability | Literacy requirement |
|---|---|---|
| IVR (voice) | Full — recorded prompts in 5 languages | **None** — listen and press a digit |
| USSD | Text in local script | Recognise words and numbers |
| SMS | Text in local script or Latin transliteration | Read short messages |
| Agent | Human | **None** |
| App | Text + icons + images | Basic literacy |

**Therefore: IVR and agents are the universal channels. USSD/SMS are the literate-majority channels.
Apps are the agent-and-buyer channel.**

### 3.2 Interface rules

| Rule | Why |
|---|---|
| Max 5 menu options per IVR level, numbered | Working-memory and comprehension limits |
| No free-text input on farmer flows | Spelling, script, transliteration errors |
| Commodity and region codes as numbers, with printed cards | Recognition over recall |
| Prices always stated in **birr per quintal** and **birr per kg** | Avoids unit confusion, the most common transactional error |
| Visual price boards at cooperatives | Community-visible, no device needed |
| Speech output for every confirmation | Payment confirmations must be heard, not just read |
| Reading the amount twice in confirmations | Prevents digit mishearing |
| Icons tested with non-readers | Written descriptions of icons fail illiterate users |

### 3.3 Voice technology

| Capability | Status in Ethiopia | Use |
|---|---|---|
| Recorded IVR prompts | Mature (8028) | MVP — record all prompts |
| Speech-to-text, Amharic/Afaan Oromo | Developing; Ethiopian AI Institute working on machine-readable local languages | Post-MVP for query handling |
| Text-to-speech, local languages | Developing | Advisory generation at scale |
| Voice authentication | Early | Avoid as a security factor |
| AI conversational agents | Early | High potential but not yet trustworthy for financial instructions |

**Recommendation:** launch with **recorded human voice prompts** (highest trust, lowest risk). Adopt AI
voice when the AI Institute's local-language models are validated — and never for irreversible
financial actions without a second confirmation.

---

## 4. Translation is not localisation

A translated interface still fails if the *concepts* are foreign. Examples:

| Concept | Foreign framing | Local framing that works |
|---|---|---|
| "Escrow" | A financial term | "The money is kept safe until you get your grain" |
| "Credit score" | A number | "The platform knows you have sold 40 quintals twice and paid back — the bank will lend to you" |
| "Insurance" | A product | "You pay a little now; if the rain fails, you get your seed money back" |
| "Marketplace" | A place | "Gebeya" (market) — the physical market people know |
| "Digital wallet" | A technology | "Your phone's money" |
| "Platform fee" | An abstraction | "A small share when you sell, like the broker's, but smaller and fixed" |

**Design process:** concept testing with farmers in the pilot region, in the local language, using
non-literate participants. Do not test only with cooperative officials.

---

## 5. Naming and brand

The source brief proposed the name **"MeroMero"** (from *mero*, market/auction in Amharic) for the
pilot. That is a reasonable direction but note:

- A name in one language can be meaningless or unintentionally comic in another.
- Brand names should be **pronounceable in all five MVP languages** and should not contain sounds
  that are ambiguous on a poor phone line.
- The name should be tested for meaning before commitment. *Mero* is auction; *gebeya* is market;
  *souk* is also used in some regions; *lersha* means "for agriculture."

**Recommendation:** test 3–5 candidate names with farmers in each pilot region; select on
recognition, pronunciation over IVR, and absence of negative meaning. Do not commit to a name before
the pilot region is chosen.

---

## 6. Content and advisory localisation

| Content type | Approach |
|---|---|
| Weather forecasts | Reuse EthioMet + ATI channels; adapt language, not data |
| Pest and disease alerts | Local crop names must map to botanical species (a single crop may have 3 local names) |
| Agronomy | Co-develop with ATI/EIAR; do not invent; validate with development agents |
| Market prices | Always include market name in local pronunciation |
| Contract terms | Read aloud by agent; recorded in local language; SMS copy in local script |
| Dispute process | Voice explanation, not written policy |

**Cost reality:** five languages × all content = ~5× the content cost. Plan for it in the budget, and
launch only 2–3 languages in Phase 1 (Amharic + the pilot region's language + optionally Tigrinya or
Somali), expanding in Phase 2. This is a deliberate deviation from the 8028 set, justified by pilot
scope.

---

## Decisions forced

| Decision | Choice |
|---|---|
| MVP language set | 2–3 (Amharic + pilot region language), extending to the 8028 five-language set by Phase 2 |
| Primary channel for low-literacy users | IVR + agent; never USSD-only |
| Voice technology | Recorded human prompts at launch; AI voice later |
| Unit convention | Always quote birr/quintal and birr/kg |
| Content source | Reuse ATI/EIAR/8028 content; do not recreate |
| Naming | Test 3–5 candidates in pilot region; do not pre-commit |
| Testing method | Non-literate participant testing in the local language |
