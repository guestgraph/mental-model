---
source: Local
owner: Owner
measures: Delivery
unit: hours
direction: lower
read-with:
  - Change Fail Rate
---

# Change Lead Time

> The time a change takes from being committed to version control to running in production.

## How it is measured

A deployment is a merge to `main` in a repository whose workflows publish one of this model's surfaces: the guestgraph.io website, which GitHub Pages publishes, and the mcp.guestgraph.io MCP server and the chat.guestgraph.io chat, which that repository's deploy and chat workflows publish. A merge counts once, however many of its workflows publish. The MCP Registry listing, republished when the MCP server's repository tags a release, is not a deployment. A release of the Apaleo Connector or of the shared conventions each service vendors into its build is not a deployment while nothing in production runs one.

For each deployment, the time from the earliest commit it carries that no earlier deployment carried to the moment it is live; a change to the model counts from its commit in guestgraph/mental-model to the deployment of the re-pin that carries it. The value is the median over the deployments of a calendar month in UTC, read from the merges to `main` and their times in the GitHub history of guestgraph/guestgraph.github.io and guestgraph/mcp-guestgraph-io, and from their publishing runs on `main` — GitHub Pages' own `pages-build-deployment` for the site, and mcp-guestgraph-io's `deploy` and `chat` workflow runs.

## What it can hide

It shortens when changes get smaller and when review gets thinner, and only the first is progress. Thinner review shows as a higher Change Fail Rate, which is why the two are read together. A median also hides the change that waited a week behind a re-pin.

## References

| What | URL |
| --- | --- |
| DORA's definition | https://dora.dev/guides/dora-metrics/ |
