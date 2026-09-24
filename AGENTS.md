# GuestGraph — working conventions

This repository is a CompanyGraph instance. The rules it is held to are vendored under `meta/core/`, and `meta/core/CONVENTIONS.md` is the one to read before writing anything here: one file per entity, a reference written as a canonical name, and a schema for every type under the same folder.

The mechanical half of those rules is checked by CI, and locally by `npx github:companygraph/meta-model#v<tooling> check`, where `<tooling>` is the release `.companygraph/manifest.json` names. What no check reads is each schema's `## Writing rules`, which an agent judges by reading them against the entity: the `companygraph-validate` skill runs both halves. `companygraph-export` packages the model for an agent and for Gemini Notebook, and `companygraph-surface` produces a surface the model records; both need Python 3. `companygraph-profile` builds a profile, or extends one, from a folder of the person's documents. All of them are the tooling's and move with an upgrade, so an instance's own skills go beside them under another name.

Everything below this line is this instance's own: how it is written, what it does not claim, and where its facts are mastered.
