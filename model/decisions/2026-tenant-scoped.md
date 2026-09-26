---
source: Local
decided: 2026-07-09
kind: Architecture
status: Standing
by: Owner
upholds:
  - Tenants never meet
---

# Every row, query and lock carries its tenant from the first line of code

> We run one engine for many tenants, a hotel, a brand or a property, and put the wall between them in the data itself: every stored row, query, uniqueness rule, lock and API operation carries its tenant.

## The question

Whether one running engine serves many hotels or each hotel gets its own, and if many, where the wall between them stands. It had to be decided before the first table existed, in July 2026, because a column added to every table and a parameter added to every query after the fact is a rewrite of everything written before it.

## Alternatives

| Option | Why not |
| --- | --- |
| One deployment per hotel, tenancy added later | Process isolation stands in for data isolation until the hosted service needs many hotels in one engine, and then every table, query and lock is retrofitted at once. |
| A database or schema per tenant | The wall moves out of the code into provisioning, a hotel group's brands cannot share one engine without one schema each, and the hosted service would run different code from the one anyone can run. |

## Why

Tenancy is cheap on the first day and brutal to retrofit, and a leak between tenants in an identity graph shows one hotel's guests to another. Carried in the data, the rule can be checked mechanically: a repository method without its tenant fails the build, and an id from another tenant is answered exactly as one that never existed. When the connector's first draft served one hotel per process, it was held to the same rule before it was built, with a connection in the tenant's place.

## Consequences

Merges are serialized per tenant, so tenants never wait for each other; a service beside the engine that serves many hotels scopes its rows the same way; the hosted service runs the same code as a self-hosted engine; a hotel group chooses whether a brand or a property is a tenant. What it gave up is the simplicity of a query that forgets whose data it reads. It stays right for as long as no code path, for an operator or for ourselves, reads across tenants.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| concept | Tenant | | made it |
| product | GuestGraph Engine | | made it |

## References

| What | URL |
| --- | --- |
| The engine's constitution, principle I | https://github.com/guestgraph/engine/blob/main/.specify/memory/constitution.md |
| The core design, fixed decisions | https://github.com/guestgraph/engine/blob/main/docs/superpowers/specs/2026-07-09-guestgraph-core-design.md |
| The Apaleo connector's research, R12 | https://github.com/guestgraph/engine/blob/main/specs/005-apaleo-connector/research.md |
