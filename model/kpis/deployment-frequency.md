---
source: Local
owner: Owner
measures: Delivery
unit: deployments per week
direction: higher
read-with:
  - Change Fail Rate
---

# Deployment Frequency

> How often a change reaches production.

## How it is measured

A deployment is a merge to `main` in a repository whose workflows publish one of this model's surfaces: the guestgraph.io website, which GitHub Pages publishes, and the mcp.guestgraph.io MCP server and the chat.guestgraph.io chat, which that repository's deploy and chat workflows publish. A merge counts once, however many of its workflows publish. The MCP Registry listing, republished when the MCP server's repository tags a release, is not a deployment. A release of the Apaleo Connector or of the shared conventions each service vendors into its build is not a deployment while nothing in production runs one.

The number of deployments in an ISO week, Monday midnight UTC to the next. Deployments and their times are read from the merges to `main` in the GitHub history of guestgraph/guestgraph.github.io and guestgraph/mcp-guestgraph-io; their publishing runs are GitHub Pages' own `pages-build-deployment` runs for the site and mcp-guestgraph-io's `deploy` and `chat` workflow runs on `main`. A workflow run that failed and published nothing is not a deployment.

## What it can hide

It rises when one change is split into several deployments and when something ships that did not need to; the first is the point and the second is noise. A rise bought with rushed changes shows in Change Fail Rate. A week without deployments reads the same whether nothing was ready or nothing was worth shipping.

## References

| What | URL |
| --- | --- |
| DORA's definition | https://dora.dev/guides/dora-metrics/ |
