# Milestone 0 — feasibility and provenance audit

Status: **COMPLETE — static/read-only audit, 2026-10-15.**

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

## Findings at a glance

- Overall technical verdict: **CONDITIONAL**.
- Covet baseline: stock wheelbase `2.500 m`; body-mesh AABB `1.674 m` wide by `3.693 m` long by `1.147 m` vertical; B-pillar-adjacent cut/join region is geometrically credible but structurally dense.
- Base rear suspension recommendation: vanilla Lansdale FWD beam axle with heavy-duty spring/shock behavior, adapted to project-owned mounts and verified under load.
- Preliminary Campette mass envelope: `1570–2290 kg`, with `1900 kg` as a calculation/test point only. Nothing in this audit establishes GVWR, payload or axle capacity.
- AWD: vanilla Lansdale architecture makes it technically plausible, but packaging and ratios are unverified and implementation is deferred.
- Critical non-mechanical gate: approve a provenance-safe local/private/permission route for the cut vanilla Covet body before Milestone 1.
- BeamNG was not launched. All runtime, handling, crash, thermal and deployment statuses remain **NOT TESTED**.

## Navigation

- [Environment inventory](environment-inventory.md)
- [Covet geometry and JBeam](covet-geometry-and-jbeam.md)
- [Rear suspension options](rear-suspension-options.md)
- [Mass and handling](mass-and-handling.md)
- [AWD feasibility](awd-feasibility.md)
- [Asset provenance](asset-provenance.md)
- [Feasibility verdict and risk register](feasibility-verdict.md)
- [Proposed Milestone 1](proposed-milestone-1.md)

## Method completed

1. Inventory Git, Python, Blender, BeamNG, its user folder, and active mods location without installing or launching anything.
2. Identify the exact installed Covet source version and inspect its geometry/JBeam/configuration references read-only.
3. Inspect vanilla rear-suspension and driven-rear candidates and compare static compatibility.
4. Evaluate camper packaging, structural load paths, the walkthrough, preliminary masses, axle loads, CG, and vehicle-dynamics risks.
5. Recorded provenance and redistribution limits, graded each requirement, and proposed the smallest production-intent first playable milestone.

No mesh, JBeam, material, configuration, mechanic, game file, mod asset, ZIP or release was created or modified. No dependency was installed, no third-party content was downloaded, and no deployment occurred.
