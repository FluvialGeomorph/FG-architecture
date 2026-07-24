# Dependency map

## Verified software dependencies

| Consumer | Upstream | Evidence | Classification |
|---|---|---|---|
| `fluvgeo` | `RegionalCurve` | `DESCRIPTION` Imports/Remotes and `R/stream_power.R` calls | verified |
| `fluvgeo` | `fluvgeodata` | `DESCRIPTION` Suggests/Remotes; described as test data | verified |
| `FluvialGeomorph-toolbox` | `fluvgeo` | install script plus direct calls throughout R tools and reports | verified |
| `FluvialGeomorph-toolbox` | `RegionalCurve` | install and region-update scripts | verified |
| `ohwm2` | `fluvgeo` | `DESCRIPTION` Imports/Remotes and app design docs | verified |

`fluvgeodata` is an optional package dependency in R metadata but a test-data dependency by declared role. That distinction should remain visible.

## Verified documentation relationships

- `FG-User-Manual` documents toolbox installation, workflows, and report review.
- `FG-Tech-Manual` documents toolbox methods, features, dependencies, `fluvgeo`, `RegionalCurve`, and rapid-assessment tools.
- Technical manual content links to user procedures for operational steps.

Documentation relationships are not runtime dependencies and do not transfer implementation authority.

## External dependencies

The toolbox documentation requires Windows, ArcGIS Pro, and R. `ohwm2` is a golem/Shiny R package and its code supports rsconnect deployment. Exact external service inventories, deployment accounts, and credentials are intentionally outside this repository.

## Unknowns to resolve

- The exact supported production target and URL for `ohwm2`.
- Whether all toolbox-to-`RegionalCurve` use should remain direct or flow exclusively through `fluvgeo`.
- Which cross-repository data contracts are stable enough to document as organization schemas.
