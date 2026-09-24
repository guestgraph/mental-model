---
source: Local
owner: Requestor
executed-by:
  - Requestor
gate-approvers:
  - Requestor
escalation-authority: Owner
gate-to: Understand
---

# Raise

> Say where it can be answered that GuestGraph would not do something the asker needed.

## What it takes

Whatever the Requestor was trying to do and could not, in whatever words they have for it.

## Activities

1. The Requestor opens an issue on the repository the request concerns.
2. The Requestor says what they were trying to do and where they stopped, in their own words.
3. The Requestor adds whatever makes that concrete, the system they wanted connected or the question the API could not answer, and nothing they were not asked for.

## What it produces

| Deliverable | Description |
| --- | --- |
| Request | A GitHub issue on the repository it concerns, saying what could not be done |

## What it never does

- Never has to be written in our terms; putting it in them is our work.
- Never has to name the hotel it asks for, or carry a guest's data.
- Never waits for a template, a label or a form; there is none, by design.

## Gate

To leave Raise, all of these hold:

- An issue exists, in the open, on the repository the request concerns.
- It says what the Requestor was trying to do and could not.

Where they cannot be met, the Owner helps state it rather than closing it; a request nobody could phrase is still a finding.
