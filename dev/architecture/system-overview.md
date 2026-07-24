# System overview

## Ecosystem

FluvialGeomorph is a set of independently versioned repositories:

- `RegionalCurve` owns regional hydraulic geometry data and related R calculations.
- `fluvgeodata` owns packaged fixtures used to test `fluvgeo`.
- `fluvgeo` owns shared R-side fluvial geomorphic calculations, geospatial contracts, plots, and reports.
- `FluvialGeomorph-toolbox` owns ArcGIS/Python orchestration and calls `fluvgeo` for many calculations and reports.
- `ohwm2` owns an interactive Shiny workflow and imports `fluvgeo`.
- `FG-User-Manual` owns user procedures and report-review guidance.
- `FG-Tech-Manual` owns technical methods and system reference material.
- `FG-architecture` owns organization-level roles, relationships, and context governance.

These statements are `verified` by repository metadata, code calls, and maintained documentation listed in [the catalog](../../repositories.yml). Exact scientific approval ownership and the current hosted target for `ohwm2` remain `unknown`.

## Runtime and publication view

```text
RegionalCurve ──> fluvgeo <── fluvgeodata (test fixtures)
                     │
                     ├──> FluvialGeomorph-toolbox ──> desktop ArcGIS users
                     └──> ohwm2 ──> Shiny application users

FG-User-Manual ──> user procedures
FG-Tech-Manual ──> methods and technical reference
FG-architecture ──> organization context for maintainers and cross-repo work
```

The arrows represent documented dependency or consumption, not source-code ownership transfer.

## Scientific quality boundary

Scientific algorithms require explicit ownership in the implementing repository. Assumptions, units, coordinate systems, datums, valid domains, literature references, and validation evidence belong near that capability. Clients must call the owning implementation or explicitly document an authorized divergence; they must not silently reimplement or reinterpret backend calculations.

Codex may inspect evidence and run verification. Tests establish defined software behavior. Scientific acceptance and any required engineering approval remain human responsibilities. This repository maps those responsibilities but does not itself validate scientific correctness.
