---
source: Local
production: built
built-by: https://github.com/guestgraph/mcp-guestgraph-io
url: https://chat.guestgraph.io
---

# chat.guestgraph.io chat

> The chat a visitor opens on guestgraph.io to ask about what we know, answered from what the mcp.guestgraph.io MCP server says at its pinned commit, and the page a person reaches at the same address.

## What it shows

- **Endpoint** — `/chat` on this address, which a page of guestgraph.io posts a visitor's conversation to and which answers it as a stream of events.
- **Answer** — the text a language model writes from what the MCP server's tools returned for the visitor's question, in the language of the visitor's message, naming the entity each claim rests on.
- **From the model** — a link to each entity a tool returned on its own, opening its file at the commit it was read from.
- **Refusals** — the sentences a visitor reads instead of an answer when the day's or the month's share is spent, when one address has sent too many messages in an hour, when the host does not answer or when the chat is switched off.
- **Page** — what a browser gets at the chat's own address: the host's name, the vision's and the identity's taglines, the paths and the events the endpoint answers, the fence that bounds what it spends, and the commit of the model it answers from.

## Constraints

- The chat answers about GuestGraph and never about a hotel's guests; no guest's data is in the model it reads.
