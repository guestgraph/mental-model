---
source: Local
decided: 2026-07-09
kind: Architecture
status: Standing
by: Owner
---

# A record is resolved inside the request that submits it, one merge at a time per tenant

> We resolve every record before we answer its submission, and we serialize every change to a tenant's graph behind one lock per tenant, so the caller learns which guest its record belongs to in the same answer and concurrent submissions end where the same submissions one after another would have.

## The question

Whether resolution happens while the submitter waits or afterwards from a queue, and how two submissions that touch the same guests at once are kept from corrupting each other. It had to be decided with the ingest contract, in July 2026, because a submitter built against an answer that names the guest cannot be moved to one that names a job, and a locking scheme is built into every operation that changes the graph.

## Alternatives

| Option | Why not |
| --- | --- |
| Accept the record and resolve it later from a queue | The submitter would poll for a guest it could have been told, and a connector could not hold the guest id of what it just sent. |
| Lock the guests a record touches, row by row | A transitive merge touches a set of guests nobody knows in advance, and locks taken in varying order deadlock. |
| Serializable isolation with retries | A retry loop inside a synchronous submission makes its answer time unpredictable, and every caller would have to handle the retries it leaks. |
| A lock per identifier | A record with several identifiers needs several locks in a fixed order, which is more machinery for little more parallelism. |

## Why

A transaction-scoped PostgreSQL advisory lock keyed by the tenant is the simplest scheme that is correct under concurrency: every operation that creates, merges or unmerges a guest takes it first, the lock releases itself at commit or rollback, and tenants never wait for each other. Virtual threads make a blocking request cheap, so resolving inside it costs the submitter little, and one tenant's ingest volume fits in one serial section.

## Consequences

The answer to a submission names, per record, the guest and whether it was created, attached, merged or flagged; a batch is processed record by record inside the request and never fails as a whole; every later feature that changes the graph, unmerge and review decisions among them, runs under the same lock. What it gave up is parallel resolution within one tenant. It stays right for as long as a tenant's busiest hour fits through one serial section within the time a submitter will wait.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| feature | Submit a record from any system | | made it |
| feature | Resolve records into one guest | | made it |

## References

| What | URL |
| --- | --- |
| The engine's constitution, concurrency model | https://github.com/guestgraph/engine/blob/main/.specify/memory/constitution.md |
| The core resolution research, R3 and R11 | https://github.com/guestgraph/engine/blob/main/specs/001-core-identity-resolution/research.md |
