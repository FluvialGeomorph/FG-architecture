# Adoption policy

## Controlled rollout

```text
canonical standard
    -> FG adoption policy
        -> member-repository adoption
            -> validation and review
```

The eventual `reproducibleai` standard may distribute general reusable scaffolding, templates, validation, and skills. `FG-architecture` owns FluvialGeomorph-specific policy and extensions. Each member repository owns its local implementation and declared adoption.

Adoption is incremental. Inventory and crosswalk existing content before proposing changes. Preserve useful content and Git history where practical. Stop for human approval before applying a migration. Do not change application or package behavior unless separately authorized.

Standards should be versioned before automated multi-repository rollout. This version documents the intended evolution path but does not implement an updater. Historical ADRs are not rewritten solely to match a newer template. Tools must detect and preserve local customizations; they must never overwrite them silently.

## Adoption declaration

A repository is adopted only when its maintainers approve the local structure, its root routing and links validate, repository checks pass or documented exceptions are accepted, and its local record identifies the standard version and intentional deviations. A catalog entry alone does not declare adoption.
