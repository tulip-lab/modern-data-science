# Offering Layers

Offering layers contain public university-, unit-, and teaching-period-specific delivery information built on the reusable Modern Data Science common core.

Target path:

```text
offerings/<institution>/<unit>/<offering>/
```

Each offering must:

- include a manifest conforming to [offering-manifest.schema.json](offering-manifest.schema.json);
- identify the common-core commit or release it uses;
- identify its institution, unit, teaching period, and status;
- list public assessment artefacts and their canonical sources;
- link to current institution-approved policy sources;
- exclude private assessment and student materials.

## Current Offerings

- [USTB Modern Data Science 2026](ustb/modern-data-science/2026/README.md)

The previous `assessments/2026/ustb/` assignment path remains as a compatibility pointer to the canonical offering-layer page.

See [HUB-GOVERNANCE.md](../HUB-GOVERNANCE.md) for public/private boundaries and release requirements.
