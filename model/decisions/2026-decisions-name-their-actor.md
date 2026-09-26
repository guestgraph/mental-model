---
source: Local
decided: 2026-08-21
kind: Architecture
status: Standing
by: Owner
serves:
  - An agent can decide a merge a hotel would accept
upholds:
  - Every merge can be explained and undone
---

# Every decision on the graph names who made it, and the credential says what kind

> We record on every merge, split, review decision and do-not-merge rule whether the system, a person or an agent made it, and who; the credential that made the call fixes whether it was a person or an agent, the request may only name which one, and automatic resolution is always the system.

## The question

Whether the audit trail says who decided, and whom to believe about it. It had to be decided in August 2026, before any agent acted as a steward, because the rule that an agent never overrides a person's split is a comparison between two recorded actors, and a decision recorded without one cannot be attributed afterwards.

## Alternatives

| Option | Why not |
| --- | --- |
| The actor as the request states it | A header would then authorize what it only describes, and any caller could record its decision as a person's. |
| The actor carried as ambient request state, as the tenant is | The resolution logic would read request scope it is otherwise free of, and under test it would fall back silently to someone it should not. |
| The actor recorded on a rule's creation only | Lifting a do-not-merge rule is overriding a split, the exact act the actor exists to gate, and a deleted rule would leave nowhere to say who lifted it. |

## Why

Binding the kind of actor to the credential puts the trust boundary where the key is: a key registered for an agent can never record a person's decision, and the request's header names the individual without authorizing anything. Passing the actor explicitly to the three operations that take a steward's decision makes it visible at every call, and the resolution logic takes no actor at all, so there is no path by which an automatic merge reads as a person's.

## Consequences

Explain, review decisions and do-not-merge rules show their actor; a rule is lifted with its lifter recorded rather than deleted, so the person's split and the agent's lift sit on one row; decisions from before the change read as unattributed rather than guessed. What it gave up is a hard delete of a rule. It stays right for as long as no path records a decision without the credential that made it.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| concept | Do-not-merge rule | | changed it |
| feature | Ask why records are one guest | | changed it |
| feature | Review an uncertain match | | changed it |

## References

| What | URL |
| --- | --- |
| The timeline and attributed decisions research, R4 and R8 | https://github.com/guestgraph/engine/blob/main/specs/003-timeline-journey/research.md |
