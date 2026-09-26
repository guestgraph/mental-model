---
source: Local
decided: 2026-07-09
kind: Architecture
status: Standing
by: Owner
---

# Every service is written in Java 25 and Spring Boot 4 on PostgreSQL

> We build the engine and every service beside it on one stack, Java 25 with virtual threads, Spring Boot 4, PostgreSQL and Maven, and a language, framework or datastore outside it enters only by amending the engine's constitution.

## The question

What the engine is written in and what it stores in, and whether each later service chooses its own. It had to be decided before the first line of code, in July 2026, because the persistence layer, the test harness and the guardrails a contributor meets are all built for one stack and are not moved to another.

## Alternatives

| Option | Why not |
| --- | --- |
| Python, for the matching libraries | The engine's work is ingest and lookup, waiting on the database and the network, and a matcher that needs Python can run beside it behind the matcher contract without moving the rest. |
| A graph database as the store | A graph store alone is a commodity, and what makes the graph worth having is resolution, which needs transactions, locks and constraints PostgreSQL already gives. |
| Each service choosing its own stack | Every stack is a second toolchain in CI, a second set of guardrails and a second harness, and the connector needs nothing the one stack does not give. |

## Why

The workload waits on I/O, and virtual threads make blocking code in a request cheap, so resolution can run inside the ingest request and stay simple. It is the stack the owner can maintain alone and the one enterprise Java contributors expect, and one stack means one set of shared rules every service takes at a pinned release. When the connector was built, an embedded database was weighed and PostgreSQL kept, because the engine's test harness carried over unchanged.

## Consequences

The connector and every later service start from the same parent build, checks and runtime code; a probabilistic matcher in another language may run as a sidecar behind the matcher contract, and nothing else leaves the stack without an amendment. What it gave up is the machine learning ecosystem inside the engine. It stays right for as long as a second stack, when one is needed, can be added beside the first as its own set of rules rather than replacing it.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| product | GuestGraph Engine | | made it |

## References

| What | URL |
| --- | --- |
| The engine's constitution, technology constraints | https://github.com/guestgraph/engine/blob/main/.specify/memory/constitution.md |
| The core design, fixed decisions | https://github.com/guestgraph/engine/blob/main/docs/superpowers/specs/2026-07-09-guestgraph-core-design.md |
| The Apaleo connector's research, R1 | https://github.com/guestgraph/engine/blob/main/specs/005-apaleo-connector/research.md |
| The service conventions' research, R9 | https://github.com/guestgraph/engine/blob/main/specs/007-service-conventions/research.md |
