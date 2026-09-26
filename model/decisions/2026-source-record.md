---
source: Local
decided: 2026-07-09
kind: Architecture
status: Standing
by: Owner
upholds:
  - Store what happened, derive who it was
---

# A source record is never edited, and the guest is derived from it

> A record enters exactly as its system sent it and is never changed or deleted by application code; a guest is a conclusion recomputed from the records, not a row anyone edits.

## The question

What the engine stores and what it computes, and whether a correction changes what was stored. It had to be decided before the first table existed, in July 2026, because a store that edits records in place cannot be turned into one that does not without losing what it already overwrote.

## Alternatives

| Option | Why not |
| --- | --- |
| A master record edited in place | Every correction would overwrite what a system actually sent, and no merge could be explained or undone from what was left. |
| A golden record kept as a CRM keeps one | A row someone edits is a claim nobody can recompute, and the survivorship that produced it is lost the moment it is saved. |

## Why

An explanation, an undo and a replay of resolution are possible only from records kept as they arrived. If the golden profile is computed from the records by survivorship rules, it can be recomputed at any time, which is what makes a wrong merge reversible and a right one explainable.

## Consequences

A correction arrives as a new record; the profile is derived and can be recomputed; lawful erasure under data protection law is the one exception and is named as one. What it gave up is the cheap fix: nobody can edit a profile to make it right. It stays right for as long as no code path writes to a record after it entered.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| concept | Source record | | made it |
| concept | Golden profile | | made it |
