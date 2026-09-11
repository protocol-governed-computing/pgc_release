# PGC v4 — composed platform: deposit manifest

**Public identity:** v4
**Assembler ordinal:** 16
**Profile:** GOVERNANCE_SURFACE_PROFILE_V0

**Sealed snapshot id**
`d92b447fd39eaf926bb2f4330f9efbb19d744ecfbc3fe9a214ae52945918905d`

**Composite hash**
`d92b447fd39eaf926bb2f4330f9efbb19d744ecfbc3fe9a214ae52945918905d`

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
- Checked at: 2026-09-11T21:05:08Z

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

| Component | Version DOI | Commit at `v4` | Contributes artifacts |
|---|---|---|---|
| `software_governance` | 10.5281/zenodo.22714508 | `405dc8e0b32c` | yes |
| `conformance_workloads` | 10.5281/zenodo.22714505 | `ed30babeb0bc` | yes |
| `business_domains` | 10.5281/zenodo.22714506 | `8c9fe7555499` | yes |
| `protocol_compiler` | 10.5281/zenodo.22714509 | `90b6425c8d85` | — |
| `protocol_runtime` | 10.5281/zenodo.22714512 | `6148e2699b24` | — |
| `snapshot_assembler` | 10.5281/zenodo.22714507 | `97c860269356` | — |
| `protocol_transport` | 10.5281/zenodo.22714513 | `5d46d29e52a9` | — |
| `snapshot_inspector` | 10.5281/zenodo.22714514 | `e55637e02331` | yes |
| `transformation` | 10.5281/zenodo.22714518 | `b7f6808878ea` | yes |

Components marked `—` are the toolchain; they produce and consume the snapshot rather than
contributing protocol artifacts to it.

### Commit provenance

The `v4` tags are orphan publication commits on `main`; the snapshot was assembled from the
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
