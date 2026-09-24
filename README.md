# GuestGraph — Mental Model

> GuestGraph described in the vocabulary CompanyGraph publishes: the project behind the open-source guest identity graph, as an instance of the meta-model.

[CompanyGraph](https://github.com/companygraph/meta-model) publishes a vocabulary for describing a company as a graph of Markdown files. The two instances before this one describe a company of one and the project behind the vocabulary itself, and what each ships is about modeling. This one describes a company whose product is about something else entirely, guest identity in hospitality, so it asks whether the vocabulary holds a product's own words, its domains and concepts, and a delivery process that is not the vocabulary's own. It was made by the meta-model's `init` rather than laid out by hand.

```text
.companygraph/manifest.json    which units this vendors, and a hash per vendored file
meta/core/                     core at the release .companygraph/manifest.json names, copied whole and never edited here
conventions/                   the family's shared conventions, vendored at the release conventions.json names
model/                         the company — everything under here is an entity, nothing else is
  identity.md                  who the company is, and where it can be found
  vision.md                    the future it works toward
  sources/                     where each page's facts are mastered
  values/                      what it will and will not do
  strategic-objectives/        what must become true for the vision to be reached
  strategies/                  how one gets reached, and what the route rules out
  surfaces/                    one file per place the model is published
  roles/                       the seats its work is done from, each naming no holder
  profiles/ai-agent/           the agent, and the seats it holds
  processes/                   each kind of work it does, phase by phase
  products/                    what it ships
  features/                    what each product lets someone do
  domains/                     the areas its vocabulary falls into
  concepts/                    the words it means something exact by, and how they hang together
AGENTS.md                      this instance's own rules; every modeling rule is in meta/core/CONVENTIONS.md
```

**No person is described here.** GuestGraph is built by the company of one the [reference instance](https://github.com/robertblust/mental-model) describes, and that is where the person is. The one profile this repository carries is an agent's; a `role` is a seat and names no holder, and a seat no profile names is held by a person.

**guestgraph.io is a surface, and so are the MCP server and the chat.** guestgraph.io, built by `guestgraph/guestgraph.github.io`, draws its Model, Team, Principles and Surfaces pages from a pinned commit of this repository. The MCP server at mcp.guestgraph.io, its MCP Registry listing and the chat at chat.guestgraph.io are built from it by `guestgraph/mcp-guestgraph-io`.

The content is mastered here — `source: Local`, corrected in this repository and nowhere else — and what it says is drawn from prose that is already published: the organization profile on GitHub, the pages and the introduction talk of guestgraph.io, the READMEs of the engine and the connector, and the engine's constitution and reference documents. Nothing is invented, and a claim that cannot be traced to one of those does not go in.

## License

[CC BY 4.0](LICENSE) for everything written here — the model and the documentation beside it. Use it, quote it, build on it; credit it. The prose is the artifact, which is why this is a content license rather than a code license.

`meta/core/` is not written here: it is CompanyGraph core, vendored at the release `.companygraph/manifest.json` names, and stays under its own [Apache 2.0](meta/core/LICENSE). `conventions/` is vendored the same way, from robertblust/conventions at the release `conventions.json` names, and is edited there.
