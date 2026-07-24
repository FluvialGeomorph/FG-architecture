# ADR 0002: Standardized agentic-context architecture

- **Date:** 2026-07-24
- **Status:** Accepted

## Context

The `ohwm2/dev` proof of concept demonstrates valuable separation among plans, design, schemas, decisions, reusable instructions, and session history, but its naming and transcript-heavy continuity model are not yet an organization standard. Agents need concise entry points and durable, role-specific context without loading every artifact.

## Decision

Participating repositories should gradually adopt:

- a concise root `AGENTS.md` that routes context conditionally;
- standardized plural `/dev` directories for goals, architecture, decisions, governance, workflows, schemas, features, and checkpoints as applicable;
- distinct artifact roles and lifecycle rules;
- generated `/docs` remaining available for `pkgdown` or other published output; and
- incremental migration instead of a mass rewrite.

Repository-local adaptations are permitted and must not be overwritten silently.

## Rationale

Conditional routing reduces irrelevant context, plural stable names avoid churn as collections grow, and explicit artifact roles make durable outcomes discoverable. Incremental adoption limits risk and respects local history.

## Alternatives considered

- **Load all development files for every task.** Rejected due to noise and conflicting scopes.
- **Use only one large context document.** Rejected because plans, decisions, contracts, and current state have different authority and lifecycles.
- **Mass-migrate every repository immediately.** Rejected because local structures require inventory, crosswalk, and approval.
- **Use `/docs` for internal context.** Rejected because R repositories may reserve `/docs` for generated `pkgdown` output.

## Consequences

Each adopting repository needs a content inventory, authority review, crosswalk, and local validation. Empty standard directories are allowed when their README defines the role. The standard can evolve, but migration tooling must preserve local content by default.

## Verification

Validate root routing, directory names, defining READMEs, links, artifact role separation, and repository-specific checks after each adoption.

## Follow-up

Version the standard before automated multi-repository rollout and evaluate reusable generic scaffolding for `reproducibleai`.
