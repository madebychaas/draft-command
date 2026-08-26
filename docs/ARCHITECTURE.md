# Public Architecture

This document describes Draft Command at the **contract level**. It intentionally omits the private numerical recipe.

## Core architecture

```text
LIVE STATE
  ↓
GROUND TRUTH
  ↓
VALUATION
  ↓
MARKET MODEL
  ↓
OPPORTUNITY COST
  ↓
DECISION SURFACE
  ↓
HUMAN ACTION
```

## Separation of responsibilities

### Deterministic layer
Owns facts and arithmetic that should not depend on model opinion.

Examples:

- identity
- league rules
- roster eligibility
- draft topology
- source timestamps
- persisted state
- numerical scoring contracts

### Probabilistic layer
Represents uncertainty that cannot be known exactly in advance.

Examples:

- market survival
- possible room evolution
- future availability
- scenario sensitivity

### AI-assisted layer
Used where language and broad reasoning are useful.

Examples:

- engineering assistance
- adversarial review
- explanation
- documentation

AI does **not** own numerical truth.

## Decision API contract

A public-facing decision can be thought of as:

```json
{
  "action": "PICK",
  "primary": "Player A",
  "backups": ["Player B", "Player C"],
  "why": "Waiting costs more than acting.",
  "confidence": "high",
  "status": "ready"
}
```

If evidence is insufficient:

```json
{
  "action": null,
  "status": "withheld",
  "reason": "Required inputs are not sufficiently fresh."
}
```

The private implementation that produces these outputs is intentionally not described here.

## Theme architecture

Team personalization should modify product identity without corrupting semantic meaning.

```css
--team-primary
--team-secondary

--status-positive
--status-warning
--status-negative
--status-neutral
```

A team’s gold, orange, red, or green should never automatically become the product’s “positive” or “warning” status color.

## Information architecture

The product should avoid a traditional sidebar full of redundant destinations.

Primary modes:

- **Plan** — what should I be preparing to do?
- **On Clock** — what should I do now?
- **Queue** — what should I add next?
- **Proof** — why should I trust the system?

Everything else should appear contextually inside those modes rather than becoming a permanent top-level page.
