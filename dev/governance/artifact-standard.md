# Artifact standard

## Distinct roles

| Artifact | Purpose |
|---|---|
| Goals | Approved scope, goals, and non-goals |
| Architecture | Stable current system structure and ownership |
| ADR | Consequential choice, rationale, alternatives, consequences |
| Governance | Cross-cutting artifact and adoption rules |
| Workflow | Repeatable procedure |
| Schema | Exact data, file, interface, or artifact contract |
| Feature | Cohesive cross-repository capability design |
| Checkpoint | Concise resumable unfinished state |
| Member user docs | User behavior, guidance, examples, releases |

Do not duplicate the same authoritative content. Link to the owner and summarize only what a reader needs for navigation.

## Promotion matrix

| Change introduced | Required destination |
|---|---|
| Goal, scope, or non-goal | `dev/goals/` |
| Component boundary or runtime flow | `dev/architecture/` |
| Consequential choice among alternatives | ADR |
| Data, file, interface, or artifact contract | `dev/schemas/` |
| Repeatable procedure | `dev/workflows/` |
| Cohesive feature behavior or design | `dev/features/` |
| Resumable unfinished work | Current checkpoint |
| User-facing behavior | Owning repository's README, vignette, help, or NEWS as appropriate |
| No durable impact | No governance update |

## Authority and precedence

Use the [authority model](../architecture/authority-model.md). Accepted ADRs govern their decisions; current architecture states maintained boundaries; schemas govern exact documented structure; workflows govern procedure; checkpoints govern no durable design.

Code, tests, and configuration evidence actual behavior and can expose documentation drift. Drift requires reconciliation, not an automatic assumption that either implementation or prose is intended.

## Internal versus user-facing documentation

Internal development context belongs under `dev/`. User guidance, exported API documentation, vignettes, help, release notes, and published sites belong in the implementing repository's normal user-documentation locations. Do not publish internal rationale as user guidance unless it is genuinely useful and approved for that audience.

## Evidence and information safeguards

Claims must be labeled `verified`, `inferred`, or `unknown`. Cite safe repository evidence instead of copying secrets or sensitive material. Never place credentials, tokens, PII, restricted data, unsuitable internal system details, or large sensitive logs in context artifacts. Session history is non-authoritative and full transcripts are not normal context sources.
