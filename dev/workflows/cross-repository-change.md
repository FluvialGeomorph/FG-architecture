# Cross-repository change

1. Begin with `FG-architecture`: read goals, architecture, catalog, applicable ADRs, schemas, and feature records.
2. Name every repository in scope and confirm authorization to modify each one.
3. Inspect each repository's instructions, Git state, implementation, tests, documentation, and release/deployment constraints.
4. Build an evidence table of affected capability owners, interfaces, consumers, uncertainties, and human approvals.
5. Assign the contract change to its owning repository; avoid silent client reimplementation.
6. Propose sequencing, compatibility, rollback, and verification per repository.
7. Obtain human approval for consequential boundary, schema, scientific, release, or deployment choices.
8. Implement in small reviewable changes, preserving unrelated local work.
9. Verify producer contracts before consumers, then run each repository's checks and cross-repository integration checks.
10. Promote durable outcomes in each owning repository and update the organization catalog/architecture if relationships changed.
11. Confirm Git diffs match the authorized repository set.
12. Record a checkpoint only for meaningful unfinished work.

Never treat write access to one repository as authorization to change another.
