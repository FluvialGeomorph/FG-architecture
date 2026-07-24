# Agent instructions

## Identity and scope

`FG-architecture` is the organization-level context and architecture repository for FluvialGeomorph. It catalogs repository roles, cross-repository relationships, capability ownership, and the agentic-context standard. It is not a monorepo, implementation repository, project-management system, or transcript archive.

## Always-applicable rules

- Inspect current repository and Git evidence before changing architecture records.
- Keep member repositories authoritative for their code, tests, local architecture, releases, and deployment configuration.
- Do not modify a member repository unless that repository is explicitly in scope.
- Keep this file concise; route detailed knowledge into `dev/`.

## Conditional context routes

- Organization scope or goals: `dev/goals/`
- Architecture, dependencies, authority, or ownership: `dev/architecture/`
- Consequential choices: `dev/decisions/`
- Governance or artifact lifecycle: `dev/governance/`
- Repeatable procedures: `dev/workflows/`
- Exact structural contracts: `dev/schemas/`
- Cohesive cross-repository capabilities: `dev/features/`
- Resumable unfinished work: `dev/checkpoints/current/`

Full session transcripts are not normal context sources. Use maintained durable artifacts and concise checkpoints.

## Evidence, uncertainty, and authority

Label claims `verified`, `inferred`, or `unknown`; never present inference as fact. Code and tests evidence actual behavior and can reveal documentation drift, but accepted ADRs govern their decisions and schemas govern exact documented contracts. `FG-architecture` does not automatically govern sibling repositories; cross-repository work must explicitly begin with this organization context. Scientific acceptance and required engineering approval remain human responsibilities.

## Completion governance

Before declaring meaningful work complete, classify whether it changed goals or scope, architecture or capability boundaries, an accepted decision, a schema or interface contract, a repeatable workflow, feature behavior, or active work state. Update the applicable durable artifact first. Create a checkpoint only when useful resumable state remains.

## Verification and information governance

Verify structure and links, validate changed contracts, run proportionate repository checks, review Git status and diff, and confirm the change boundary. Never record credentials, tokens, PII, restricted data, secrets, unsuitable internal details, or large logs containing sensitive paths or data; cite safe evidence instead.
