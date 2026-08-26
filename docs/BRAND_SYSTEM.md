# Brand System

## Brand idea

Draft Command should feel like a **premium live decision product**, not a fantasy-football website.

Reference qualities:

- control-room calm
- broadcast clarity
- sports intelligence
- technical credibility
- editorial restraint
- visible depth without visual clutter

Avoid:

- turf textures
- stadium clichés
- football icons everywhere
- ESPN imitation
- cyberpunk overload
- “AI glow” as the entire visual language
- sidebars full of destinations
- dashboard card soup

## Default theme: Northstar

The default showcase palette is Minnesota-inspired without using official team marks.

Suggested brand variables:

```css
--team-primary: #4F2683;
--team-primary-deep: #1B102B;
--team-secondary: #FFC62F;
--team-secondary-soft: #F2D37B;
--surface: #0B0912;
--surface-raised: #14101F;
--text: #F6F2EA;
--text-muted: #AAA3B6;
```

### Semantic colors

These do **not** change with team theme:

```css
--positive: #4FE0A1;
--warning: #F4B860;
--negative: #FF6B6B;
--info: #69B7FF;
--neutral: #8E889A;
```

This is critical. Gold can be a Minnesota-flavored brand accent without accidentally becoming “positive.”

## Team personalization

A future theme system should allow users to select a favorite sports team or a custom palette.

Only brand identity changes:

- primary chrome
- secondary accent
- subtle gradient
- background energy
- selection outline

Semantic meaning stays fixed:

- recommended / ready = green
- caution / review = amber
- blocked / stale = red
- informational = blue

Use colors, not protected marks, unless the implementation has rights to the relevant logos.

## Typography

Direction:

- wide condensed display face for product titles
- clean grotesk / sans-serif for UI
- monospaced accents only for machine-state details

Do not make the entire interface monospace. That quickly becomes “AI terminal” instead of premium product.

## Iconography

Simple geometric line icons.

Good:
- clock
- shield
- target
- branch
- queue
- source / provenance
- confidence state

Avoid:
- generic robot head
- sparkles everywhere
- neural-network brain icon as a default AI signifier

## Navigation

Do not recreate a traditional fantasy product information architecture.

Primary modes should be few and meaningful:

**Plan**  
Prepare the next decision.

**On Clock**  
Make the current decision.

**Queue**  
Act immediately after the draft or between decisions.

**Proof**  
Inspect why the system is trustworthy.

Pool, roster, board, freshness, and market context should appear *inside* those modes when relevant.

## Player imagery

Player headshots can materially improve scanning and visual continuity.

Publication rule:

- use a provider whose terms explicitly permit the intended display
- do not present AI-generated likenesses as official player photography
- if licensed photography is unavailable, use high-quality initials, team-neutral silhouettes, or abstract player tokens
- keep the image secondary to the player name and action

## League identity imagery

League avatars and manager profile images can improve continuity if sourced through the user’s authorized league data and if the platform’s terms permit display.

For a public portfolio case study, sanitize or replace personal league avatars unless every depicted person has consented.

## Product principle

**Complexity behind the glass. Clarity in front of it.**
