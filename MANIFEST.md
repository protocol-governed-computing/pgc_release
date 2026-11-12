# PGC v7 — composed platform: deposit manifest

**Public identity:** v7
**Assembler ordinal:** 19
**Profile:** GOVERNANCE_SURFACE_PROFILE_V0

**Sealed snapshot id**
`8ad89baa75ce1412bb61dceb5bc5dc11eeba146c96eed600d43c169b2d447982`

**Composite hash**
`8ad89baa75ce1412bb61dceb5bc5dc11eeba146c96eed600d43c169b2d447982`

## What this deposit is

The *composition* — a single governance surface assembling 8 governed domains,
including mutually unrelated business domains, over 603 protocol artifacts.
Claims about domain independence and closure refer to this artifact, not to any one component
repository. The 9 components are archived separately and named below as parts.

## Conformance

- Phase: `composition_conformance` (conformance v0, assembler 19)
- Artifacts examined: **603**
- Rules evaluated: **5**
- Status: **PASSED**
- Checked at: 2026-11-12T01:03:34Z

### Governed domains (8)

- `ai_governance` — graph address `9d3769cd06e05c08…`
- `blockchain` — graph address `64c3d7832831c714…`
- `book_library_mgmt` — graph address `3028eda9475b28d7…`
- `causal_language_model` — graph address `62da88a930c69c3a…`
- `inspection` — graph address `105bd8c89088adbf…`
- `platform` — graph address `d7fa834815208003…`
- `transformation` — graph address `be8b1cb5bb2baa23…`
- `workload` — graph address `e9c71cd86bfc5d7b…`

## Standard claimed

Open Protocol-Governed Computing Standard, revision v1 — 10.5281/zenodo.23486349
(archived separately; related as `references`).

## Components (9)

| Component | Distribution | Version DOI | Commit at `v7` | Contributes artifacts |
|---|---|---|---|---|
| `software_governance` | `pgc-governance` 7.0.0 | 10.5281/zenodo.24148805 | `c8999affcd24` | yes |
| `conformance_workloads` | `pgc-workloads` 7.0.0 | 10.5281/zenodo.24148806 | `0a300f3687c9` | yes |
| `business_domains` | `pgc-domains` 7.0.0 | 10.5281/zenodo.24148807 | `84c61b90e4e3` | yes |
| `protocol_compiler` | `pgc-compiler` 7.0.0 | 10.5281/zenodo.24148808 | `25ec6b7460da` | — |
| `protocol_runtime` | `pgc-runtime` 7.0.0 | 10.5281/zenodo.24148809 | `8a68ddf4569c` | — |
| `snapshot_assembler` | `pgc-assembler` 7.0.0 | 10.5281/zenodo.24148810 | `dcb3abc85b19` | — |
| `protocol_transport` | `pgc-transport` 7.0.0 | 10.5281/zenodo.24148811 | `e55a317c4ac1` | — |
| `snapshot_inspector` | `pgc-inspector` 7.0.0 | 10.5281/zenodo.24148812 | `2684b2b8bc28` | yes |
| `transformation_compilers` | `pgc-transformation` 7.0.0 | 10.5281/zenodo.24148813 | `b3f660dba72e` | yes |

Components marked `—` are the toolchain; they produce and consume the snapshot rather than
contributing protocol artifacts to it.

### Commit provenance

The `v7` tags are orphan publication commits on `main`; the snapshot was assembled from the
corresponding `dev/20` commits, so the two carry different commit ids by construction. They
are the same content: `release.sh` verifies each orphan's tree against its `dev` tree before
pushing, and aborts if they differ.

## Contents

- `snapshot/` — the sealed snapshot as assembled, 894 files, 892
  constituents, committed expanded rather than archived, so every artifact is browsable and
  diffable between releases.
- `composition.json` — the record this manifest is generated from: each component's distribution,
  version, commit and DOI, and the snapshot identity. `pgc_install`'s pins are generated from it.
- `MANIFEST.md` — this file.
- `.zenodo.json` — deposit metadata, read by the GitHub–Zenodo integration when a release is tagged.

## Not included, and why

- **`.github`** — workspace process. It is released with the components and carries its own DOI,
  but it is process rather than a part of the composition, so it is not named as `hasPart`.
- **`standards`** — carries its own revision identity and is archived separately; related here as
  `references`.
