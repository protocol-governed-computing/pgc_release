# PGC v6 — composed platform: deposit manifest

**Public identity:** v6
**Assembler ordinal:** 18
**Profile:** GOVERNANCE_SURFACE_PROFILE_V0

**Sealed snapshot id**
`13e3c5bb502e2548389f5787caa9438247ee34f9d510ce6a8a3ed980fdf974d1`

**Composite hash**
`13e3c5bb502e2548389f5787caa9438247ee34f9d510ce6a8a3ed980fdf974d1`

## What this deposit is

The *composition* — a single governance surface assembling 8 governed domains,
including mutually unrelated business domains, over 556 protocol artifacts.
Claims about domain independence and closure refer to this artifact, not to any one component
repository. The 9 components are archived separately and named below as parts.

## Conformance

- Phase: `composition_conformance` (conformance v0, assembler 18)
- Artifacts examined: **556**
- Rules evaluated: **5**
- Status: **PASSED**
- Checked at: 2026-10-19T22:06:01Z

### Governed domains (8)

- `ai_governance` — graph address `19b1ffd62b01c6d7…`
- `blockchain` — graph address `61fb675d65a9d523…`
- `book_library_mgmt` — graph address `241cc19d20e092a0…`
- `causal_language_model` — graph address `0cb00fe1720d17c0…`
- `inspection` — graph address `ca1ed12896a102f8…`
- `platform` — graph address `0b46cb9cd37263fc…`
- `transformation` — graph address `f6b5d15e8da60a12…`
- `workload` — graph address `2fed05e3e9077e25…`

## Standard claimed

Open Protocol-Governed Computing Standard, revision v0 — 10.5281/zenodo.22150616
(archived separately; related as `references`).

## Components (9)

| Component | Distribution | Version DOI | Commit at `v6` | Contributes artifacts |
|---|---|---|---|---|
| `software_governance` | `pgc-governance` 6.0.0 | 10.5281/zenodo.23485266 | `f37f22a07bcc` | yes |
| `conformance_workloads` | `pgc-workloads` 6.0.0 | 10.5281/zenodo.23485267 | `7db60796a63e` | yes |
| `business_domains` | `pgc-domains` 6.0.0 | 10.5281/zenodo.23485268 | `df2d0e97ddf5` | yes |
| `protocol_compiler` | `pgc-compiler` 6.0.0 | 10.5281/zenodo.23485269 | `c8d7a28079a8` | — |
| `protocol_runtime` | `pgc-runtime` 6.0.0 | 10.5281/zenodo.23485270 | `c3d5d962052e` | — |
| `snapshot_assembler` | `pgc-assembler` 6.0.0 | 10.5281/zenodo.23485271 | `e32494fc48c1` | — |
| `protocol_transport` | `pgc-transport` 6.0.0 | 10.5281/zenodo.23485272 | `4dc586bcc09c` | — |
| `snapshot_inspector` | `pgc-inspector` 6.0.0 | 10.5281/zenodo.23485273 | `4ced82108ba0` | yes |
| `transformation_compilers` | `pgc-transformation` 6.0.0 | 10.5281/zenodo.23485274 | `938d14968ee9` | yes |

Components marked `—` are the toolchain; they produce and consume the snapshot rather than
contributing protocol artifacts to it.

### Commit provenance

The `v6` tags are orphan publication commits on `main`; the snapshot was assembled from the
corresponding `dev/19` commits, so the two carry different commit ids by construction. They
are the same content: `release.sh` verifies each orphan's tree against its `dev` tree before
pushing, and aborts if they differ.

## Contents

- `snapshot/` — the sealed snapshot as assembled, 892 files, 890
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
