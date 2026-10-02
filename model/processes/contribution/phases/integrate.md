---
id: 01a0d360-9b98-7270-9bc1-054b5bc8c4cf
source: Local
owner: Owner
executed-by:
  - Owner
  - Surveyor
gate-approvers:
  - Owner
escalation-authority: Owner
---

# Integrate

> Take the change into the default branch, and carry it to whoever vendors or pins what it touched.

## What it takes

A change whose findings the Owner has ruled on, with every required check green.

## Activities

1. On the Owner's word the change is merged with a merge commit, never a squash, so the address the contributor committed under reaches the default branch unchanged.
2. Where the change touches what another repository vendors, a release is tagged on the Owner's word, with notes the Owner has read saying what a consumer must do.
3. The Owner moves every pin that names what moved, each in a commit that says why, or records it as deliberately behind.
4. The Owner deletes the branch, as their own step.

## What it produces

| Deliverable | Description |
| --- | --- |
| Merge commit | The change on the default branch, carrying the author it was given |
| Release | Where something vendored moved: a tag and notes saying what a consumer must do |

## What it never does

- Never leaves a pin behind a release without recording that it is deliberately behind.

## Gate

To leave Integrate, all of these hold:

- The default branch carries the change under the address its author committed with.
- Where something vendored moved, a release exists and its notes say what a consumer must do.
- Every pin that names the release has moved with it, or is recorded as deliberately behind.

## If not met

| Outcome | Leads to |
| --- | --- |
| reverted | |

The Owner reverts rather than leave the default branch in a state nobody chose.
