---
id: 01a0ffcc-0534-753c-aca7-166b1b2dfd38
source: Local
kind: preventive
mode: automated
enforces:
  - The Owner's word merges
---

# An agent's permissions refuse a merge it was not given

> The permission layer an agent runs under refuses a merge the agent attempts without the Owner's word for it in that conversation.

## How it is carried out

Claude Code's permission layer, before the agent's command runs: it judges the action against the conversation, and a merge without a review it can see is refused, so the agent stops and the merge waits for the Owner.

## Applies to

| Type | Entity | Owner |
| --- | --- | --- |
| role | Controller | |
| role | Implementer | |
| role | Surveyor | |
| phase | Integrate | Delivery |

## References

| What | URL |
| --- | --- |
| Claude Code permission modes | https://code.claude.com/docs/en/permission-modes |
