---
source: Local
products:
  - GuestGraph Engine
concepts:
  - Guest
  - Identifier
  - Merge
  - Matcher
---

# Resolve records into one guest

> Records of the same person from different systems end up on one guest, without anyone having to match them by hand.

## Description

A record that shares a normalized strong identifier with a guest, an email, a phone, a loyalty id, an ID document or an external key, joins that guest at full confidence, and merges carry transitively. Records sharing no identifier are found by name phonetics and scored on a weighted set of signals, and a score merges only above the threshold the tenant chose; below it, the candidate goes to review. It stops short of guessing: a record nobody could justify joining opens a guest of its own, and automatic probabilistic merging is off until a tenant turns it on.
