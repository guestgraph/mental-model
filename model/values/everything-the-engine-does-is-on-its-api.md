---
source: Local
---

# Everything the engine does is on its API

> Every capability of the engine is reachable through its versioned REST API, and every refusal carries a type a program can act on and a person can look up.

## In practice

Registering a source system, submitting a record, reading a guest, asking why, undoing a merge, deciding a review and setting the matching thresholds are all operations of the API, and a connector reaches the engine through that API like any other client. Every refusal is a problem detail whose type leads to a page saying what it means and what to do next. The hosted service will run this same engine, so the API is the product's contract from the first day.

I never build an engine capability that can only be reached through a job, an internal call or the database.
