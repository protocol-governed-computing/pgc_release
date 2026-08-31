# pgc_release

**The composed Protocol-Governed Computing platform — the artifact the paper's claims refer to.**

A platform is not a repository. It is the composition of a governance surface, workloads, and
business domains under a conformance profile. This repository holds one such composition, sealed:
the assembled snapshot for public identity `v2`, together with the manifest naming every component
it was built from.

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

- `snapshot/` — the sealed snapshot, expanded. 597 files across seven governed domains.
- `MANIFEST.md` — snapshot id, conformance result, and the nine components with their version DOIs
  and commits at `v2`.
- `.zenodo.json` — deposit metadata; the GitHub–Zenodo integration reads it when a release is tagged.

## Verifying

```sh
python -c "import json;print(json.load(open('snapshot/manifest.json'))['snapshot_id'])"
python -c "import json;d=json.load(open('snapshot/conformance/composition.json'));print(d['status'],d['artifacts_examined'],'artifacts',d['rules_evaluated'],'rules')"
```

Expected: snapshot id `4a1e88967b71a99a566d4b74b8b790fbbb3485149b02db7c401c853e463f7842`,
and `PASSED 410 artifacts 5 rules`.

## Citing

Cite the version DOI of the release you used. The component repositories carry their own DOIs and
are named in `MANIFEST.md`; cite this one when the claim is about the composition — seven governed
domains over 410 artifacts under a single governance surface — rather than about any one component.

## Releasing

Each release is a new sealed composition:

1. Replace `snapshot/` with the newly assembled snapshot.
2. Update `MANIFEST.md` — snapshot id, conformance numbers, component DOIs and commits.
3. Update `version` in `.zenodo.json`, and add the new component DOIs as `hasPart`.
4. Bump `VERSION` to the assembler ordinal.
5. Tag and publish a GitHub release. Zenodo mints the version DOI automatically.

## License

Apache-2.0. See `LICENSE` and `NOTICE`.
