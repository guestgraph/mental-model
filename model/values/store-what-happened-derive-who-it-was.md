---
source: Local
---

# Store what happened, derive who it was

> A source record is kept exactly as its system sent it, and a guest is a conclusion drawn from those records rather than a row anyone edits.

## In practice

A record enters as it arrived, its raw payload beside the fields extracted from it, and application code never changes or deletes it; a correction arrives as a new record. The golden profile is computed from the records by survivorship rules and can be recomputed at any time, which is what makes an explanation, an undo and a replay of resolution possible at all. Lawful erasure under data protection law is the one exception, and it is named as one.

I never overwrite a source record to fix what a guest's profile says.
