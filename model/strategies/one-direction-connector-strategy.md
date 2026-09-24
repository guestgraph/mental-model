---
source: Local
adopted: 2026-09-10
serves:
  - Every system a guest passes through feeds the graph
upholds:
  - Everything the engine does is on its API
  - Never drop what can be parsed
---

# One-Direction Connector Strategy

> Each source system gets a connector of its own, a separate service that reads that system and submits what it finds through the engine's API, so the engine calls nothing outward and runs with any number of connectors or none.

## The approach

A connector reaches one external system and is a client of the engine's REST API and nothing more: it submits one observation per person per version of a source object, keyed by the source's own clock so retries and full re-syncs are idempotent, and it holds the guest ids the engine answers. It owns a database schema of its own and connects as a role that sees nothing else, so whether it shares the engine's database is a deployment choice. The first connector is for a real PMS, Apaleo, because a PMS is what decides whether any of this is usable, and every rule a connector follows is decided in the engine's specification, with a change taken while building carried forward into the roadmap notes.

## What it rules out

No integration code inside the engine, and no engine call out to a hotel's systems. No connector reading the engine's tables, since its role cannot. And no connector that writes back into the system it reads.

## What would show it is working

A second connector, for a different kind of system, built against the same API without a change to the engine beyond what its specification asked for. A deployment running the engine alone, or several connectors against one engine, from the same builds. And the connector's status showing deliveries retried rather than lost when the engine or the source was down.
