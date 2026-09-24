---
source: Local
products:
  - GuestGraph Engine
concepts:
  - Match review
  - Matcher
  - Tenant
---

# Review an uncertain match

> A match the rules were not sure of waits for a person, with the reasons laid out signal by signal, and the person's answer stands.

## Description

A probabilistic candidate below the tenant's threshold, or a strong identifier shared by suspiciously many records, goes into the review queue instead of merging. A steward reads each review with the reasons it was held back, confirms or rejects it once, and the first decision stands. Each tenant sets its own thresholds and identifier rules. It stops at the decision: nothing is merged from the queue without one, and a decided review cannot be decided again.
