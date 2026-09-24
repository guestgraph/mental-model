---
source: Local
---

# A match is not trusted until it is justified

> Finding a match is the easy part; knowing when not to trust one is the work, and a match that cannot justify itself is escalated rather than made.

## In practice

Each layer of matching decides only what it is entitled to and hands the rest upward: a shared strong identifier merges outright, a probabilistic score merges only above a threshold the tenant chose, and everything else queues for a person, whose decision sticks. Automatic probabilistic merging ships switched off, so out of the box a score suggests and a person decides, and lowering the threshold is an explicit, reversible act of trust. An agent gets no exemption a score would not get: it passes through the same thresholds, the same review queue and the same undo.

I never switch on a merge that no person asked to trust.
