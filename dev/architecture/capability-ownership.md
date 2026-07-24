# Capability ownership

| Capability | Owning repository | Evidence | Confidence |
|---|---|---|---|
| Organization architecture and context standard | `FG-architecture` | ADR 0001 and repository purpose | verified |
| Regional hydraulic geometry data and calculations | `RegionalCurve` | package DESCRIPTION, functions, and vignettes | verified |
| Shared R fluvial-geomorphology calculations | `fluvgeo` | package DESCRIPTION, exports, and consumers | verified |
| Test fixtures for `fluvgeo` | `fluvgeodata` | both package DESCRIPTION files | verified |
| ArcGIS geoprocessing orchestration | `FluvialGeomorph-toolbox` | toolbox source and README | verified |
| OHWM Shiny UI and reactive orchestration | `ohwm2` | DESCRIPTION, app source, and design docs | verified |
| User procedures | `FG-User-Manual` | Quarto configuration and chapter set | verified |
| Technical methods and reference | `FG-Tech-Manual` | README, Quarto configuration, and chapters | verified |

Ownership means authority to define and verify the capability in that repository. Consumers may integrate it but should not silently duplicate or reinterpret it.

## Scientific records

For each scientific algorithm, the owning repository should maintain:

- assumptions and valid domain;
- input/output units;
- coordinate systems and datums where spatial behavior depends on them;
- references and derivation;
- validation evidence and known limitations; and
- named human review or approval responsibility where required.

The organization catalog currently establishes repository-level ownership only. Function-level scientific ownership is `unknown` and requires human confirmation before automated enforcement.
