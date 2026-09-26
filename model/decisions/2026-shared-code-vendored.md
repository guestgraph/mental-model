---
source: Local
decided: 2026-09-11
kind: Architecture
status: Standing
by: Owner
---

# What every service shares is copied in at a pinned release, never published

> We keep the build, the checks and the runtime code every service shares in one repository, and each service vendors a copy at the release it pins, held to that release by a check; nothing is published to a package registry.

## The question

How the engine and the connector share the rules and the code they had each carried by hand, the parent build, the architecture tests, the error shape and the filters, once the copies had begun to differ. It had to be decided in September 2026, when the connector had become the second service and every later one would start from whichever copy it found.

## Alternatives

| Option | Why not |
| --- | --- |
| A parent build and a library published to a package registry | Nothing in the family is published, and a registry would put a credential into every build, the public ones included. |
| A jar committed into each service | A binary in git that no one can review in a diff, held no better than source. |
| Each service keeping its own copy by hand | The copies were already drifting, and a service with a rule missing passes its own checks. |

## Why

The family already shares its writing rules and the design system by vendoring at a pin, and the tag is the release, so a service takes shared files the one way it takes everything else. Maven reads a parent build by path, which shares plugins and versions without a repository, and the shared runtime code sits under the package name a published library would carry, so the copy can become a dependency later without a rename in any service. A check reads each copy against the release it pins, so a copy that drifts fails rather than diverges.

## Consequences

A rule changed once reaches every service by moving its pin; a service with a shared file edited in place fails its check; a new service is scaffolded from the rule set and passes on its first run. What it gave up is a dependency a build resolves on its own. It stays right for as long as nothing in the family publishes, and the day something does, the copies are replaced by the dependency under the same names.

## Bears on

| Type | Entity | Owner | How |
| --- | --- | --- | --- |
| product | GuestGraph Engine | | changed it |
| product | Apaleo Connector | | changed it |

## References

| What | URL |
| --- | --- |
| The service conventions research, R1 and R2 | https://github.com/guestgraph/engine/blob/main/specs/007-service-conventions/research.md |
| The shared runtime research, R1 | https://github.com/guestgraph/engine/blob/main/specs/008-shared-runtime/research.md |
| The shared repository | https://github.com/guestgraph/service-conventions |
