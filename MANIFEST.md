# PGC v3 — composed platform: deposit manifest

**Public identity:** v3
**Assembler ordinal:** 16
**Profile:** REFERENCE_PLATFORM_PROFILE_V1

**Sealed snapshot id**
`cb56beb413476f9be6e2b0f4dabc134a9fb072156d1aec5584a5157f98809167`

**Composite hash**
`cb56beb413476f9be6e2b0f4dabc134a9fb072156d1aec5584a5157f98809167`

## What this deposit is

The *composition* — a single governance surface assembling 7 governed domains,
including mutually unrelated business domains, over 410 protocol artifacts.
Claims about domain independence and closure refer to this artifact, not to any one component
repository. The 9 components are archived separately and named below as parts.

## Conformance

- Phase: `composition_conformance` (conformance v0, assembler 16)
- Artifacts examined: **410**
- Rules evaluated: **5**
- Status: **PASSED**
- Checked at: 2026-09-07T00:34:29Z

### Governed domains (7)

- `ai_governance` — graph address `92f1390ab2e62204…`
- `blockchain` — graph address `7ebdeabe69c15aea…`
- `book_library_mgmt` — graph address `714d777710c3bbe8…`
- `inspection` — graph address `c817428996724335…`
- `platform` — graph address `98b58901e7dc64eb…`
- `transformation` — graph address `0e20da43241c585c…`
- `workload` — graph address `0f8ad9f398389d33…`

## Standard claimed

Open Protocol-Governed Computing Standard, revision v0 — 10.5281/zenodo.22150616
(archived separately; related as `references`).

## Components (9)

| Component | Version DOI | Commit at `v3` | Contributes artifacts |
|---|---|---|---|
| `software_governance` | 10.5281/zenodo.22564615 | `e263fc0bca84` | yes |
| `conformance_workloads` | 10.5281/zenodo.22564783 | `753e2d14a6db` | yes |
| `business_domains` | 10.5281/zenodo.22564704 | `e2c9b54b37fe` | yes |
| `protocol_compiler` | 10.5281/zenodo.22564884 | `853f615f660c` | — |
| `protocol_runtime` | 10.5281/zenodo.22565005 | `d81725688c2e` | — |
| `snapshot_assembler` | 10.5281/zenodo.22565082 | `33326f06ffb1` | — |
| `protocol_transport` | 10.5281/zenodo.22565441 | `0c055b61e4a3` | — |
| `snapshot_inspector` | 10.5281/zenodo.22565012 | `c5d9f0ddbac6` | yes |
| `transformation` | 10.5281/zenodo.22565161 | `3066efd37382` | yes |

Components marked `—` are the toolchain; they produce and consume the snapshot rather than
contributing protocol artifacts to it.

### Commit provenance

The `v3` tags are orphan publication commits on `main`; the snapshot was assembled from the
corresponding `dev/16` commits, so the two carry different commit ids by construction. They
are the same content: `release.sh` verifies each orphan's tree against its `dev` tree before
pushing, and aborts if they differ.

## Contents

- `snapshot/` — the sealed snapshot as assembled, 597 files, 595
  constituents, committed expanded rather than archived, so every artifact is browsable and
  diffable between releases.
- `MANIFEST.md` — this file.
- `.zenodo.json` — deposit metadata, read by the GitHub–Zenodo integration when a release is tagged.

## Not included, and why

- **`.github`** — workspace process. It is released with the components and carries its own DOI,
  but it is process rather than a part of the composition, so it is not named as `hasPart`.
- **`standards`** — carries its own revision identity and is archived separately; related here as
  `references`.
