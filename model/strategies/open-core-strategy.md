---
source: Local
adopted: 2026-07-09
serves:
  - Whether a hotel would pay to know its guests is answered
upholds:
  - The core stays open
---

# Open Core Strategy

> The engine, the graph, the API and the connectors are open source for anyone to run, and what could ever be paid for is running them: managed hosting, a console and MCP access for agents.

## The approach

Everything that resolves a guest is in public repositories under Apache 2.0, built spec-first in the open, so a hotel or an integrator can read exactly how a merge was decided before trusting one, and can run it without me. The commercial layer is planned on top of the core and never inside it: the core does not depend on commercial code, authentication beyond per-tenant API keys belongs to that layer, and the hosted service will run the same engine anyone can run. The talks and the pages say plainly that there is no product for sale yet and ask where the idea is wrong.

## What it rules out

No proprietary edition of the engine and no capability held back to make the hosted service worth buying. No closed matching model whose decisions a hotel cannot inspect. And no license change on the core later, which is why the pages say it will remain open rather than only that it is open.

## What would show it is working

People outside the project reading the engine and arguing with how it decides, in issues, pull requests or replies to the talk, which says the openness is being used rather than merely offered. Integrators running the engine themselves against their own systems. And, later, a hotel choosing the hosted service over running the same code itself, which is the one signal that the commercial half has a reason to exist.
