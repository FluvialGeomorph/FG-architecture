# Durable development context

`dev/` contains maintained organization knowledge, governance, and operational state. It does not contain implementation code, user-facing member-repository documentation, or full chat transcripts.

| Directory | Role |
|---|---|
| `goals/` | Organization scope, goals, and non-goals |
| `architecture/` | System structure, dependencies, ownership, and authority |
| `decisions/` | Consequential choices and rationale |
| `governance/` | Artifact standards, lifecycle, and adoption |
| `workflows/` | Repeatable procedures |
| `schemas/` | Exact structural contracts |
| `features/` | Cross-repository capability design |
| `checkpoints/` | Concise resumable state |
| `scripts/` | Proven maintenance automation, when justified |

Use the narrowest applicable artifact. Promote important outcomes from conversations before completing work, and avoid duplicating the same authority across artifacts.

Update this map when a durable artifact role or standard directory changes. FluvialGeomorph maintainers own the map; it remains current until revised through the applicable governance and decision process. Each child directory's README defines its local lifecycle and relationship to the other artifacts.
