---
source: Local
decided: 2026-09-10
kind: Architecture
status: Standing
by: Owner
---

# Each service owns one database schema and connects as a role that owns nothing else

> We put every service, the engine first, in a schema of its own inside the database and connect it as a role that owns that schema and is granted nothing else, and nothing in a service's migrations or queries names the schema, so whether two services share one database is a deployment's choice.

## The question

Where the engine's tables live once a second service, the connector, runs beside it, and what stops one service reading another's data when they share a database. It had to be decided in September 2026, before the first release, while the first migration could still be edited and no deployment had data that would need moving.

## Alternatives

| Option | Why not |
| --- | --- |
| The engine stays in the database's default schema | Any role that reaches the database reaches the engine's tables, and a second service in the same database shares a namespace with it. |
| A database of its own for every service | It decides for every deployment what only a deployment knows, and makes a small hotel run and back up two databases where one would do. |
| The schema written into every migration and query | The build would know its layout, and moving a service would mean editing every file it has. |

## Why

Owning the schema is the one privilege that makes the rest unnecessary: the owner may create and change what is inside it, and no other role reads it unless granted. Since PostgreSQL 15 an ordinary role cannot create in the default schema, so a role that owns its schema and nothing else cannot stray even by accident. One configuration value names the schema and sets both the connection's search path and where migrations run, so the same build runs in a shared database and in a dedicated one.

## Consequences

A deployment runs two statements per service, one creating the role and one the schema, and the connector's role cannot read a single guest; a check holds every service to the pattern. What it gave up is a database that was set up by starting the engine alone, and the local databases from before the move, which were dropped rather than migrated. It stays right for as long as no service is granted another's schema to save a call through its API.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| product | GuestGraph Engine | | changed it |
| product | Apaleo Connector | | changed it |

## References

| What | URL |
| --- | --- |
| The engine schema specification | https://github.com/guestgraph/engine/blob/main/specs/006-engine-schema/spec.md |
| The engine schema research, R1 and R2 | https://github.com/guestgraph/engine/blob/main/specs/006-engine-schema/research.md |
