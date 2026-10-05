# File-only task-context materialization

Version: 0.1.0. Consumers: compiled exports.BuildSourceCatalog,
exports.ResolveSelections and exports.Materialize under authenticated ROOT admission.
Inputs: strict authored entries, payloads and exact immutable source blobs.
Outputs: complete readonly file images, pinned closure and explicit conflicts.
No command, formatter, hook, network operation or provider code executes.
The toolDigest pins these inert semantics; it is not an executable identity.
