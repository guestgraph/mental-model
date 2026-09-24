---
source: Local
---

# Tenants never meet

> One instance serves many brands, properties or customers, and nothing in one tenant is readable from another, from the first line of code on.

## In practice

Every stored row, query, uniqueness rule, lock and API operation carries its tenant, and resolution, lookup and merging happen within one tenant only. An id that belongs to another tenant is answered exactly as one that never existed, so a refusal cannot say whether an id is in use elsewhere, and the core has no administrative path that reads across tenants. Tenancy was there on the first day because it is cheap then and brutal to retrofit, and a leak between tenants in an identity graph is a privacy incident.

I never add a path, for an operator or for myself, that reads one tenant's guests from another's.
