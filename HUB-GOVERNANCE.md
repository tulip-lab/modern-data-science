# Shared Multi-Institution Delivery Hub Governance

## Product Identity

This repository is a shared delivery hub for Modern Data Science learning materials used across multiple universities and offerings.

It has two public layers:

1. **Common core** — reusable module content, learning outcomes, activities, and references.
2. **Offering layers** — university-, unit-, and teaching-period-specific delivery and assessment information.

The current module paths remain the common-core candidates until a reviewed migration decision is implemented.

## Common-Core Rules

Common-core material should:

- use institution-neutral learning language;
- state observable learning outcomes;
- provide a coherent sequence of learning and practical activities;
- use stable, public, and appropriately licensed dependencies;
- include accessibility and independent-execution guidance;
- avoid current dates, submission systems, university policy wording, and active assessment instructions.

The current common-core definition and maturity status are recorded in [common-core-manifest.json](common-core-manifest.json).

## Offering-Layer Rules

Each offering should be scoped by institution, unit, and offering identifier. The target pattern is:

```text
offerings/<institution>/<unit>/<offering>/
```

Every offering must include a manifest conforming to [offerings/offering-manifest.schema.json](offerings/offering-manifest.schema.json).

An offering layer may contain:

- public delivery navigation;
- public assessment briefs and starter materials;
- dates, group rules, filenames, and submission instructions;
- links to the institution's current policy sources;
- a versioned dependency on the common core.

It must not contain:

- solutions or expected answers;
- marking guides or moderation notes;
- hidden tests or private evaluation thresholds;
- student submissions, grades, or identifiable feedback;
- credentials, private links, or restricted data.

## Canonical-Source Rule

Every public assessment artefact must have one editable canonical source. An offering manifest may reference or record a reviewed release from another public repository, but it must not create a second independently edited copy.

SIT742 assessment artefacts remain canonical in the public SIT742 repository, with private support retained outside this public hub.

## Status and Archive Rules

Offering status must be one of:

- `planned`
- `active`
- `superseded`
- `archived`

Only one offering page should be presented as current for the same institution, unit, and teaching period. Superseded or archived material must carry a prominent warning and must not be presented as current instructions.

## Release Gate

Before publishing or updating an offering:

1. validate its manifest;
2. verify every public artefact and canonical source;
3. confirm policy links and dates with the relevant institution;
4. scan for private materials and student information;
5. verify licensing, provenance, accessibility, and links;
6. record the common-core version used by the offering.
