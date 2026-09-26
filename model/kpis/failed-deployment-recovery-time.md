---
source: Local
owner: Owner
measures: Delivery
unit: hours
direction: lower
read-with:
  - Change Fail Rate
---

# Failed Deployment Recovery Time

> The time it takes to recover from a deployment that fails and needs immediate intervention.

## How it is measured

A deployment is a merge to `main` in a repository whose workflows publish one of this model's surfaces: the guestgraph.io website, which GitHub Pages publishes, and the mcp.guestgraph.io MCP server and the chat.guestgraph.io chat, which that repository's deploy and chat workflows publish. A merge counts once, however many of its workflows publish. The MCP Registry listing, republished when the MCP server's repository tags a release, is not a deployment. A release of the Apaleo Connector or of the shared conventions each service vendors into its build is not a deployment while nothing in production runs one.

For each failed deployment, as Change Fail Rate counts them, the time from that deployment going live to the deployment that restores the surface going live, whether a revert, a fix or a re-pin to an earlier release. The value is the median over a calendar quarter in UTC. Deployments and their times are read from the merges to `main` in the GitHub history of guestgraph/guestgraph.github.io and guestgraph/mcp-guestgraph-io; their publishing runs are GitHub Pages' own `pages-build-deployment` runs for the site and mcp-guestgraph-io's `deploy` and `chat` workflow runs on `main`. A failure no deployment caused, a provider's outage, is not counted.

## What it can hide

It shortens when every failure is reverted rather than fixed, which restores the surface and leaves the change undone, so the change comes back as rework. Failures are rare here, so a quarter's median can rest on one or two events, and one slow recovery moves it a long way.

## References

| What | URL |
| --- | --- |
| DORA's definition | https://dora.dev/guides/dora-metrics/ |
