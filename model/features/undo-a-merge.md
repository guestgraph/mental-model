---
source: Local
products:
  - GuestGraph Engine
concepts:
  - Merge
  - Do-not-merge rule
  - Guest
---

# Undo a merge

> When the graph put two people together, a person can split them again, and the split holds against whatever arrives later.

## Description

An unmerge detaches the named records from a guest and resolves them again, and it writes a do-not-merge rule so that new evidence cannot silently put them back together. The rules can be listed and lifted through the API when a split was itself a mistake, and lifting one is recorded with who did it. It does not repair a record: the records are unchanged, and only which guest they belong to moves.
