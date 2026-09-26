---
source: Local
decided: 2026-09-09
kind: Architecture
status: Standing
by: Owner
upholds:
  - Store what happened, derive who it was
---

# A retired guest id answers where the person is now, and never redirects

> We answer a read of a guest id that a merge absorbed or a split emptied with how it was retired and the guest or guests that hold the person now, worked out from the merge history rather than recorded apart from it, and we refuse the operations under that id with a pointer instead of carrying them out on the new guest.

## The question

What another system gets back when it reads a guest id it stored and a merge or split has since retired. It had to be decided in September 2026, before the first connector held guest ids, because a connector that gets a bare not found cannot tell a retired id from one that never existed and drops a reference that was still good.

## Alternatives

| Option | Why not |
| --- | --- |
| A bare not found, as before | A retired id and an unknown one would read the same, and the one failure a stored reference has would stay silent. |
| A redirect to the current guest | A split has no single target, and a client that follows redirects on its own reads the new guest without ever learning its stored id is stale. |
| A separate endpoint that resolves ids | The guest read would still answer not found to a client that did not know to ask elsewhere, which is the silent failure left in place. |
| Retirements recorded in a table of their own | A second copy of what the merge events already say, kept in step at two points, and every retirement before it would need a backfill computed by the walk it was meant to replace. |

## Why

Every retirement was already recorded once, in the merge event that absorbed the id or the unmerge that emptied it, in a table nothing may edit. Walking those events forward answers where the person went with nothing new to store and nothing to drift. One field on the read, whether the id is active, merged, split or retired, answers the only question a client has: can it replace the id it holds with one id.

## Consequences

A stored guest id is safe to keep, and the rule for integrators is one sentence: an id may be retired, and reading it tells you the current one. An operation under a retired id is refused as gone with the current ids, so nothing is done to a guest the caller did not name; a split names every current guest and never picks one. What it gave up is the convenience of a client that never checks. It stays right for as long as every merge and unmerge is recorded as an event nothing edits.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| concept | Retired guest id | | made it |
| feature | Keep a guest id you stored | | made it |

## References

| What | URL |
| --- | --- |
| The retired guest ids specification | https://github.com/guestgraph/engine/blob/main/specs/004-retired-guest-ids/spec.md |
| The retired guest ids research, R1 and R4 | https://github.com/guestgraph/engine/blob/main/specs/004-retired-guest-ids/research.md |
