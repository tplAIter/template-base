---
name: context-selection
description: Select complete task-scoped template-base resources through an installed authenticated ROOT context route when the task needs reusable context.
---
# Context selection

Select `base.skill.context-selection` for the current task with empty typed
bindings. The compiled resolver includes `base.block.task-context` automatically.
Use installed CLI `context select` or MCP `context` action `select`; the exact
request and output contracts are in [task selection](../../docs/task-context.md).

Check the successful result's snapshot, source pins, complete mandatory floor,
required chains and file hashes before consuming its images. Unknown/repeated
selectors, missing prerequisites, stale observations and insufficient complete
capacity refuse. Narrow the explicit request instead of dropping required data.

The returned images are readonly task context. This skill does not install itself,
apply rule overrides, execute tools or grant authority. Read
[catalog contracts](../../catalog/README.md) when enrolling or checking source data.
