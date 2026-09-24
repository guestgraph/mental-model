---
source: Local
production: built
built-by: https://github.com/guestgraph/guestgraph.github.io
url: https://guestgraph.io
---

# guestgraph.io website

> The project's own site, in English and Swiss Standard German, where a hotel, an integrator, a search engine or an agent meets the guest identity graph and the project that builds it, with the pages drawn from our model rebuilt from a pinned commit of it.

## What it shows

- **Landing** — the problem in one line, five strangers and one guest, with the way into the introduction talk and the code.
- **Team** — each process's phases as a board of the roles that own, execute, support and approve each, and the profiles that hold those roles, drawn from `model.json`.
- **Principles** — the vision and the values, drawn from `model.json`.
- **Surfaces** — every surface the model records, with how each is made and what makes it, and nothing kept beside the model, drawn from `model.json`.
- **API** — the engine's and the connector's operations, generated from their OpenAPI documents at the commits the site pins.
- **Model** — this model, drawn as a graph from `model.json`, with each entity's card.
- **Talks** — the introduction talk, narrated in both languages with a PDF, and the questions it ends on.
- **Billing** — the one meter the hosted service would bill on, what is free and stays so, and the ways to charge that were refused and why.
- **Privacy** — what leaves a visitor's browser and what stays in it, listed in full, and how the hosted service will treat guest data.
- **Problems** — what each refusal type a GuestGraph service answers means, and what to do about it.
- **model.json** — this model parsed at the commit the site pins, published as a dataset.
- **Chat** — the button at the foot of every prose page and the panel it opens, answered by the chat.guestgraph.io chat.
- **Structured data** — the organization, the website and the dataset each page describes to a crawler.

## Constraints

- The site collects nothing: no page sets a cookie, no page loads an analytics script, and nothing counts a visit; the one request a page makes to another address is the chat's, and only after the visitor has pressed send.
- Every page drawn from the model names the repository and the commit it was parsed from, on the page.
- A page drawn from the model is rebuilt from `model.json`, and the build fails when that file is not what the pinned commit parses to.
- Both languages carry the same claims: a page's German is a translation of its reviewed English, never a second text.
