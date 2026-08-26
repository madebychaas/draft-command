# Draft Command

**Real-Time Adversarial Decision Intelligence**

*A predictive decision system for sequential choice under uncertainty.*

Draft Command turns a chaotic live fantasy draft into a clearer decision environment. It combines live state, league-specific context, player value, market behavior, and timing pressure to produce one actionable recommendation for the decision **right now**.

> **One decision. All the intelligence behind it.**

---

## What you get

Draft Command gives you **real-time decision intelligence for live drafting**.

Instead of static rankings, you get:

- **A current recommendation** — one clear answer when it is your turn.
- **Ranked backup options** — the next best moves if the room changes before you act.
- **A concise explanation of why** — enough context to act without reading a model dump.
- **Signals on whether waiting costs value** — not just who is good, but whether delaying the decision is expensive.
- **Guidance shaped by your roster and live draft context** — recommendations are contextual, not generic.
- **Confidence-aware outputs** — when the inputs are not good enough, Draft Command withholds the recommendation rather than bluffing.

### The product surface

```text
PICK
Breece Hall

BACKUP 1
Saquon Barkley

BACKUP 2
Ashton Jeanty

WHY
Waiting costs more than acting.

CONFIDENCE
High
```

The interface is intentionally simpler than the machinery behind it.

---

## A predictive decision system, not a prediction system

Prediction asks:

> What will happen?

Decision intelligence asks:

> Given what may happen, what should I do now?

Draft Command is designed around the second question.

It treats a live draft as a **finite-horizon, sequential, partially observable, multi-agent decision environment**: other managers compete for scarce options, every action changes the shared state, and the next decision must be made under uncertainty and time pressure.

The football domain is the proving ground. The architecture is broader.

---

## The Decision Stack

Draft Command separates **truth, uncertainty, and judgment**.

| Layer | Question |
|---|---|
| **Ground truth** | What is actually true right now? |
| **Valuation** | What is this option worth in this environment? |
| **Market model** | What is likely to remain available? |
| **Opportunity cost** | What do I lose by waiting? |
| **Decision surface** | What should the human do now? |

**Deterministic code owns numerical truth.** Probabilistic simulation handles uncertainty. AI assists with engineering, critique, and explanation — it does not get to invent scoring, state, or arithmetic.

> The football-specific inputs change. The decision architecture does not.

---

## What makes it different

### Context-aware, not ranking-aware
A player is not evaluated in isolation. The recommendation reflects the live board, exact league rules, roster context, and available future decisions.

### Timing is part of value
Draft Command is built to answer a harder question than “who is ranked higher?” It considers the **cost of waiting**.

### Market-aware
The board is treated as a changing competitive market, not a static list.

### Human-in-the-loop
The system recommends. The human decides.

### Fail closed, not confidently wrong
If the inputs are stale, ambiguous, or incomplete, Draft Command can withhold the recommendation instead of producing false certainty.

---

## Proof of system behavior

The public showcase intentionally does **not** publish the private operational model, league database, weighting scheme, or strategic heuristics. It does publish evidence that the system behaves as intended.

| Evidence | Result |
|---|---:|
| Draft-room realizations exercised | **192** |
| Scenario regimes | **4** |
| Simulations per regime | **1,000** |
| Deepest keeper-adjusted decision exercised | **164** |
| Market-backed alternatives remaining at the final owned pick | **59** |
| Production tests | **75 / 75 passing** |
| Local decision computation | **sub-second** |
| Live decision clock | **60 seconds** |

The point is not benchmark theater. The point is whether the system can remain trustworthy and usable inside the actual decision window.

---

## Keeper-adjusted topology

Raw board position is not necessarily the real decision order in a keeper league.

Draft Command converts the raw draft board into the **actual open-player decision topology** before modeling availability. In the test environment, for example:

- raw **2.08** becomes open-pool decision **16**
- raw **3.07** becomes open-pool decision **28**

That distinction matters because availability is a function of how many **open selections** occur before the user acts, not the raw number printed on the draft board.

---

## AI-assisted engineering, deterministic proof

Draft Command was developed with an adversarial AI workflow:

**Build → independent audit → reproduce → regression test → accept or reject**

The operating rule is simple:

> **No model wins by sounding confident.**

An audit finding only changes the system if it can be reproduced against the real production path and survive deterministic testing.

That separation matters. AI can generate hypotheses quickly; reproducible evidence decides whether the system changes.

---

## Public showcase boundary

This repository is a **product and architecture showcase**, not the private competition system.

Published:

- product framing
- UX concepts
- architecture principles
- selected sanitized examples
- public-safe diagrams
- verification methodology

Not published:

- private league identifiers or exports
- personal messages or chat-derived signals
- the operational SQLite database
- exact weighting and tuning
- source-specific edge logic
- private heuristics
- live credentials or tokens

The goal is to show the **quality of the decision architecture** without publishing the competitive edge.

---

## Visual system

The default public theme is a **purple-and-gold “Northstar” palette** inspired by the creator’s Minnesota fandom, without using official team marks.

Brand color and semantic color are intentionally separate:

- **Purple / gold** = identity and emphasis
- **Green** = positive / ready / recommended
- **Amber** = warning / review
- **Red / coral** = blocked / stale / negative

This means a team theme can change without making “gold” accidentally mean “good” or “warning.”

The longer-term theme system can map the product chrome to a user’s preferred team while keeping semantic status colors consistent.

---

## Status

The private production system reached its first verified draft-ready checkpoint after:

- whole-draft rehearsal
- market provenance hardening
- adversarial audit and adjudication
- fresh live-state preflight
- watcher validation
- UI/API smoke testing
- full regression suite

The public repository is intentionally curated from that work rather than mirroring the private codebase.

---

## About the project

Draft Command started with a deceptively simple question:

> **Who should I draft?**

Answering it responsibly required a different question:

> **What decision should I make now, given the state of the system, the uncertainty in the market, the cost of waiting, and the evidence I can actually trust?**

That is the project.

---

### Disclaimer

Draft Command is an independent portfolio project and is not affiliated with or endorsed by Sleeper, the NFL, the Minnesota Vikings, or any NFL team. Team-color themes are aesthetic customization only. Player imagery should be sourced from a provider whose license permits the intended use; concept mockups should not be treated as official player photography.
