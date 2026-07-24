# Project goals

## Goals

1. Provide a concise, evidence-classified map of the FluvialGeomorph software ecosystem.
2. Catalog repository roles, responsibilities, dependencies, consumers, publication targets, and authoritative capabilities.
3. Make organization-level capability ownership and authority boundaries explicit.
4. Define a standard agentic-context architecture that member repositories can adopt incrementally.
5. Govern durable context, ADRs, workflows, schemas, feature design, checkpoints, and cross-repository work.
6. Serve as a proof of concept for potential reusable scaffolding in `MVR-GIS/reproducibleai`.
7. Support authoritative, reproducible scientific and engineering software without claiming that architecture documentation itself establishes scientific validity.

## Non-goals

`FG-architecture` is not a monorepo, implementation repository, replacement for repo-local documentation, project-management system, release registry, or archive of full AI conversations. It does not centralize member-repository source code, tests, release state, or deployment configuration.

## Success conditions for version 0.1

- Every repository in the scoped workspace has a catalog entry grounded in repository evidence.
- Durable artifacts have distinct roles, documented precedence, lifecycle rules, and routing.
- Cross-repository work has an approval-aware workflow.
- Member adoption can proceed incrementally without changing application behavior or overwriting local customizations.
- Scientific assumptions and validation evidence remain near the implementing capability and under human acceptance authority.
