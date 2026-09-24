---
source: Local
owner: Specifier
executed-by:
  - Specifier
gate-approvers:
  - Owner
escalation-authority: Owner
gate-to: Plan
---

# Specify

> Write what the slice must do and why, completely enough that the plan does not have to guess.

## What it takes

The requirements the roadmap notes have captured for this slice, the constitution the slice must not contradict, and the specifications and reference documents already merged, read rather than remembered.

## Activities

1. The Specifier opens the slice's numbered branch and reads the roadmap notes and the documents the slice touches.
2. The Specifier writes the specification: the user stories, the functional requirements and what is explicitly not in the slice.
3. The Specifier puts every open question to the Owner and records the answers in the specification rather than assuming one.

## What it produces

| Deliverable | Description |
| --- | --- |
| Specification | The slice's requirements under the engine's specs, with its open questions answered and what is not in the slice named |

## What it never does

- Never writes the plan or the code it specifies.
- Never decides a question that is the Owner's; it asks and records the answer.
- Never edits a specification an earlier slice merged.

## Gate

To leave Specify, all of these hold:

- The Owner has read the specification and approved it.
- No question in it is left open.

Where they cannot be met, the Owner decides whether the slice is narrowed, split or deferred to the roadmap notes.
