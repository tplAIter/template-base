# Transparent typed rule composition

Version: 0.1.0. Selector: `base.approach.transparent-overrides`.
Required context: `base.block.rule-overrides`.

The compiled `exports.ResolveModifiers` API accepts a `RuleSet` and parsed
`Modifier` documents (`tplaiter.dev/modifier/v1`). This is a separate pure API:
ROOT selection materializes this explanation and its required block; it does not
invoke the resolver or mutate a project automatically.

`RuleSet` carries active rules with ID/digest/version/provider, required
capabilities, prior tombstones and observed export/tool facts. Each `Modifier`
retains exact source pins, compatibility, typed requirements/bindings, explicit
operations and capability/tool constraints. Obtain concrete pins and facts from
verified source selection; this document supplies no mutable grant or self pin.

| Operation | Input precondition | Result |
| --- | --- | --- |
| `add` | Fresh ID and available export | New active rule with a derived digest |
| `replace` | Active target, matching `expectedDigest`, optional `expectedVersion` | New active rule; old digest retained in a replace tombstone with `replacedBy` |
| `remove` | Active target with matching preconditions | Target retired in a remove tombstone |

Every operation has explicit `before` and `after` arrays. They order operations;
there is no task/global/project priority ladder. Capability replacement needs
explicit mappings. Active or retired IDs cannot be reused.

A bounded composition example uses the actual selected `base.block.task-context`
payload digest as the active `context-default` rule's digest. A modifier replaces
it with `context-explicit`, then adds `context-notes` with
`after: ["context-explicit"]`. The output has two active rules, one replace
tombstone retaining the original digest, ordered replace/add operations, new rule
digests and a composition digest. A following remove of `context-notes`, using
its returned digest, leaves one active rule and two tombstones. Replacing with a
stale expected digest, introducing an ordering cycle or reusing the retired ID
refuses. Full typed inputs and outputs must retain the concrete selected source,
contract and export facts; the operation description alone is not a Modifier wire
or a source authorization.

These are deterministic metadata operations. Neither composition nor the selected
Markdown runs a tool, hook, provider program or installation command.
