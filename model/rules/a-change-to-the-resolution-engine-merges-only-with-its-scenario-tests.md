---
id: 01a0fd97-3bd6-7927-b759-6586861e448e
source: Local
modality: must
---

# A change to the resolution engine merges only with its scenario tests

> The scenario tests that hold a change to the resolution engine are written before it, and the change is merged only with them passing.

## Why

A wrong merge shows one guest another's stays and invoices, so the engine that decides merges is written test first, with scenario tests for shared family addresses, transitive merges and an unmerge followed by new records. A change that arrives without the scenarios that hold it, from us or from a contributor, asks the engine to be trusted on less than it was built to show.

## Applies to

| Type | Entity | Owner |
| --- | --- | --- |
| process | Delivery | |
| process | Contribution | |
