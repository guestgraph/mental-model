---
source: Local
decided: 2026-07-09
kind: Business
status: Standing
by: Owner
upholds:
  - The core stays open
---

# Open core under Apache 2.0, with paid hosting later

> Everything that resolves a guest, the engine, the graph, the API and the connectors, is open source under Apache 2.0 for anyone to run, and what could ever be paid for is running it: managed hosting, a console and MCP access for agents.

## The question

What is open and what could be sold, and whether the license on the core can ever change. It had to be decided before the first public commit, in July 2026, because a license that closes later is read as one that will.

## Alternatives

| Option | Why not |
| --- | --- |
| A closed SaaS | A hotel could not read how a merge was decided before trusting one, and the people arguing with the engine in the open, who are the first signal the idea is right, would not exist. |
| A source-available license | It says open and means later, and integrators who would run the engine themselves would not build on a license that can close. |

## Why

A hotel or an integrator can read exactly how a merge was decided before trusting one, and can run it without us. The commercial layer is planned on top of the core and never inside it, so the hosted service runs the same engine anyone can run, and the pages can say plainly that there is no product for sale yet and ask where the idea is wrong.

## Consequences

No proprietary edition, no capability held back to make hosting worth buying, authentication beyond per-tenant API keys belongs to the commercial layer, and no license change on the core later. What has to stay true is that the core does not depend on commercial code.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| strategy | Open Core Strategy | | made it |
| product | GuestGraph Engine | | changed it |
