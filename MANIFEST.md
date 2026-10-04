# PGC v5 — composed platform: deposit manifest

**Public identity:** v5
**Assembler ordinal:** 17
**Profile:** GOVERNANCE_SURFACE_PROFILE_V0

**Sealed snapshot id**
`f8356d9c8938aea16ab7850d7bda964d8d16c42c64e5db9056d5fe58040ec1d0`

**Composite hash**
`f8356d9c8938aea16ab7850d7bda964d8d16c42c64e5db9056d5fe58040ec1d0`

## What this deposit is

The *composition* — a single governance surface assembling 8 governed domains,
including mutually unrelated business domains, over 515 protocol artifacts.
Claims about domain independence and closure refer to this artifact, not to any one component
repository. The 9 components are archived separately and named below as parts.

## Conformance

- Phase: `composition_conformance` (conformance v0, assembler 17)
- Artifacts examined: **515**
- Rules evaluated: **5**
- Status: **PASSED**
- Checked at: 2026-10-04T01:14:13Z

### Governed domains (8)

- `ai_governance` — graph address `70bc902acb1e7727…`
- `blockchain` — graph address `a384e0cf8e5d3768…`
- `book_library_mgmt` — graph address `9f26cb4ced3230ea…`
- `causal_language_model` — graph address `3cbdd6668ca663cb…`
- `inspection` — graph address `fceedb73972c88a0…`
- `platform` — graph address `c6787de2f24cd506…`
- `transformation` — graph address `dab947a5805dd2fc…`
- `workload` — graph address `68559acbef74117f…`

## Standard claimed

Open Protocol-Governed Computing Standard, revision v0 — 10.5281/zenodo.22150616
(archived separately; related as `references`).

## Components (9)

| Component | Version DOI | Commit at `v5` | Contributes artifacts |
|---|---|---|---|
| `software_governance` | 10.5281/zenodo.23129781 | `74cba758807a` | yes |
| `conformance_workloads` | 10.5281/zenodo.23129784 | `b7028c745e1f` | yes |
| `business_domains` | 10.5281/zenodo.23129785 | `9c66e8a21603` | yes |
| `protocol_compiler` | 10.5281/zenodo.23129786 | `bf3217be13a4` | — |
| `protocol_runtime` | 10.5281/zenodo.23129787 | `9b96962d493c` | — |
| `snapshot_assembler` | 10.5281/zenodo.23129788 | `cfb194eb590b` | — |
| `protocol_transport` | 10.5281/zenodo.23129789 | `ec5d722b0bf7` | — |
| `snapshot_inspector` | 10.5281/zenodo.23129791 | `ea03124c4dcc` | yes |
| `transformation` | 10.5281/zenodo.23129792 | `4da9b66aca46` | yes |

Components marked `—` are the toolchain; they produce and consume the snapshot rather than
contributing protocol artifacts to it.

### Commit provenance

The `v5` tags are orphan publication commits on `main`; the snapshot was assembled from the
corresponding `dev/18` commits, so the two carry different commit ids by construction. They
are the same content: `release.sh` verifies each orphan's tree against its `dev` tree before
pushing, and aborts if they differ.

## Contents

- `snapshot/` — the sealed snapshot as assembled, 829 files, 827
  constituents, committed expanded rather than archived, so every artifact is browsable and
  diffable between releases.
- `MANIFEST.md` — this file.
- `.zenodo.json` — deposit metadata, read by the GitHub–Zenodo integration when a release is tagged.

## Not included, and why

- **`.github`** — workspace process. It is released with the components and carries its own DOI,
  but it is process rather than a part of the composition, so it is not named as `hasPart`.
- **`standards`** — carries its own revision identity and is archived separately; related here as
  `references`.
