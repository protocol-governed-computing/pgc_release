# pgc_release

**The composed Protocol-Governed Computing platform — the artifact the paper's claims refer to.**

A platform is not a repository. It is the composition of a governance surface, workloads, and
business domains under a conformance profile. This repository holds one such composition, sealed:
the assembled snapshot for one public identity, together with the manifest naming every component
it was built from. Which identity, which snapshot, and which components are stated in `MANIFEST.md`,
which is generated at release time — this file does not restate them, because a hand-kept copy of a
generated fact is a copy that drifts.

It contains no source and no toolchain. It is the output the toolchain produced, kept so it can be
cited, browsed, and checked.

## Where it fits

```
software_governance    the normative surface every composition rests on
conformance_workloads  workloads that prove conformance
business_domains       domains built on the surface

protocol_compiler      source      → compiled projections
snapshot_assembler     projections → assembled snapshot
pgc_release            the assembled snapshot, sealed and cited   (this repo)
protocol_runtime       snapshot    → execution
snapshot_inspector     snapshot    → inspection
```

## What is here

- `snapshot/` — the sealed snapshot, expanded.
- `MANIFEST.md` — snapshot id, conformance result, and the nine components with their version DOIs
  and commits, for the identity this release carries.
- `.zenodo.json` — deposit metadata; the GitHub–Zenodo integration reads it when a release is tagged.

## Verifying

Reading what it claims about itself needs nothing installed:

```sh
python -c "import json;print(json.load(open('snapshot/manifest.json'))['snapshot_id'])"
python -c "import json;d=json.load(open('snapshot/conformance/composition.json'));print(d['status'],d['artifacts_examined'],'artifacts',d['rules_evaluated'],'rules')"
```

Both values are stated in `MANIFEST.md`. Compare them: the commands read the snapshot, the manifest
records what was sealed, and the two agreeing is the check. Nothing to look up, and nothing here that
can be stale — an expected value written into prose is one more thing that can be wrong, and once was.

That reads the claim. Checking the claim against the content — every constituent rehashed, the
identity re-derived, the profile evaluated — is what booting it does, below.

## Running it

This repository holds the snapshot and no toolchain. The toolchain is published separately, so
running the cited artifact takes an install and no build: nothing here is compiled, because the
compiling already happened and this is its output.

To build a platform from source rather than run this one — or to author a domain against it — see
[`pgc_install`](https://github.com/protocol-governed-computing/pgc_install).

**1. The toolchain, from PyPI.**

```sh
python3.12 -m venv .venv && source .venv/bin/activate
pip install protocol-governed-computing
```

**2. The profile this snapshot claims.** A snapshot names the conformance profile it claims, and
acceptance refuses to boot one whose profile it cannot read — a claim nobody can read is not a claim.
Profiles are published in the org's `.github` repository, which is where they are governed; this
repository does not carry a copy, because two copies of one profile are two things that can disagree.

```sh
git clone https://github.com/protocol-governed-computing/.github pgc_github
export PGC_SNAPSHOT_PROFILES=$PWD/pgc_github/snapshot_profiles
```

The snapshot names its profile in `snapshot/manifest.json` under `profile`, so you can check which
one is being read.

**3. Boot it.** This verifies every constituent against the manifest and refuses on any disagreement.

```sh
protocol_runtime boot --snapshot $PWD/snapshot
```

Expect seven domains resident and hash-verified.

**4. Inspect it.**

```sh
si --snapshot $PWD/snapshot snapshot summary
si --snapshot $PWD/snapshot snapshot validate
```

**5. Execute a workflow.** The payload is yours to write; nothing needs downloading.

```sh
echo '{"numbers": [27]}' > payload.json
protocol_runtime run \
  --wf workload::WF_COLLATZ_CONJECTURE_V0 \
  --payload $PWD/payload.json \
  --snapshot $PWD/snapshot \
  --data-root $PWD/data
```

Expect `SUCCESS`, `all_terminate: true`, and the 111-step sequence for 27.

**Paths must be absolute.** `--snapshot`, `--payload` and `--data-root` all refuse a relative path
rather than resolving it against a working directory the snapshot knows nothing about.

**macOS:** opening the snapshot in Finder writes a `.DS_Store` into it, and acceptance then refuses
the snapshot as carrying content its self-description does not enumerate. `find snapshot -name
.DS_Store -delete` restores it; nothing about the snapshot has changed.

## Citing

Cite the version DOI of the release you used. The component repositories carry their own DOIs and
are named in `MANIFEST.md`; cite this one when the claim is about the composition — every governed
domain under a single governance surface — rather than about any one component.

## Releasing

Each release is a new sealed composition:

1. Replace `snapshot/` with the newly assembled snapshot.
2. Update `MANIFEST.md` — snapshot id, conformance numbers, component DOIs and commits.
3. Update `version` in `.zenodo.json`, and add the new component DOIs as `hasPart`.
4. Bump `VERSION` to the assembler ordinal.
5. Tag and publish a GitHub release. Zenodo mints the version DOI automatically.

## License

Apache-2.0. See `LICENSE` and `NOTICE`.
