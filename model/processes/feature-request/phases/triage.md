---
source: Local
owner: Owner
executed-by:
  - Owner
gate-approvers:
  - Owner
escalation-authority: Owner
gate-to: Answer
---

# Triage

> Decide what kind of thing the gap is, and whether it is ours to fill.

## What it takes

A restated request naming what could not be done.

## Activities

1. The Owner decides which of four the gap is: a capability of the engine, a connector for a system not yet reached, something of the planned commercial layer, or no gap at all.
2. The Owner checks whether the engine already does it under another name, because a request for what exists is a finding about how it is documented.
3. The Owner weighs it against the constitution and the strategies: a capability reachable only outside the API, or one that would merge on less than the layers allow, is refused whoever asks.
4. Where the gap is real, the Owner writes it into the roadmap notes, where the next slice's specification will read it.
5. The Owner writes the classification and its reason in the issue.

## What it produces

| Deliverable | Description |
| --- | --- |
| Classification | Which of the four the gap is, with the reason, written in the issue |
| Roadmap note | Where the gap is real: the requirement as the next slice's specification will read it |

## What it never does

- Never leaves the reason out because the classification seems obvious.
- Never admits a request that breaks a principle of the constitution because it was asked for.
- Never opens a specification; what happens next is Delivery's, and it starts from the roadmap notes.

## Gate

To leave Triage, all of these hold:

- The gap is classified as an engine capability, a connector, the commercial layer or no gap.
- The reason is written where the request was made.
- Where the gap is real, the roadmap notes carry it.

Where they cannot be met, the Owner leaves the request open and says what would settle it, rather than classifying it to be finished with it.
