---
source: Local
---

# Never drop what can be parsed

> Data loss is the cardinal sin: a record that can be read at all is kept, however wrong it looks.

## In practice

Hospitality systems are dirty by nature, so a malformed record that can still be parsed is stored and flagged for review rather than rejected, and only a request that cannot be parsed at all is refused, with a problem detail saying exactly what was wrong. A connector keeps a delivery it could not fetch or submit, with its reason and its next attempt, and retries it rather than dropping it. A flagged record can be repaired and resolved again; a discarded one is a guest interaction lost for good.

I never discard a parseable record because it does not look the way I expected.
