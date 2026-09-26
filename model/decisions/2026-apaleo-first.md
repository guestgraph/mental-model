---
source: Local
decided: 2026-09-10
kind: Product
status: Standing
by: Owner
---

# Apaleo is the first connector

> The first source system connected to the graph is a real property management system, Apaleo, and the connector is built against its API rather than against a PMS in general.

## The question

Which system to connect first, and whether the first connector is for one system or for a class of them. It had to be decided in September 2026, when the engine could resolve records and had none to resolve.

## Alternatives

| Option | Why not |
| --- | --- |
| A generic PMS adapter | An adapter for every PMS fits none, and the rules a connector follows would be guessed instead of read from one real API. |
| A booking engine or the wifi first | A PMS is where the reservation and the check-in live, which is what decides whether any of this is usable for a hotel at all. |

## Why

A PMS is what decides whether any of this is usable, and Apaleo is a PMS with a public API that a connector can be built and tested against without a hotel's help. Every rule a connector follows is then decided in the engine's specification against something real, and a change taken while building is carried forward into the roadmap notes.

## Consequences

The connector's rules are decided once against a real API; the second connector, for a different kind of system, is what proves the API rather than the first. What it gave up is breadth on the first day. It stays right for as long as hotels that keep their stays in Apaleo are the ones asking.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| product | Apaleo Connector | | made it |
| feature | Bring reservations and bookings into the graph | | made it |
