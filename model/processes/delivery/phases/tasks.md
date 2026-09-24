---
source: Local
owner: Planner
executed-by:
  - Planner
  - Reviewer
gate-approvers:
  - Owner
escalation-authority: Owner
gate-to: Implement
---

# Tasks

> Break the plan into ordered tasks an implementer can take one at a time, and check that specification, plan and tasks agree.

## What it takes

An approved plan and the specification it serves.

## Activities

1. The Planner writes the tasks in the order they are to be done, with the test tasks ahead of the code they test wherever the resolution engine is touched.
2. The Reviewer reads the specification, the plan and the tasks against each other and reports every requirement no task covers and every task no requirement asks for.
3. The Planner corrects the tasks where the report found a gap.

## What it produces

| Deliverable | Description |
| --- | --- |
| Tasks | The ordered task list, covering every requirement of the specification and nothing beyond it |

## What it never does

- Never leaves a change to the resolution engine without a test task written before it.
- Never adds a task the specification does not ask for.

## Gate

To leave Tasks, all of these hold:

- Every functional requirement has a task, and every task a requirement.
- Resolution-engine work has its scenario tests as tasks ahead of its code.
- The Owner has approved the tasks.

Where they cannot be met, the Owner decides whether the plan or the specification goes back a phase.
