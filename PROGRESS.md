# Progress and resumption state

Status: **Milestone 1 implementation specification finalized for approval 2026-10-15; no technical implementation started.**

## Milestone 1 approval package — 2026-10-15

- Starting state: branch `main`, commit `0cdbf39cd8a432a7e8c7d9c3fb0ea26e727e6d11`, clean, two local audit commits ahead of `origin/main`.
- Authorization: planning only. No mesh, JBeam, material, configuration, game/mod file, ZIP, deployment or runtime action was authorized or performed.
- Owner direction recorded as D-015: preserve the Covet cab/front/doors/dashboard/character; treat the Lansdale FWD beam as the preferred but conditional rear candidate; do not adopt an entire Lansdale chassis.
- Final proposal: `milestone-1/implementation-specification.md` defines evidence-labeled package targets, structural architecture, FWD mechanical baseline, provenance-safe local build, deliverables, sequence, acceptance tests, risks and the exact next authorization.
- Recommended construction defaults: `2.815 m` nominal wheelbase, `1.95 m` coach width, `4.80 m` overall length, `2.45 m` overall height, `0.60 m` walkthrough width, Lansdale-style beam/rear discs, Covet GTz-turbo-derived FWD baseline and `1900 kg` nominal engineering test point. All non-observed dimensions are explicitly estimates, not measurements.
- Proprietary handling: public Git may contain project-authored source/scripts/docs; extracted or modified vanilla assets and complete derived ZIPs remain local/private unless BeamNG permission is documented.
- Validation for this planning task: documentation consistency, repository privacy/proprietary-content scan and Git diff review. In-game status remains **NOT TESTED**.

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
- No geometry, JBeam, material, configuration, vehicle mod, ZIP, runtime testing or deployment has been created or performed.
- No Campette mass, CG, axle capacity, suspension travel, thermal margin, handling result, payload or GVWR has been measured/approved.
- The active mods directory is not runtime-confirmed; no owner-run BeamNG test session has occurred.
- No permission to publish a modified vanilla Covet mesh has been verified.

## Next action / authorization gate
Stop at the approval gate. Request the exact Milestone 1 authorization stated in `milestone-1/implementation-specification.md`. Do not modify vehicle files before that approval. The next approved task should begin production-intent construction, not another broad feasibility study.

## Milestone reporting format
- Milestone, date, owner authorization:
- Version, branch and commit:
- Changes and exact asset provenance:
- Static validation vs in-game validation:
- Deployment and rollback path:
- Confirmed results, uncertainty, blockers:
- Restart steps and next approval gate:
