# Inert source-bound catalog data

`entries.json` is an array of the existing strict core `ExportEntry` type. It is
not a complete Catalog wire document. Each record has exactly `id`, `domain`,
`name`, `version`, `contentDigest`, `parameters`, `toolDigest` and typed `requires`.
Domains are singular `block`, `skill` and `approach`. All four exports are version
`0.1.0`; parameters are empty. Requirement ranges are `>=0.1.0 <0.2.0`.

`contentDigest` is raw SHA256 of `payloads/<id>.json`. Each strict
`tplaiter.dev/export-payload/v1` document has exact file source/target paths, mode
`100644` and raw file-content SHA256, with empty `slots` and `blocks`.
`toolDigest` is raw SHA256 of `tool-contract.md`. Cross-export targets must remain
portable, case-consistent and free of file/ancestor collisions.

The native v1 contract pins raw `template.manifest.yaml` bytes and retains empty
dependencies. Its source-contract identity is the existing domain digest:
`DomainDigest("tplaiter.dev/source-contract/v1", {apiVersion:
"tplaiter.dev/source-contract/v1", path: "template.contract.json", contentSHA256:
SHA256(raw contract bytes)})`. Typed requirement `contractDigest` uses this identity,
not the raw contract hash. Changing manifest/contract bytes requires recomputing it.
Changing a resource requires updating its payload hash and entry contentDigest.

`context-root-bindings.v1.json` uses the existing closed
`tplaiter.dev/context-root-bindings/v1` contract. It declares alias `base`, provider
`template-base`, empty parameters and snapshot-relative entries/payload/tool paths.
It contains no commit, tree digest, source evidence, executable or trust Boolean.

After an immutable source commit exists, normal operator enrollment captures and
verifies that exact public Git closure. The configured installed runtime supplies
commit/tree/contract/evidence pins and retained source snapshots. Its compiled
collector passes immutable bytes to generic `exports.BuildSourceCatalog` with
`SourceCatalogInput {Pins, Alias, Data}`. The pure builder validates data and never
grants authority. It derives the existing `tplaiter.dev/export-catalog/v1` wire
with provider, source graph key, contractDigest and exports. ResolveSelections
closes prerequisites; Materialize produces complete file images. No provider
adapter, Go compilation, overlay or script is part of this runtime route.

Keep derived catalogs, enrollment evidence and publication receipts outside this
source commit. A commit cannot contain its own immutable commit/tree pin. The
local-operator route attests captured bytes without asserting upstream authorship
or organization authority. Existing enrollment inputs select one source and finite
project contexts; later authority refresh and dependency enrollment are separate.

The installed ROOT action returns a complete bounded readonly preview. Missing,
unknown or duplicate selectors, malformed declarations, digest mismatches, missing
required blocks and unsafe topology refuse. Selection does not apply modifier
operations or write context files into a project. See [task requests](../docs/task-context.md)
and [typed rule composition](../docs/rule-overrides.md).
