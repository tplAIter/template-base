# Task-scoped complete context

Purpose: keep the current task's declared resources and prerequisites together.
Version: 0.1.0. Selector: `base.block.task-context`. No prerequisites.

Identify the task, selected resources and returned immutable source pins. Consume
the complete mandatory floor, graph and file images. Do not replace required
context with an excerpt or treat catalog availability as an instruction to load
all resources. If the complete result does not fit, reduce the requested task
scope explicitly and select again; do not silently discard prerequisites.

Selection is readonly. Resource metadata, a provider label and this block do not
grant tool execution, project mutation, organization authority or model capacity.
