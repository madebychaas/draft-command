# Draft Command — Case Study

## The problem

Fantasy draft tools usually optimize for information density: rankings, projections, ADP, news, tiers, and chat. But a live draft is not primarily an information-retrieval problem.

It is a **decision problem**.

At any moment, the user needs to know:

1. What changed?
2. What is actually available?
3. What is each option worth in this exact environment?
4. What is likely to disappear before I act again?
5. What do I lose by waiting?
6. What should I do now?

Draft Command was built around that sequence.

## Product thesis

**Complexity behind the glass. Clarity in front of it.**

The user should not have to operate the model. The system should compress the model into a decision surface:

- PICK
- BACKUP 1
- BACKUP 2
- WHY
- CONFIDENCE

Everything deeper should be inspectable, but nothing deeper should compete with the action.

## Why “Real-Time Adversarial Decision Intelligence”

The phrase is intentionally descriptive rather than ornamental.

**Real-time**  
The board changes continuously and the decision clock is finite.

**Adversarial**  
Independent actors compete for scarce options and each action changes the state available to everyone else. “Adversarial” is used in the game-theoretic sense, not the cybersecurity sense.

**Decision intelligence**  
The system combines state, rules, valuation, probabilistic market behavior, opportunity cost, and human judgment to improve an action — not merely to predict an outcome.

## The formal problem

Draft Command can be described as a human-in-the-loop decision-support system for **finite-horizon sequential decision-making under uncertainty in a partially observable multi-agent environment**.

It is:

- finite-horizon
- sequential
- partially observable
- multi-agent
- stochastic
- constrained
- human-in-the-loop

The domain is fantasy football. The systems pattern is more general.

## The Decision Stack

### 1. Ground truth
Establish the current state and the rules that define the environment.

### 2. Valuation
Translate options into environment-specific value.

### 3. Market model
Estimate which options are likely to survive until future opportunities.

### 4. Opportunity cost
Measure what may be lost by delaying action.

### 5. Decision surface
Return a concise human-facing recommendation.

The implementation details below those layers remain private.

## Trust architecture

The public design principle is:

> **Fail closed, not confidently wrong.**

A trusted recommendation should depend on trusted inputs. If a required input becomes stale or incomplete, the product should say so.

That is a UX decision as much as an engineering decision. Confidence is not a visual treatment; it is a contract.

## Adversarial AI development

AI was used in multiple roles rather than as a single unquestioned builder.

The high-level workflow:

1. Build with AI assistance.
2. Have an independent model attack assumptions.
3. Reproduce the finding against the actual system path.
4. Create deterministic regression evidence when warranted.
5. Accept or reject the finding.

This intentionally separates **hypothesis generation** from **proof**.

## What the user gets

The system ultimately compresses all of that into:

- one current recommendation
- immediate alternatives
- concise reasoning
- a cost-of-waiting signal
- roster and market context
- confidence constrained by evidence quality

That compression is the product.

## What is intentionally not public

This case study does not publish the exact numerical recipe.

The following remain private:

- private data and identifiers
- source-specific competitive edge
- weight tuning
- exact heuristics
- production database
- operational automation
- proprietary strategy logic

The portfolio value is the architecture, methodology, reliability discipline, and UX — not disclosure of the competitive model.
