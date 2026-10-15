# Progress and resumption state

Status: **Milestone 0 read-only feasibility audit complete 2026-10-15; no technical implementation started.**

## Completed Milestone 0 — 2026-10-15
- Authorization: explicit owner approval in the initiating task; recorded as D-012.
- Starting repository state: branch `main`, commit `a0ff7e30c12b363b606d893723707d5e158322c4`, clean working tree after cloning the owner-specified repository into the empty workspace.
- Scope boundary: project-owned documentation and Git history only. BeamNG/game/mod content remains read-only; no modeling, JBeam/material/configuration/mechanical changes, deployment, release, dependency installation, or automatic game launch.
- Planned evidence: installed tool/version/path status; BeamNG version, user folder and active mods path; exact vanilla Covet and candidate donor paths and identifiers; defensible static measurements; packaging/load-path analysis; bounded mass/handling calculations; AWD options/blockers; provenance; per-requirement verdicts; and a decision-ready proposed Milestone 1.
- Evidence labels: verified local fact, static-derived result, estimate, hypothesis, unknown, and in-game status are kept distinct.
- Documentation checkpoint: `ee22dae` (`docs: checkpoint milestone 0 feasibility evidence`). Final validated commit recorded in the completion report.
- Environment: BeamNG 0.39.4.0.20972/build 20972, Git 2.54.0, Python 3.12.6 and Blender 4.5.3 LTS were found and inspected without installation or game launch. The Documents mods folder is observed but not confirmed active by a current runtime log.
- Measured/derived baseline: Covet 2.500 m stock wheelbase; body-mesh AABB 1.674 m wide × 3.693 m longitudinal × 1.147 m vertical; B-pillar/cut landmarks and rear mount identifiers documented.
- Rear suspension: Lansdale FWD beam axle with heavy springs/shocks is the preferred base reference; H-Series is a load-bearing reference but rejected for base FWD; stock Covet rear is not accepted without comprehensive capacity proof.
- Mass: 1570–2290 kg preliminary uncertainty envelope and 1900 kg nominal calculation point; no payload/GVWR/axle rating established.
- AWD: technically plausible using the Lansdale split-shaft/independent-rear pattern; packaging unverified and implementation deferred.
- Overall verdict: CONDITIONAL. Critical gates are provenance route, owner-frozen dimensions/mass targets, donor approval, and later owner-launched in-game validation.
- Static documentation status: passed final checks. In-game, deployment and release status: NOT TESTED / NOT PERFORMED.

## Confirmed
- Repository: https://github.com/sczahra/beamng-covet-campette
- Default branch: `main`.
- Owner approved guided autonomy, guarded asset sourcing, frequent checkpoints, commits at validated milestones, and validated automatic ZIP deployment with rollback (never launch BeamNG).
- Vehicle concept approved: Ibishu Covet front with an original Shasta-inspired canned-ham baby Class C, continuous walkthrough, overcab bunk, integrated swoopy single rear wheel openings, signature rear wings, reinforced rear suspension, FWD base and possible AWD upgrade.

## Not done
- No BeamNG installation, tools, versions, mods folder, local assets or candidate JBeam donors inspected.
- No geometry, JBeam, vehicle mod, ZIP, testing or deployments completed.
- No dimensions, rear suspension donor, AWD design or payload capacity verified.

## Next action / authorization gate
Stop after Milestone 0. Request separate explicit owner approval for the proposed Milestone 1 scope in `milestone-0/proposed-milestone-1.md`, including the provenance route, dimensions/mass targets, Lansdale beam-axle decision, FWD powertrain baseline and owner-launched test permission. Do not modify vehicle files before that approval.

## Milestone reporting format
- Milestone, date, owner authorization:
- Version, branch and commit:
- Changes and exact asset provenance:
- Static validation vs in-game validation:
- Deployment and rollback path:
- Confirmed results, uncertainty, blockers:
- Restart steps and next approval gate:
