<p align="center">
  <img src="https://raw.githubusercontent.com/tplAIter/.github/main/assets/banner.png?v=20260928" alt="tplAIter — Build with blocks. Spend fewer tokens." width="100%">
</p>

<h1 align="center">template-base</h1>

<p align="center">Neutral bootstrap assets for a tplAIter template repository.</p>

<p align="center"><strong>Status: public development preview · local manifest</strong></p>

<p align="center"><a href="https://github.com/tplAIter/tplaiter">core CLI</a> · <a href="https://github.com/tplAIter/template-go">Go template</a> · <a href="https://github.com/tplAIter/template-rust">Rust template</a> · <a href="https://github.com/tplAIter/tplaiter/blob/main/docs/template-validation.md">validation workflow</a></p>

`template-base` contains the neutral bootstrap files used by the base template contract. Rendering is handled by the shared Go `text/template` engine from the core repository.

It is the small, reviewable starting point for an intended MCP-assisted flow:
an agent chooses parameters and blocks, the renderer materializes them, and
the shared checker verifies the manifest and fixture output. It does not mean
that a live project-creation workflow is available in this preview.

## Included

- `template.manifest.yaml` with the `template-base` identity and `files` render root.
- A native template contract with no dependencies.
- The retained base file skeleton under `files/`.

## Verification

The repository workflow runs on pushes, pull requests, and manual dispatch. It uses the pinned `tplAIter/tplaiter` template-check action to validate the manifest and render its fixture combinations. See the [core validation contract](https://github.com/tplAIter/tplaiter/blob/main/docs/template-validation.md) for the checker boundaries.

For local work, run the same core checker from a checked-out core repository against this template, then inspect the rendered fixture output. The checker does not run template hooks or manifest commands.

## Status

This preview has no published version, release, dependency graph, or production-readiness claim. The manifest version is `0.0.0-local`; further template composition and validation are still in progress.
