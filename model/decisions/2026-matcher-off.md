---
source: Local
decided: 2026-07-09
kind: Architecture
status: Standing
by: Owner
upholds:
  - Every merge can be explained and undone
  - A match is not trusted until it is justified
---

# The probabilistic matcher ships switched off

> The machinery that makes a merge safe to allow, explanation, undo, the review queue and a confidence behind each decision, is built first, and the probabilistic matcher is admitted through it switched off, for a tenant to turn on under its own threshold.

## The question

Whether uncertain matching is allowed to merge before a hotel can see why and undo it, and in what order the safety machinery and the matchers are built. It had to be decided in July 2026, before any matcher beyond the deterministic one existed, because a safeguard added after the decisions it guards cannot reach the ones made before it.

## Alternatives

| Option | Why not |
| --- | --- |
| On by default under a threshold | A hotel would get merges it never chose to allow before it had seen one explained, and a wrong merge shows one guest another's stays and invoices. |
| No probabilistic matcher at all | Deterministic matching alone leaves the returning guest with a typo in the email as a stranger, and the review decisions that would train a better matcher would never accumulate. |

## Why

Every merge is recorded with its matcher, its confidence and its evidence, can be asked why and undone, and a suspicious match queues for review under a threshold each tenant sets, and all of that existed while matching was still deterministic. A new matcher is then one more implementation of the same contract, candidates in and scored decisions out, and an agent is treated as one more uncertain matcher behind it.

## Consequences

No matcher merges before it can be explained and undone; no agent path around the review queue; a split holds against new evidence through a do-not-merge rule; the review decisions accumulate with the feature vector each was scored on. What it gave up is a higher merge rate out of the box. It stays right for as long as a wrong merge is rarer than a missed one.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| concept | Matcher | | changed it |
| strategy | Safety-First Strategy | | made it |
| feature | Review an uncertain match | | made it |
