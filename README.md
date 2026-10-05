# Template base

A neutral Go-template root with versioned, reusable task context. The existing
`files` engine renders the project README. Context resources are selected
separately through the compiled authenticated ROOT consumer; they are not copied
into a project or executed automatically by rendering.

| Selector | Purpose | Required context |
| --- | --- | --- |
| `base.block.task-context` | Task scope and complete context consumption | None |
| `base.block.rule-overrides` | Explicit rule changes and retained provenance | None |
| `base.skill.context-selection` | Select complete task context | `base.block.task-context` |
| `base.approach.transparent-overrides` | Explain typed rule composition | `base.block.rule-overrides` |

All four exports are version `0.1.0`. See [task selection](docs/task-context.md),
[rule composition](docs/rule-overrides.md), and [catalog contracts](catalog/README.md).

Use a compiled core build with authenticated ROOT selection support. A configured
operator must capture an immutable source commit, enroll its public evidence,
install the pinned registration, provision trust, and create the project through
normal `new`. See the core [source enrollment documentation](https://github.com/tplAIter/tplaiter/blob/main/docs/source-enrollment.md).
Local-operator attestation describes approved captured bytes; it does not establish
upstream authorship or organization authority.

This source supplies data only: Markdown, closed JSON declarations and immutable
payload digests. Selection returns complete readonly file images with source pins
and prerequisite closure. No tool, formatter, hook or provider program runs.
Dependency enrollment and project writes are separate contracts. This template's
native v1 contract keeps `dependencies: []`.
