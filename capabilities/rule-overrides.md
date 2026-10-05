# Explicit rule override context

Purpose: make each rule change and its provenance inspectable.
Version: 0.1.0. Selector: `base.block.rule-overrides`. No prerequisites.

Use explicit typed add, replace or remove operations. Replacement/removal checks
the active target's expected digest and optional version. Keep operation ordering,
new digests and retired-rule tombstones in the resulting composition. An ordering
edge is not an implicit precedence ladder. Stale preconditions or reuse of retired
IDs refuse; resolve the conflict before composing again.

This block describes pure composition. Selecting it does not apply rules or run
tools. See `base.approach.transparent-overrides` for the input/output boundary.
