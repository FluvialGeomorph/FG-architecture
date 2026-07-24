# Artifact lifecycle

## Create

Create an artifact only when its role is triggered. Use the applicable schema or template, identify authority, and link rather than duplicate.

## Maintain

Update current-state artifacts when their facts change. Record material choices in ADRs. Keep evidence classifications and open questions visible. Review links and contradictions whenever adjacent authority changes.

## Supersede

Do not rewrite historical accepted ADRs to match newer templates. Create a new ADR that names the superseded decision. For other durable artifacts, replace obsolete current-state text and preserve history through Git.

## Archive or remove

Archive a checkpoint when its operational history remains useful; remove it when it has no continuing value. Never use an archive as current authority. Do not retain complete chat transcripts as a substitute for promotion.

## Completion gate

Before completion, classify impacts across goals, architecture, decisions, schemas, workflows, features, user-facing behavior, and active state. Promote each durable outcome, verify the resulting artifacts, and create a checkpoint only if useful unfinished state remains.
