---
id: 01a0ffcc-327f-7562-ac09-5df548965b62
source: Local
kind: detective
mode: automated
enforces:
  - The model is corrected first
---

# Pages drawn from the model are held to it

> A pull request to guestgraph.io fails where a page drawn from the model differs from what the model, at the commit the site pins, would draw.

## How it is carried out

The site's CI, on every pull request, in the `verify` job the ruleset requires: `model:check` parses this model at the commit `source.json` pins and fails where the committed `model.json` differs, and `pages:check` renders every region drawn from it and fails where the committed page differs, so a page edited by hand, or one the model no longer produces, cannot merge until the model is corrected and the page drawn again.

## Applies to

| Type | Entity | Owner |
| --- | --- | --- |
| phase | Integrate | Delivery |

## References

| What | URL |
| --- | --- |
| guestgraph.io's CI | https://github.com/guestgraph/guestgraph.github.io/blob/main/.github/workflows/ci.yml |
