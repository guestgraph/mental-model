---
source: Local
products:
  - GuestGraph Engine
concepts:
  - Source record
  - Source system
  - Tenant
---

# Submit a record from any system

> Whatever a hotel's system knows about a person can be handed to the graph as it is, and nothing it said is lost or changed.

## Description

A caller registers a source system once and then submits records through the API, each keyed by the system and a key the caller chose, so a second submission of the same key is recognized rather than stored twice. The record is kept exactly as sent beside what the engine extracted from it, and a record the engine could only partly understand is stored and flagged for review rather than refused. It stops at storing and resolving: it does not fetch anything from the system, which is a connector's work, and it never edits a record once stored.
