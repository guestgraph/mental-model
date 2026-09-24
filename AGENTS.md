<!-- conventions · v1.32.0 -->
Shared conventions of the robertblust, guestgraph and companygraph organizations live in `conventions/`, vendored from robertblust/conventions at the release `conventions.json` names. Read them before writing or committing anything here.

- `conventions/WRITING.md` — how we write: one voice, three registers, English and German.
- `conventions/WORKING.md` — how we work with git and GitHub.
- `conventions/REPOSITORIES.md` — the family: what each repository is and what pins what.
- `conventions/WRITER.md`, `conventions/TRANSLATOR.md`, `conventions/EDITOR.md`,
  `conventions/BACKREADER.md`, `conventions/GLOSSARY.md`, `conventions/GERMAN.md` — the four roles
  that make a text, the terms they keep and the German they write.

Everything below this block is this repository's own. `sh conventions/conventions-sync check` says whether the copy matches the release, `sync` brings it to the release the pin names, and `sh conventions/conventions-check` holds this repository's own Markdown to `WRITING.md`, and `sh conventions/conventions-format` to its one form, which `fix` writes. Edit a shared file in robertblust/conventions, never here.
<!-- end conventions -->

# GuestGraph — working conventions

This repository is a CompanyGraph instance. The rules it is held to are vendored under `meta/core/`, and `meta/core/CONVENTIONS.md` is the one to read before writing anything here: one file per entity, a reference written as a canonical name, and a schema for every type under the same folder.

The mechanical half of those rules is checked by CI, and locally by `npx github:companygraph/meta-model#v<tooling> check`, where `<tooling>` is the release `.companygraph/manifest.json` names. What no check reads is each schema's `## Writing rules`, which an agent judges by reading them against the entity: the `companygraph-validate` skill runs both halves. `companygraph-export` packages the model for an agent and for Gemini Notebook, and `companygraph-surface` produces a surface the model records; both need Python 3. `companygraph-profile` builds a profile, or extends one, from a folder of the person's documents. All of them are the tooling's and move with an upgrade, so an instance's own skills go beside them under another name.

Everything below this line is this instance's own: how it is written, what it does not claim, and where its facts are mastered.

## What this is

GuestGraph, described in CompanyGraph's vocabulary. What `model/` holds is the project behind the guest identity graph: where it is going, what it will and will not do, what it ships and the words it means something exact by, and how a slice of it is delivered. `meta/core/` is core, vendored and never edited here; `.companygraph/manifest.json` records which release and a hash per file.

## How it is written

Prose follows `conventions/WRITING.md`, and an entity answers to its schema's `## Writing rules` in `meta/core/` as well. No check reads those; an agent judges them by reading them against the entity it is writing.

Entries are written and reviewed one at a time — what it says, the case against it, a proposal, and the owner decides — because these are editorial facts about a company rather than a schema being filled in. Nothing is committed ahead of that review.

## What it does not claim

**No person is described here.** No `skill`, `experience` or `proficiency-level` is written in this repository, and every profile it carries is an agent, by decision and not for the moment. GuestGraph is built by the company of one that `robertblust/mental-model` describes, and that is where the person is described; a profile for a person here would put one canonical name in two instances with two sets of facts behind it, and the second set would go stale without a sound. A `role` is a seat and names no holder. What a seat is held by is said once, by the agent profiles listing the seats each agent holds: a seat no profile names is held by a person, and which person is a fact this repository does not carry.

**Only what is built from this model is a surface.** guestgraph.io is, built by `guestgraph/guestgraph.github.io`, which draws its model pages from a pinned commit of this repository; so are the MCP server, its Registry listing and the chat, built by `guestgraph/mcp-guestgraph-io`. A place that is planned and not yet reachable has no file until it is.

**No count, threshold or version of the services is written here.** The engine's reference documents are the single place a matching value is defined, and the organization profile is the one place that says which phases have shipped; an entry that needs either says what it is and leaves the value where it lives.

## Where its facts are mastered

Every page is mastered here — `source: Local`, corrected in this repository and nowhere else. There is no upstream to correct first.

A fact enters from prose that is already published and already reviewed: the organization profile on GitHub, the pages and the introduction talk of guestgraph.io, the READMEs of the engine and the connector, and the engine's constitution and reference documents. A claim that cannot be traced to one of those does not go in, however true it sounds; the guard is against invention by whoever is editing.

## Checks

Two jobs, both required by the ruleset on `main`: `companygraph`, which calls meta-model's `instance-check.yml` at the release its workflow names and is shown by GitHub as `companygraph / companygraph`, and `conventions`, called from robertblust/conventions at the tag `conventions.json` names and shown as `conventions / conventions`. A ruleset requires a job by its id, so neither is renamed without its ruleset.

`meta/` is excluded from the prose check and from the Markdown form because it is core, vendored and never edited here; its words are core's to hold, and holding them here would fail this repository for a change made somewhere else.
