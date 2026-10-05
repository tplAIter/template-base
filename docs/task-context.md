# Select complete task context

The installed authenticated ROOT route reads the signed root binding from the
verified source snapshot. Its default path is `catalog/context-root-bindings.v1.json`.
It derives the catalog with the compiled generic data builder and closes each
selected export's typed requirements before producing output.

An installed CLI request for the skill is:

```sh
tplaiter context select --json --request '{"selections":[{"apiVersion":"tplaiter.dev/export-selection/v1","selector":"base.skill.context-selection","bindings":[]}],"maxRecords":256,"maxBytes":32768}'
```

The existing MCP `context` tool uses the same registered route:

```json
{"action":"select","rootSelection":{"selections":[{"apiVersion":"tplaiter.dev/export-selection/v1","selector":"base.skill.context-selection","bindings":[]}],"maxRecords":256,"maxBytes":32768}}
```

The skill includes `base.block.task-context`; the approach includes
`base.block.rule-overrides`. Batch selections coalesce shared prerequisites while
retaining all dependency chains and source/export identities. Each export has
empty typed parameters and uses empty `bindings`. Requests allow 1..16 selections,
1..256 records and 1..32768 bytes. Unknown or repeated selectors refuse.

Successful `ContextData` has `action: "select"`, a snapshot and typed
`nativeRootSelection`: complete mandatory floor, graph, source/evidence/contract
pins, delivery digests and file images with exact content hashes and modes.
File content is JSON base64. `bytes` measures the serialized outer data; the final
CLI/MCP frame has its own bound including envelope, escaped strings and newline.
Insufficient complete capacity refuses the whole result rather than truncating a
prerequisite or image. Model context-window state remains unknown.

Use the returned snapshot as `snapshot` on a later request when continuity is
required. Stale pins, changed captured source or sealed locks, missing prerequisite
and cancellation refuse. The runtime retains its real read session through final
serialized delivery. A successful selection is a readonly task-context preview,
not installation of a skill or application of rule changes.

`rootSelection` is exclusive with query `request` and local `preview`, including
null-valued fields. The existing query and explicitly untrusted local-preview
actions remain distinct contracts. A request cannot supply a publisher, source
pin, executable, authority flag or model-window grant.
