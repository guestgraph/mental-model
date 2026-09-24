---
source: Local
owner: Planner
executed-by:
  - Planner
gate-approvers:
  - Owner
escalation-authority: Owner
gate-to: Tasks
---

# Plan

> Decide how the slice will be built, and hold that design to the constitution before and after it is made.

## What it takes

An approved specification, the constitution and the code the slice lands in.

## Activities

1. The Planner runs the Constitution Check against the specification before any research.
2. The Planner writes the research, the data model and the API contracts the slice needs, each decision with the alternatives it rejected.
3. The Planner runs the Constitution Check again against the design.
4. Where the design needs more than the constitution's fixed shape, the Planner writes the excess into the plan's complexity tracking with the simpler alternative it rejected.

## What it produces

| Deliverable | Description |
| --- | --- |
| Plan | The implementation plan, with the research, the data model and the contracts beside it, passing the Constitution Check twice |

## What it never does

- Never plans a module, a service or a datastore beyond the fixed shape without saying in complexity tracking why the simpler option was rejected.
- Never plans a capability that is reachable other than through the API.
- Never changes the specification it plans; a gap goes back to the Owner.

## Gate

To leave Plan, all of these hold:

- The Constitution Check passes, before research and after design.
- Every exception to the fixed shape is in complexity tracking with its rejected alternative.
- The Owner has approved the plan.

Where they cannot be met, the Owner decides whether the design changes or the constitution is amended first.
