---
id: 01a13d68-db37-70a7-a505-5713fdca4f22
source: Local
kind: detective
mode: manual
enforces:
  - A feature request carries no guest's data
performed-by: Owner
---

# A guest's data in a request is taken out of it

> The Owner reads every feature request for a guest's data before restating it, and takes out any it finds, from the issue and from its edit history.

## How it is carried out

The Owner, in Understand, on every feature request: before restating it, it reads the request and every comment on it for a guest's data, a name, an address, a booking or anything else that points at a guest; where it finds any, it edits it out, deletes the content of that edit from the issue's edit history, which leaves only who edited and when, and asks for the gap again without it. It never asks for a guest's data to illustrate a request. An issue is public from the moment it is opened, so what was read before the Owner took it out stays read; the control shortens that time and cannot undo it.

## Applies to

| Type | Entity | Owner |
| --- | --- | --- |
| phase | Understand | Feature request |

## References

| What | URL |
| --- | --- |
| GitHub's edit history and how to delete from it | https://docs.github.com/en/communities/moderating-comments-and-conversations/tracking-changes-in-a-comment |
