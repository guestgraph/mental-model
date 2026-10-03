---
id: 01a0ffcb-f64d-7b19-a126-b386e59263cc
source: Local
kind: detective
mode: automated
enforces:
  - A change to what another repository vendors is released
---

# A vendored copy is held to the release it names

> A pull request fails where what a repository vendors differs from the release it pins, so a change reaches another repository only once it is released.

## How it is carried out

The conventions job, required on the default branch of each of our repositories, on every pull request: `conventions-sync check` compares the vendored `conventions/` with the release `conventions.json` names and fails for each file that differs. In the engine and the Apaleo connector, the required `service-conventions` job runs `service-conventions-sync check`, which fails where the vendored service conventions differ from the release they pin. In our model, the required instance check refuses a checker other than the release `.companygraph/manifest.json` names and fails where a vendored core file differs from the hash the manifest recorded when that release was taken. Nothing checks what a release's notes ask of a consumer.

## Applies to

| Type | Entity | Owner |
| --- | --- | --- |
| phase | Integrate | Delivery |
| phase | Integrate | Contribution |

## References

| What | URL |
| --- | --- |
| The conventions job | https://github.com/robertblust/conventions/blob/main/.github/workflows/check.yml |
| The conventions copy check | https://github.com/robertblust/conventions/blob/main/conventions/conventions-sync |
| The engine's CI | https://github.com/guestgraph/engine/blob/main/.github/workflows/verify.yml |
| The service conventions copy check | https://github.com/guestgraph/service-conventions/blob/main/spring/service-conventions-sync |
| The instance check | https://github.com/companygraph/meta-model/blob/main/.github/workflows/instance-check.yml |
