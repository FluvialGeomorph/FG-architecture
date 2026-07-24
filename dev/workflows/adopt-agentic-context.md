# Adopt agentic context

Use this workflow to migrate one member repository. Migration must not alter application or package behavior unless separately authorized.

1. Read the organization context in `FG-architecture`.
2. Inspect the target repository's Git state, applicable instructions, metadata, code structure, tests, documentation, and configuration.
3. Inventory existing context artifacts without assuming current names determine future authority.
4. Classify each item as instruction, durable knowledge, decision, workflow, schema, feature design, active state, or history.
5. Identify duplication, contradictory statements, and conflicting authority.
6. Produce an old-to-new crosswalk that marks preserve, move, consolidate, archive, or leave in place.
7. Propose a concise root `AGENTS.md` with always-on rules and conditional routes.
8. Plan to preserve useful content and Git history where practical; identify local customizations explicitly.
9. Stop for human approval of the crosswalk and proposed target structure.
10. Apply only the approved migration.
11. Validate routing, internal links, required structure, information safeguards, and normal repository checks.
12. Create one current checkpoint only if meaningful work remains unfinished.

Completion requires a declared standard version or explicit partial-adoption status, recorded deviations, and no silent content loss.
