# ADR-0004: Folder-based spatial deliverables with external GeoTIFF terrain

- Status: accepted migration design, directed by the user; implementation and
  cross-client qualification remain pending.
- Date: 2026-09-07
- Reaffirmed by the user: 2026-09-08, after the two-computer qualification experiment.
- Scope: new open-source workflows and prepared archive candidates; no automatic
  conversion of production ArcGIS projects or customer applications.

## Evidence and its limits

**Verified documentation:** Esri GeoPackage support is selective. ArcGIS Pro
documents raster-pyramid creation and raster-layer access, so a claim that all
Esri clients cannot access any GeoPackage raster is too broad.
[Raster creation](https://pro.arcgis.com/en/pro-app/latest/tool-reference/conversion/add-raster-to-geopackage.htm),
[raster access](https://pro.arcgis.com/en/pro-app/3.3/tool-reference/data-management/make-raster-layer.htm).

OGC distinguishes numerical terrain coverage from ordinary image tiles. Its
gridded-coverage extension carries analytical values and their interpretation.
Successful image display therefore does not demonstrate faithful DEM/REM access.
[OGC coverage guidance](https://www.geopackage.org/guidance/extensions/tiled_gridded_coverage_data.html).

Esri's documentation inspected on this date identifies ArcGIS Pro 3.7 and lists
supported GeoPackage extensions without listing tiled gridded coverage. It also
states that Pro does not read GeoPackage metadata-extension entries and that
publishing hosted layers does not preserve those entries. This is a specific
metadata interoperability limitation even when vectors display successfully.
[Esri support matrix](https://pro.arcgis.com/en/pro-app/latest/help/data/databases/database-requirements-sqlite.htm).

**Unknown:** analytical coverage support outside the tested ArcGIS Pro 3.6 paths,
and future vendor support. The matrix omission is not a local runtime test or
proof of universal raster non-support. Vendor motives and predictions of
permanent non-support are not established engineering facts.

**Planning constraint:** do not depend on Esri reading scientific GeoPackage
terrain, or on future vendor changes. The user's operational experience and
the documented differences are sufficient reason to select a portable boundary.

## Decision

### Experimental confirmation and human acceptance (2026-09-08)

**Verified:** [FGDB's completed analysis](../../../FGDB/dev/experiments/geopackage-raster/FINAL-FINDINGS.md)
(analysis commit `df01025`, returned evidence `9181522`) demonstrates exact
numerical reading of nine supplied GeoPackages in ArcGIS Pro 3.6. Its tested
`AddRasterToGeoPackage` creation path converted all ten terrain rasters to Byte
PNG tiles with changed values and NoData masks. The report separately qualifies
provisional CRS false failures, unresolved `CopyRaster` paths and one changed
auxiliary-file checksum; it does not certify unrestricted round-trip equivalence.

**Accepted decision:** the user accepted this evidence and reaffirmed the folder
design below. GeoPackage is not the required analytical-raster interchange
container. Qualified numerical GeoPackage reading may remain useful, but it must
not substitute for the terrain delivery contract. Further broad GeoPackage/File
GDB equivalence testing is not a prerequisite for migration development.

**Next implementation boundary:** define and qualify the folder manifest and
shared artifact resolver, including metadata conflicts, missing dependencies and
relocation. Storage direction is decided; exact bindings and complete cross-client
folder qualification remain unfinished. Do not weaken CRS, value, NoData or unit
checks to accommodate the failed writer.

### Accepted storage boundary

The local **Reach–Survey–Event delivery unit is a folder**, not one geodatabase
or one GeoPackage. Use qualified **GeoPackages for vectors and related tables**,
**GeoTIFF files for analytical rasters**, and versioned metadata linking all
artifacts to their scientific context. COG is an optional qualified GeoTIFF
layout, not a substitute for fidelity checks. Keep reports as ordinary documents.

This refines FGDB ADR-0024: GeoPackage is not the terrain payload container for
this migration. Earlier GDAL-only raster-GeoPackage experiments remain evidence
about those paths, not the selected interoperable delivery design. Preserve all
original File GDB archives and their metadata as evidence.

Physical separation must not sever logical ownership. Retain embedded raster
georeferencing and explicit metadata for identity, parentage, provenance,
horizontal/vertical references, units, grid, values/NoData and integrity. Do not
infer identity from filenames, or a vertical datum from a horizontal EPSG code.
Use [FGDB's package requirements](../../../FGDB/dev/schemas/local-project-folder-requirements.md)
to frame the versioned storage binding; these are requirements, not implemented APIs.

## Responsibility and rollout

- FGDB owns governed identity/ingestion contracts and the folder-to-enterprise
  crosswalk; enterprise mosaic storage is unchanged by this decision.
- fluvgeo owns reusable export, metadata validation and report assessment.
- fg-qgis-toolbox and ohwm2 consume those shared checks, presenting failures and
  human decisions without separate scientific interpretations.
- fluvgeodata retains legacy fixtures and adds separately qualified folder cases.
- FluvialGeomorph-toolbox preserves its production contract; any future exchange
  adapter consumes the qualified folder profile, not assumed raster GPKGs.
- FG-Tech-Manual and FG-User-Manual distinguish the historical single-GDB model
  and production instructions from this developing target.

Each affected repository records its adoption locally. No generic reproducibleai
template change, downstream customer synchronization, package release, data
conversion or deployment is authorized by this documentation update.
