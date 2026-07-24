# ADR 0001: Organization context repository

- **Date:** 2026-07-24
- **Status:** Accepted

## Context

FluvialGeomorph capabilities span independently versioned code, data, application, toolbox, and documentation repositories. Cross-repository work needs a reliable starting map without moving implementation into a single repository or treating informal conversation as architecture.

## Decision

`FG-architecture` owns organization-level repository roles, relationships, capability boundaries, and context governance. Member repositories remain independently versioned and authoritative for their implementations, tests, local architecture, releases, and deployments. This is not a monorepo. Cross-repository work begins with organization context and then inspects each repository's local authority and current evidence.

## Rationale

A small, dedicated context repository provides discoverability and consistent governance while respecting independent release cycles and local implementation ownership.

## Alternatives considered

- **Put organization context in one implementation repository.** Rejected because it would privilege a consumer or backend and blur authority.
- **Create a monorepo.** Rejected because it would change versioning, release, and ownership boundaries without an implementation need.
- **Rely on repository READMEs and chat history.** Rejected because no single maintained map or durable cross-repository decision trail would exist.

## Consequences

Cross-repository claims require evidence and uncertainty labels. Maintainers must keep the catalog aligned with member repositories. Organization documents cannot directly govern or change a sibling repository. Some information will remain linked rather than duplicated.

## Verification

Review the catalog against repository metadata and source evidence; verify member repositories remain independent Git worktrees and that architecture artifacts do not claim implementation authority.

## Follow-up

Resolve catalog open questions with maintainers and adopt repo-local context incrementally.
