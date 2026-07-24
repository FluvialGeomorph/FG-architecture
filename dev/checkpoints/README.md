# Checkpoints

Checkpoints preserve concise state only when meaningful work must be resumed in a later task. Maintain one file per active work stream under `current/`, using the exact [checkpoint schema](../schemas/checkpoint.md) and [template](template.md). Do not store full conversations, routine completed-task summaries, durable decisions, or large logs here.

Update a checkpoint whenever its work advances or risks change. The work-stream owner maintains it while active. When work completes, promote durable conclusions first, then archive the checkpoint only if its operational history remains useful; otherwise remove it. Checkpoints are lower authority than maintained durable artifacts and implementation evidence.
