---
source: Local
decided: 2026-09-10
kind: Architecture
status: Standing
by: Owner
upholds:
  - Everything the engine does is on its API
---

# Each source system gets its own one-direction connector

> A connector is a separate service that reads one external system and submits what it finds through the engine's API, so the engine calls nothing outward and runs with any number of connectors or none.

## The question

Where integration with a hotel's systems lives, inside the engine or beside it, and whether anything flows back. It had to be decided in September 2026, when the first connector was about to be built, because integration code inside the engine cannot be taken out once the engine depends on it.

## Alternatives

| Option | Why not |
| --- | --- |
| Integration code inside the engine | The engine would change with every system a hotel runs and would call out to systems it should never reach. |
| A bidirectional sync | Writing back into a hotel's PMS makes the graph a system of record it was never meant to be, and a wrong merge would then reach the desk through the hotel's own system. |

## Why

A connector is a client of the engine's REST API and nothing more: it submits one observation per person per version of a source object, keyed by the source's own clock so retries and full re-syncs are idempotent, and it holds the guest ids the engine answers. Everything the engine does is on its API, so a connector needs nothing else.

## Consequences

A connector owns a database schema of its own and connects as a role that sees nothing else; whether it shares the engine's database is a deployment choice; deliveries are retried rather than lost when either side is down. What it gave up is the shortcut of reading the engine's tables. It stays right for as long as a second connector, for a different kind of system, can be built against the same API without a change to the engine.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| strategy | One-Direction Connector Strategy | | made it |
| product | Apaleo Connector | | made it |
