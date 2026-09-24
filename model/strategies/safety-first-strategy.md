---
source: Local
adopted: 2026-07-09
serves:
  - An agent can decide a merge a hotel would accept
upholds:
  - Every merge can be explained and undone
  - A match is not trusted until it is justified
---

# Safety-First Strategy

> The machinery that makes a merge safe to allow, explanation, undo, the review queue and the confidence behind each decision, is built before anything uncertain is allowed to merge, and every new kind of matcher is admitted through it.

## The approach

Every merge is recorded with its matcher, its confidence and its evidence, can be asked why and undone, and a suspicious match queues for review under a threshold each tenant sets, and all of that existed while matching was still deterministic. A new matcher is a new implementation of the same contract, candidates in and scored decisions out, and the probabilistic one was admitted switched off, with a split holding against new evidence through a do-not-merge rule. An agent is treated as one more uncertain matcher behind that contract, and the audit trail records who decided before any agent decides anything. The resolution engine is written test first, with scenario tests for shared family addresses, transitive merges and an unmerge followed by new records.

## What it rules out

No matcher that merges before it can be explained and undone, however accurate it looks. No automatic probabilistic merging out of the box. No agent path around the review queue or the thresholds, and no special trust for a model because it is a model. And no retrofitting: a safeguard added after the decisions it guards have been made cannot reach the ones made before it.

## What would show it is working

A wrong merge found in testing or in use that was undone completely, with the split holding against the records that arrived after it. Review decisions accumulating with the feature vector each was scored on, which is the labeled data a later matcher would be trained on. And a hotel shown the explanation of a merge and able to tell, from that alone, whether it was right.
