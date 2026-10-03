---
id: 01a0ffcc-4180-7f62-b037-6f93c2ab8e4d
source: Local
kind: detective
mode: automated
enforces:
  - A change to the resolution engine merges only with its scenario tests
---

# The engine's scenario tests run on every pull request

> A pull request to the resolution engine cannot merge unless its scenario tests, run over the change as it stands, pass.

## How it is carried out

The engine's CI, on every pull request: the `verify` job runs `./mvnw -B verify`, which runs every test under `src/test`, among them the resolution scenario tests for transitive merges, chains of shared identifiers, a shared identifier parked for review, and an unmerge followed by a fresh record; the ruleset on the engine's default branch requires `verify` to pass on a branch up to date with main. It holds a change to the scenarios that are there; whether they were written before the change is read in review.

## Applies to

| Type | Entity | Owner |
| --- | --- | --- |
| phase | Integrate | Delivery |
| phase | Integrate | Contribution |

## References

| What | URL |
| --- | --- |
| The engine's CI | https://github.com/guestgraph/engine/blob/main/.github/workflows/verify.yml |
| The scenario tests | https://github.com/guestgraph/engine/tree/main/src/test/java/io/guestgraph/engine/resolution |
