# Review context health

Perform periodically and before standard-version changes.

1. Validate required directories, defining READMEs, templates, and internal links.
2. Compare `repositories.yml` with current member metadata and safe source evidence.
3. Review `unknown` and `inferred` claims; promote only when evidence supports it.
4. Check for conflicting authority, duplicated content, and current-state claims trapped only in ADRs or checkpoints.
5. Confirm schemas match maintained examples and workflows.
6. Find stale current checkpoints; archive or remove those without active resumable value.
7. Scan context files for secrets, PII, sensitive paths, large logs, or transcript-like content.
8. Review member adoption declarations and intentional deviations without overwriting customizations.
9. Record consequential standard changes in a new ADR and version the standard before automated rollout.
10. Run repository validation and report unresolved drift to human maintainers.
