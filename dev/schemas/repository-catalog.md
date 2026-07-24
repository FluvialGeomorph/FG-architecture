# Repository catalog schema

## Contract

`repositories.yml` is UTF-8 YAML with this top-level shape:

```yaml
schema_version: "0.1"
repositories: []
```

`schema_version` is a required quoted string. `repositories` is a required sequence with exactly one entry per cataloged repository. Repository `name` values are unique.

## Repository entry

| Field | Type | Required | Rules |
|---|---|---:|---|
| `name` | string | yes | Stable repository name |
| `github_url` | HTTPS URL string | yes | Canonical repository URL; no local path |
| `functional_role` | string | yes | One concise organization role |
| `primary_language_or_technology` | string | yes | Primary implementation or publishing stack |
| `lifecycle_status` | string | yes | Stable declared status, not sprint state |
| `responsibilities` | sequence of strings | yes | Non-empty owned responsibilities |
| `upstream_dependencies` | sequence of strings | yes | Repository or material external dependencies; empty allowed |
| `downstream_consumers` | sequence of strings | yes | Known repositories or consumer classes; empty allowed |
| `publication_or_deployment_target` | string | yes | Stable target or explicit unknown |
| `authoritative_capabilities` | sequence of strings | yes | Non-empty capabilities for which this repository is authoritative |
| `documentation_locations` | sequence of strings | yes | Repository-relative paths or safe public URLs |
| `evidence` | mapping | yes | Classification and sources, defined below |
| `open_questions` | sequence of strings | yes | Empty allowed; questions require human confirmation |

`evidence` has:

| Field | Type | Rules |
|---|---|---|
| `classification` | string | Exactly `verified`, `inferred`, or `unknown` |
| `sources` | sequence of strings | Non-empty safe repository-relative descriptions; no local absolute paths |

## Semantics

- `upstream_dependencies` includes runtime, test-data, or material documentation inputs when supported by evidence. Explain nuanced relation types in the dependency map.
- `downstream_consumers` does not imply version compatibility or deployment state.
- `lifecycle_status` must not contain an active branch, temporary sprint state, or unverified release claim.
- `authoritative_capabilities` records repository-level ownership, not scientific acceptance.
- Uncertain facts remain in `open_questions` or use an explicit unknown value; they are not silently inferred.

## Prohibited content

Do not include local absolute paths, active branch names, credentials, tokens, temporary task state, personal data, secrets, or unsupported assumptions.

## Validation

Parse as YAML; check every required key and type; check name uniqueness, allowed classifications, HTTPS GitHub URLs, absence of prohibited local paths and secret-like fields, and consistency with the dependency and ownership maps.
