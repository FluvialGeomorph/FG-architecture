# FluvialGeomorph architecture

`FG-architecture` is the organization-level map and agentic-context standard for the independently versioned FluvialGeomorph repositories. Version 0.1 establishes:

- a stable, evidence-classified [repository catalog](repositories.yml);
- the current [system overview](dev/architecture/system-overview.md), [dependency map](dev/architecture/dependency-map.md), and [capability ownership](dev/architecture/capability-ownership.md);
- an [agentic-context model](dev/architecture/agentic-context-model.md);
- governance for decisions, workflows, schemas, features, and checkpoints; and
- an incremental [adoption policy](dev/governance/adoption-policy.md).

This repository is not a monorepo and does not replace member-repository documentation or implementation authority. Begin cross-repository work here, then inspect each repository's current instructions, Git state, code, tests, and documentation.

## Evidence labels

- `verified`: directly supported by repository code, metadata, configuration, or maintained documentation.
- `inferred`: supported indirectly but not conclusively.
- `unknown`: needs human confirmation.

See [project goals](dev/goals/project-goals.md) for scope and non-goals, and [the dev guide](dev/README.md) for the durable artifact map.
