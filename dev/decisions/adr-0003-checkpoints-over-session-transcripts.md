# ADR 0003: Checkpoints instead of complete chat transcripts

- **Date:** 2026-07-24
- **Status:** Accepted

## Context

Complete AI conversations are large, repetitive, may contain unsuitable operational detail, and mix discarded reasoning with final decisions. New tasks need concise resumable state and maintained conclusions, not a replay of every chat turn.

## Decision

Complete AI transcripts are not standard project artifacts. Durable conclusions are promoted to their proper goals, architecture, ADR, schema, workflow, or feature artifact. When meaningful work remains unfinished, one maintained checkpoint per active work stream preserves concise resumable state. Git, tests, accepted ADRs, and maintained documentation provide the audit trail. Checkpoints are archived or removed when no longer operationally useful.

## Rationale

Distillation improves discoverability, reduces sensitive-data risk, prevents obsolete reasoning from competing with maintained authority, and gives future work a bounded resumption point.

## Alternatives considered

- **Commit every full transcript.** Rejected because volume and mixed authority harm retrieval and governance.
- **Keep no continuity artifact.** Rejected because interrupted work would be costly and risky to reconstruct.
- **Create one checkpoint per chat turn.** Rejected because it recreates transcript fragmentation and drift.

## Consequences

Agents must promote durable outcomes before completion and exercise judgment about whether resumable state remains. Checkpoints are operational, not historical authority. Some exploratory reasoning will intentionally not be retained.

## Verification

Check that current checkpoints conform to the schema, correspond one-to-one with active work streams, contain no transcript dumps, and link to updated durable records.

## Follow-up

Review checkpoint usefulness during context-health reviews and archive or remove stale records.
