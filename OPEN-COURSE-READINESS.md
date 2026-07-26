# Open-Course Readiness

Snapshot date: 2026-07-26

This document records the current readiness of this repository for use by independent learners. It is an inventory and dependency audit, not a claim that the repository is already a self-contained open course.

The machine-readable snapshot is in [open-course-dependency-manifest.json](open-course-dependency-manifest.json).

## Current Position

The repository currently functions as a multi-institution teaching-material index with offering-specific delivery content. It is not yet independent of SIT742 or current partner-university delivery.

Key evidence:

- 47 tracked files: 25 Markdown files, 21 images, and one `.gitignore`;
- no locally tracked practical notebooks;
- no repository licence or content-licence notice;
- the root learning map links to 25 practical notebooks on the SIT742 `develop` branch;
- 51 SIT742 URL occurrences appear across 11 Markdown files;
- 24 handout-link occurrences point to 21 distinct resources in a separate repository;
- four Deakin Zoom recording links remain in M02;
- an active USTB 2026 assessment page depends on three SIT742 2026 Assignment 2 resources;
- 24 of 25 Markdown files contain at least one institution, partner, or SIT742 marker.

All 77 repository-local Markdown link targets resolve. External ownership, branch stability, licence, accessibility, and ongoing availability remain separate concerns.

## Module Maturity Map

| Area | Current learning assets | Independent-learning status | Primary dependency or gap |
| --- | --- | --- | --- |
| M01 Induction | Five Markdown pages | Offering-bound | Unit team, logistics, grading model, current assessment, and institution-specific support |
| M02 Python | Eleven Markdown pages and 21 local images | Partial self-study content | Six practical notebooks remain in SIT742; four Deakin Zoom links; stale branch/path references |
| M03 Big Data | One reading/index page | Reference index | Two external handouts and three SIT742 practical notebooks |
| M04 Data Manipulation | One reading/index page | Reference index | Four external handouts and six SIT742 practical notebooks |
| M05 Data Analytics | One reading/index page | Reference index | Five external handouts and five SIT742 practical notebooks |
| M06 Advanced | One module index and one local reading/activity page | Partial reference module | Six external handouts and five SIT742 practical notebooks |
| Assessments | Current index, one active USTB page, and archive index | Offering-bound | Active dates, submission channel, partner rules, and SIT742 2026 A2 |

For an independent course, each module still needs a clear learning purpose, observable outcomes, a coherent sequence, accessible learning resources, practical activities, self-check or feedback guidance, and stable licensing/provenance information.

## Dependency Findings

### SIT742

The root module map depends on 25 SIT742 notebooks:

- M02: 6
- M03: 3
- M04: 6
- M05: 5
- M06: 5

A path-level check found 38 SIT742 file references. Thirty-two resolve on the named branch and six do not:

- one M02 notebook link has a filename-capitalisation mismatch;
- four M02 data URL occurrences use the absent `master` branch;
- the USTB assessment links to a retired A2 MASE guide path.

The use of a mutable `develop` branch for the main practical sequence also makes the learning experience dependent on changes made for SIT742 delivery.

### External Handouts and Recordings

The repository links to 21 distinct handouts in another repository. These resources may remain useful, but an independent learning path needs stable versions, accessibility checks, and explicit reuse terms.

Four M02 pages link to Deakin Zoom recordings. Those recordings are institution-hosted dependencies and may have access, privacy, or longevity constraints.

### Assessment

The active USTB 2026 assignment is not a generic open-course project. It includes a dated deadline, an email submission channel, group and filename rules, and a dependency on the current SIT742 A2 specification and starter notebook.

Historical assessment references are already separated under `assessments/archive/`, but their reuse and licensing status still require review.

### Licensing and Provenance

No repository licence file currently defines reuse rights for original code or teaching content. The README also states that some material was collected from external sources. Therefore, repository presence must not be treated as permission to reuse or relicense:

- original teaching prose;
- local images;
- external handouts;
- linked notebooks or datasets;
- assessment materials;
- third-party readings or media.

## Selected Product Direction

The selected direction is a **shared multi-institution delivery hub**.

The repository will support a reusable learning core plus explicit university, unit, and offering layers. Institution-specific assessment, dates, submission rules, and policy references may remain part of the public hub when they are clearly scoped to one offering. Private solutions, marking guides, moderation notes, hidden checks, student work, grades, and identifiable feedback remain outside this public repository.

The existing module and assessment paths remain unchanged by this audit. Later implementation should:

1. define the repository licence and third-party-material boundary;
2. define a common learning core and a standard offering-layer manifest;
3. preserve current module paths initially while adding module-level outcomes and learning sequences;
4. organise university-specific delivery material by institution, unit, and offering;
5. keep one canonical source for every assessment artefact and record versioned dependencies;
6. replace fragile branch and path dependencies with reviewed, stable references;
7. archive superseded offerings without presenting them as current requirements;
8. run accessibility, link, provenance, release-boundary, and offering-isolation checks.
