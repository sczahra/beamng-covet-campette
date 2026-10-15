# Feasibility verdict

## Overall verdict: CONDITIONAL

The Campette is technically plausible as a BeamNG mod, and no inspected geometry creates an absolute blocker. The recognizable Covet cab can be retained; a B-pillar-adjacent coach join, real opening, wider rounded shell, overcab berth and load-bearing vanilla-derived rear suspension all have credible static strategies. It is not ready for unqualified implementation because gross mass/CG, clear passage dimensions, owner-selected exterior envelope, donor mounting geometry, runtime behavior and the public-repository treatment of a cut vanilla body remain unresolved.

## Requirement matrix

| Critical requirement | Verdict | Evidence | Confidence | Blocker / next proof |
|---|---|---|---|---|
| Recognizable vanilla Covet hood, fascia, windshield, doors, dash and FWD front | **PASS** for geometric retention | Exact vanilla slots and body/door AABBs inspected | High | Derived-body provenance must be resolved before public implementation |
| Original rounded Shasta-inspired coach, not replica | **CONDITIONAL** | No donor is required; original geometry is allowed in principle | Medium | Owner must freeze width/length/profile and later approve modeling milestone |
| Coach wider/taller than cab | **CONDITIONAL** | Covet body width measured at 1.674 m; roof max 1.329 m in body mesh | High for baseline, low for final envelope | No approved coach width/height |
| Real cab-to-living walkthrough | **CONDITIONAL** | B-pillar structural span 1.314 m; floor-to-roof node proxy ~1.0 m | Medium | Clear trim/seat opening and step/headroom must be measured; ring structure required |
| Overcab berth | **CONDITIONAL** | Roof/header nodes identified; load can return to B-pillar/coach ring | Medium | Berth dimensions, sightline/head clearance and support geometry unknown |
| Side entry and camper windows | **CONDITIONAL** | Original framed apertures are structurally feasible | Medium | Side/handing/layout and shear-frame design not fixed |
| Small rear-corner wings | **PASS** conceptually / **CONDITIONAL** structurally | Lightweight appendages do not control packaging | Medium | Must use low mass, controlled breakgroups and avoid hazardous collision spikes |
| Swooping integrated single-rear-wheel arches | **CONDITIONAL** | Lansdale ~1.60 m hub track suits wider coach; single-wheel options exist | Medium-high | Tire size and articulated envelope not selected/tested |
| Credible floor/chassis and JBeam continuity | **CONDITIONAL** | Specific Covet B-pillar/floor/roof nodes and donor mount patterns identified | Medium | New rails/ring/cradle must be designed and deformed in game |
| Load-bearing rear suspension | **CONDITIONAL** | Lansdale FWD beam with heavy springs/shocks is leading vanilla candidate; native cargo config 1650 kg | Medium | No axle rating, Campette mount test, ride-height or payload test |
| FWD drivability | **CONDITIONAL** | Parametric cases retain 45–59% static front load | Medium-low | Actual mass/CG, traction, front capacity, cooling and braking unknown |
| Braking and stability | **CONDITIONAL** | Required energy is estimated at 1.55–2.27× base Covet; larger vanilla brakes exist | Medium | Bias, fade, ABS, rollover/crosswind tests absent |
| Optional AWD | **CONDITIONAL / DEFER** | Complete Lansdale split-shaft AWD chain inspected; Covet has modular transfercase input | Medium | Floor corridor, rear driven package, ratio and owner authorization absent |
| Public provenance and distributability | **BLOCKED pending decision** | Project rules forbid committing copied/derived proprietary content without permission | High | Select approved local-build/private/permission route before derived Covet mesh work |

## Compact risk register

| Priority | Risk | Likelihood / impact | Mitigation / decision gate |
|---:|---|---|---|
| 1 | Public repo cannot contain the cut vanilla body needed for the literal Covet front | High / critical | Approve a local-only build pipeline, private artifact policy, or verified permission before Milestone 1 |
| 2 | Unknown gross/axle loads overload Covet front or donor rear mounts | High / critical | Freeze mass targets; instrument node mass and axle loads early; no payload claim until tested |
| 3 | Walkthrough and side door remove torsional/shear paths | High / high | Perimeter ring, twin rails, roof/header and framed apertures; deformation tests |
| 4 | High/rearward CG causes rollover, understeer or FWD traction loss | Medium-high / high | Low/forward tanks/battery, wider rear track, load placement and dynamic tests |
| 5 | Rear donor geometry conflicts with floor/wheel arches | Medium / high | Freeze wheelbase/tire/envelope; full bump/droop checks before detail modeling |
| 6 | Covet brakes/cooling/powertrain are inadequate at sustained gross mass | Medium-high / high | Production-intent vanilla upgrades only after measured thermal/brake tests |
| 7 | AWD tunnel conflicts with passage/interior and adds failure modes | High / medium | Preserve optional corridor but defer implementation until FWD package is stable |
| 8 | Visual/JBeam mismatch or rigid join causes unstable crash behavior | Medium / high | Align nodes/triangles/flexbody groups; progressive collision and deformation test matrix |

## Prioritized unresolved questions

1. Which provenance route may Milestone 1 use for the required cut/derived vanilla Covet body?
2. What owner-approved exterior width, overall length, wheelbase/rear overhang and entry-door side define the Campette?
3. What target curb mass, occupant count, payload and fluid capacities should drive axle selection?
4. Is the FWD Milestone 1 powertrain the vanilla 1.5 GTz Turbo path or another explicitly selected Covet configuration?
5. What minimum clear walkthrough width/height and bunk dimensions are acceptable?
6. Does the owner approve the Lansdale FWD beam/heavy spring/shock strategy for the next milestone?
7. What in-game test session may the owner manually launch, and what constitutes pass/fail for ride height, braking and stability?

## Test status

- Static source/provenance/geometry checks: **PASSED for Milestone 0**.
- Documentation arithmetic and path/identifier review: **PASSED**, subject to final repository validation.
- BeamNG launch, spawn, node debug, suspension travel, weight-pad, deformation, crash, driving, thermal and deployment checks: **NOT TESTED**.

