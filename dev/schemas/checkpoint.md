# Checkpoint schema

A checkpoint is a Markdown file representing one active work stream. Store current instances in `dev/checkpoints/current/` and optional retained history in `dev/checkpoints/archive/`.

## Required sections

1. H1 title
2. `Date` in `YYYY-MM-DD`
3. `Status` (`active` or `blocked`; archived instances may use `completed` or `superseded`)
4. `Owning repository or work stream`
5. `Objective`
6. `Completed work`
7. `Current state`
8. `Verification performed`
9. `Remaining work`
10. `Next action`
11. `Risks and unknowns`
12. `Durable records updated`

All sections are required; use `None` when genuinely empty. The next action must be concrete enough for a new task to execute. Paths must be repository-relative where practical.

## Invariants

- Maintain one checkpoint per active work stream, not one per conversation.
- Summarize outcomes and state; do not paste a transcript or large log.
- Do not include secrets, PII, restricted data, or sensitive local paths.
- A checkpoint cannot supersede an ADR, architecture document, schema, workflow, or implementation evidence.
- Update the existing checkpoint as work advances.
- Archive or remove it when no useful resumable state remains.
