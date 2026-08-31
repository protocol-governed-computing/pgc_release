# PGC v2 — composed platform: deposit manifest

**Public identity:** v2  
**Assembler ordinal:** 13  
**Profile:** REFERENCE_PLATFORM_PROFILE_V1

**Sealed snapshot id**  
`4a1e88967b71a99a566d4b74b8b790fbbb3485149b02db7c401c853e463f7842`

**Composite hash**  
`4a1e88967b71a99a566d4b74b8b790fbbb3485149b02db7c401c853e463f7842`

## What this deposit is

The *composition* — a single governance surface assembling seven governed domains, including mutually unrelated business domains, over 410 protocol artifacts. Claims about domain independence and closure refer to this artifact, not to any one component repository. The nine components are archived separately and named below as parts.

## Conformance

- Phase: `composition_conformance` (conformance v0, assembler 13)
- Artifacts examined: **410**
- Rules evaluated: **5**
- Status: **PASSED**
- Checked at: 2026-08-31T01:44:14Z

### Governed domains (7)

- `ai_governance` — graph address `92f1390ab2e62204…`
- `blockchain` — graph address `7ebdeabe69c15aea…`
- `book_library_mgmt` — graph address `714d777710c3bbe8…`
- `inspection` — graph address `c817428996724335…`
- `platform` — graph address `98b58901e7dc64eb…`
- `transformation` — graph address `0e20da43241c585c…`
- `workload` — graph address `0f8ad9f398389d33…`

## Standard claimed

PGC Standard revision — 10.5281/zenodo.22150616 (archived separately; related as `references`).

## Components (9)

| Component | Version DOI | Commit at `v2` | Contributes artifacts |
|---|---|---|---|
| `software_governance` | 10.5281/zenodo.22183277 | `2326a6f9fd1a` | yes |
| `conformance_workloads` | 10.5281/zenodo.22183279 | `5fdde4683e7f` | yes |
| `business_domains` | 10.5281/zenodo.22183281 | `666d3b09703f` | yes |
| `protocol_compiler` | 10.5281/zenodo.22183283 | `6cd3ebc0f618` | — |
| `protocol_runtime` | 10.5281/zenodo.22183285 | `d92164662b7c` | — |
| `snapshot_assembler` | 10.5281/zenodo.22183287 | `e951c27b3668` | — |
| `protocol_transport` | 10.5281/zenodo.22183291 | `74748ea55e16` | — |
| `snapshot_inspector` | 10.5281/zenodo.22183293 | `4e0aa0aa3531` | yes |
| `transformation` | 10.5281/zenodo.22183296 | `342c735741b9` | yes |

The four components marked `—` are the toolchain (compiler, assembler, runtime, transport); they produce and consume the snapshot rather than contributing protocol artifacts to it.

### Commit provenance

The `v2` tags are squash-merge commits on `main`; the snapshot was assembled from the corresponding `dev/14` commits, so the two carry different commit ids by construction. They are the same content: for every artifact-contributing component the commit trees are identical (`git rev-parse <dev-commit>^{tree}` equals `git rev-parse v2^{tree}`, and `git diff <dev-commit> v2` is empty). The sealed snapshot therefore corresponds exactly to the tagged `v2` state that the component DOIs archive.

## Contents

- `snapshot/` — the sealed snapshot as assembled, 597 files, 595 constituents, committed expanded rather than archived, so every artifact is browsable on GitHub and diffable between releases. `snapshot/manifest.json` carries the snapshot id above; `snapshot/conformance/composition.json` carries the conformance result.
- `MANIFEST.md` — this file.
- `.zenodo.json` — deposit metadata, read by the GitHub–Zenodo integration when a release is tagged.

## Not included, and why

- **`.github`** — workspace process (release scripts, checks, runbook). Process, not a citable component of the composition.
- **`standards`** — carries its own revision identity and is archived separately; related here as `references`.
