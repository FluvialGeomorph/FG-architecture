# FluvialGeomorph architecture

`FG-architecture` is the organization-level map and agentic-context standard for the independently versioned FluvialGeomorph repositories. Version 0.1 establishes:

- a stable, evidence-classified [repository catalog](repositories.yml);
- the current [system overview](dev/architecture/system-overview.md), [dependency map](dev/architecture/dependency-map.md), and [capability ownership](dev/architecture/capability-ownership.md);
- an [agentic-context model](dev/architecture/agentic-context-model.md);
- governance for decisions, workflows, schemas, features, and checkpoints; and
- an incremental [adoption policy](dev/governance/adoption-policy.md).

This repository is not a monorepo and does not replace member-repository documentation or implementation authority. Begin cross-repository work here, then inspect each repository's current instructions, Git state, code, tests, and documentation.

For the current terrain/reporting and open-source migration work, start with
[the project-level orientation](dev/architecture/system-overview.md#open-source-migration-why-the-pieces-fit-together).
It explains the intended outcome, separates storage testing from QGIS/R execution
testing, and routes to each owner's current plan. Installation diagnostics are
supporting evidence, not the project goal.

The accepted [open-source storage decision](dev/decisions/adr-0004-folder-based-spatial-deliverables.md),
reaffirmed after cross-client testing on 2026-09-08, uses Reach–Survey–Event
folders with GeoPackage vectors/tables, GeoTIFF terrain and linked metadata.
This is a migration design, not a replacement of deployed ArcGIS procedures.

## Evidence labels

- `verified`: directly supported by repository code, metadata, configuration, or maintained documentation.
- `inferred`: supported indirectly but not conclusively.
- `unknown`: needs human confirmation.

See [project goals](dev/goals/project-goals.md) for scope and non-goals, and [the dev guide](dev/README.md) for the durable artifact map.
