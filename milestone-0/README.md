# Milestone 0 — feasibility and provenance audit

Status: **IN PROGRESS — documentation checkpoint, 2026-10-15.**

This directory records the owner-authorized, read-only technical audit for the Ibishu Covet Campette. No vehicle implementation is part of this milestone.

## Starting point

- Repository branch: `main`
- Starting commit: `a0ff7e30c12b363b606d893723707d5e158322c4`
- Starting working tree: clean
- Authorization: explicit owner approval dated 2026-10-15, recorded as D-012 in `../DECISIONS.md`

## Method and evidence labels

The audit uses read-only local filesystem and archive inspection. It will not launch BeamNG, alter game/mod content, install dependencies, or copy proprietary game content into this repository. Public documentation sanitizes private path components.

- **VERIFIED LOCAL:** directly observed in the installed environment.
- **STATIC-DERIVED:** calculated or parsed from observed files without running the game.
- **ESTIMATE:** transparent assumption or range, not a measurement.
- **HYPOTHESIS:** engineering proposal requiring validation.
- **UNKNOWN/BLOCKED:** evidence unavailable or insufficient.
- **IN-GAME NOT TESTED:** no runtime claim; BeamNG is not launched in Milestone 0.

## Planned deliverables

- `environment-inventory.md`
- `covet-geometry-and-jbeam.md`
- `rear-suspension-options.md`
- `mass-and-handling.md`
- `awd-feasibility.md`
- `asset-provenance.md`
- `feasibility-verdict.md`
- `proposed-milestone-1.md`

## Audit plan

1. Inventory Git, Python, Blender, BeamNG, its user folder, and active mods location without installing or launching anything.
2. Identify the exact installed Covet source version and inspect its geometry/JBeam/configuration references read-only.
3. Inspect vanilla rear-suspension and driven-rear candidates and compare static compatibility.
4. Evaluate camper packaging, structural load paths, the walkthrough, preliminary masses, axle loads, CG, and vehicle-dynamics risks.
5. Record provenance and redistribution limits, grade each requirement, propose the smallest production-intent first playable milestone, validate the documentation, and commit it.

Estimated completion time at audit start: **60–90 minutes**, contingent on local asset accessibility and archive size.
