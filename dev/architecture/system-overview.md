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

## Local deliverables during open-source migration

The accepted [folder-based delivery decision](../decisions/adr-0004-folder-based-spatial-deliverables.md)
uses GeoPackage vectors/tables, external GeoTIFF terrain and explicit metadata
links within a Reach–Survey–Event folder. It does not rely on analytical raster
GeoPackage interoperability with Esri. FGDB and fg-qgis-toolbox participate in
this developing migration alongside the established backend and clients; this
does not imply deployed integration or replacement of production ArcGIS.

## Open-source migration: why the pieces fit together

**Accepted direction:** make it practical for more analysts to define, describe
and reconstruct a Study Area before Level 1, using shared fluvgeo methods from
QGIS and Shiny. A durable visual report should explain **what is known and what
the analyst needs to do next**. FGDB preparation is one use of this workflow,
not the only reason to build it. Existing ArcGIS production work continues.
See [reporting intent](../../../fluvgeo/dev/goals/reporting-intent.md) and
[the parallel migration decision](../../../fg-qgis-toolbox/dev/decisions/ADR-0001-parallel-open-source-migration.md).

| Part | Contribution to that outcome | Authoritative detail |
| --- | --- | --- |
| fluvgeo | Shared science, network preparation, study assessment and reports. | [Backend plan](../../../fluvgeo/dev/goals/project-plan.md) |
| fg-qgis-toolbox | Thin desktop tools invoking those methods through the R Provider. | [Desktop plan](../../../fg-qgis-toolbox/dev/goals/project-plan.md) |
| ohwm2 / Shiny | Web interaction with the shared backend; selective prompts are the migration target, not a deployed claim. | [Backend/client boundary](../../../fluvgeo/dev/architecture/backend-ecosystem.md) |
| FGDB | Governed identities, relationships and enterprise loading contracts. | [Initiative and current focus](../../../FGDB/dev/goals/initiative-brief.md) |
| fluvgeodata | Retained evidence and representative fixtures; originals remain unchanged. | [Fixture storage direction](../../../fluvgeodata/inst/extdata/README-storage.md) |

Two different experiments support this direction. **Verified, reviewed 2026-09-09:**

| Question | What was established | What it does not establish |
| --- | --- | --- |
| Can one GeoPackage replace the File GDB terrain container across clients? | The tested ArcGIS writer changed numerical terrain into image values. The accepted delivery remains a folder with vector/table GeoPackages, GeoTIFF terrain and linked metadata. [Storage findings](../../../FGDB/dev/experiments/geopackage-raster/FINAL-FINDINGS.md) | Universal raster non-support, or qualification of the complete folder workflow. |
| Can QGIS invoke the same R analysis reliably? | One read-only network report ran through the actual R Provider and agreed with direct R. Inherited spatial settings and a separate QGIS installation conflict were addressed. [Execution findings](../../../fg-qgis-toolbox/dev/features/qgis-provider-qualification.md) | General geometry/raster interchange, complete Study Area reopening, or production readiness. |

The QGIS repair was enabling maintenance, not a new scientific capability or a
reason to reopen the accepted storage decision. **Proposed immediate next step:**
an analyst-run isolated desktop trial of the report tool. **Still unfinished:**
complete saved Study Area/event/shared-terrain binding, broader fixtures and
folder qualification, selective Shiny integration and enterprise loading.
Member plans own task ordering and current implementation status; this overview
maps how the work contributes to the outcome, rather than duplicating task lists.

## Scientific quality boundary

Scientific algorithms require explicit ownership in the implementing repository. Assumptions, units, coordinate systems, datums, valid domains, literature references, and validation evidence belong near that capability. Clients must call the owning implementation or explicitly document an authorized divergence; they must not silently reimplement or reinterpret backend calculations.

Codex may inspect evidence and run verification. Tests establish defined software behavior. Scientific acceptance and any required engineering approval remain human responsibilities. This repository maps those responsibilities but does not itself validate scientific correctness.
