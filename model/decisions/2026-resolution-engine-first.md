---
source: Local
decided: 2026-07-09
kind: Product
status: Standing
by: Owner
---

# The product is an engine that resolves guests, and the graph is what it emits

> What we build first and at the center is identity resolution: an engine that decides which records from a hotel's systems are one person, and emits the guest graph as the result of those decisions rather than offering a place to store one.

## The question

What GuestGraph is at its core, before anything else is built on it: a store for guest data shaped as a graph, a view of a guest's stays across systems, or the engine that works out which records are one guest. It had to be decided before the first specification, in July 2026, because everything later, the matchers, the timeline and the connectors, is built on whichever of them comes first.

## Alternatives

| Option | Why not |
| --- | --- |
| A graph store for guest data | A graph store alone is a commodity, and a hotel that loads its records into one still does not know which of them are the same person. |
| The guest's journey across systems first | A timeline is only as right as the resolution under it: until records are known to be one guest, a journey either splits one person or joins two. |

## Why

Deciding which records are one person is the hard problem and the defensible one: hospitality data arrives from many systems with different keys and dirty values, and the answer has to be explainable and reversible to be trusted. The graph and the timeline follow from resolution once it is right, and neither can be right without it.

## Consequences

The engine is where the effort goes, and the matchers, the review queue and the explanation of each merge are the product rather than features around it; the timeline came as a later slice on resolved guests; the store is PostgreSQL, not a graph database. What it gave up is a product a hotel could use on the first day without resolution. It stays right for as long as knowing which records are one guest is what a hotel cannot get elsewhere.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| product | GuestGraph Engine | | made it |

## References

| What | URL |
| --- | --- |
| The core design, vision and fixed decisions | https://github.com/guestgraph/engine/blob/main/docs/superpowers/specs/2026-07-09-guestgraph-core-design.md |
