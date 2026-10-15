# Covet geometry, JBeam and camper interface

## Source and version

- BeamNG.drive `0.39.4.0.20972`, build 20972.
- Vanilla archive: `%ProgramFiles(x86)%\Steam\steamapps\common\BeamNG.drive\content\vehicles\covet.zip`.
- Archive SHA-256: `68D369CDDA446DEEAF5BC78C738D7A4E7FB81B8FCF6D3F39AF7C247FA911AD47`.
- Principal inspected members: `vehicles/covet/covet.dae`, `covet.jbeam`, `covet_body.jbeam`, `covet_suspension_F.jbeam`, `covet_suspension_R.jbeam`, `covet_hubs_F.jbeam`, `covet_hubs_R.jbeam`, `covet_brakes.jbeam`, `covet_differential_R.jbeam`, `DX_M.pc`, `info_DX_M.json`, and `info_DXi_M.json`.

All coordinates below are **STATIC-DERIVED** from the installed files. The DAE declares meters and `Z_UP`. In this vehicle coordinate system x is lateral, y increases rearward, and z is upward.

## Verified dimensions and landmarks

| Item | Static result | Evidence / limitation |
|---|---:|---|
| `covet_body` visual-mesh AABB | x `−0.8371..+0.8371`, y `−1.8496..+1.8432`, z `0.1821..1.3293 m` | Parsed from `covet.dae`; body mesh only, not tires/accessories |
| Body-mesh span | `1.6742 m` wide, `3.6927 m` longitudinal, `1.1472 m` vertical | AABB subtraction; not complete vehicle overall dimensions |
| Stock wheel-center planes | front y `−1.25 m`, rear y `+1.25 m`, z `0.288 m` | Hub slot/flexbody offsets |
| Stock wheelbase | `2.500 m` | Difference between the two verified wheel-center planes |
| Stock nominal hub-center track | about `1.420 m` | Hub flexbody centers at x `±0.71 m`; actual tire outer width depends on wheel/tire selection and offset |
| Front-door visual rear edge | y `0.48585 m` | Max y of both `covet_door_L` and `covet_door_R` meshes |
| Rear-quarter visual front edge | y `0.43529 m` | Min y of `covet_quarterpanel`; overlaps the door/B-pillar transition |
| B-pillar upper nodes | `p3r/p3l`: x `±0.657`, y `0.37`, z `1.08 m`; `p4r/p4l`: x `±0.657`, y `0.50`, z `1.08 m` | `covet_body.jbeam` |
| Front-door latch nodes | `q11r/q11l`: x `±0.60`, y `0.42`, z `0.80 m` | `covet_body.jbeam` |
| Roof at B-pillar region | `rf2r/rf2l`: x `±0.52`, y `0.47`, z `1.30 m`; `rf2`: z `1.33 m` | `covet_body.jbeam` |
| Floor near B-pillar | structural nodes `f3*` y `0.42`, z `0.20 m`; interior nodes `fi3*` y `0.424`, z `0.30 m` | `covet_body.jbeam` |
| Existing cab interior height proxy | roughly `1.00–1.03 m` from interior-floor nodes to roof nodes | Node-to-node proxy, not measured clear headroom; trim, seats and roof thickness reduce it |

The shipped DX manual metadata reports `1010 kg`, 78 hp, FWD, and 36.3 m for 100–0 km/h; DXi manual reports `1015 kg`, 89 hp and 35.7 m. These are **shipped configuration metadata**, not measurements made in this audit.

## Architecture and relevant identifiers

- Root part `covet` has core slot `covet_body`; `covet_body` supplies front/rear suspension, interior, front doors, glazing, fuel tank, cooling, bodywork and other slots.
- Key preserved slots for the recognizable front are `covet_fender_R/L`, `covet_door_R/L`, `covet_hood`, `covet_fascia_F`, `covet_bumperbar_F`, `covet_bumper_F`, `covet_headlight_R/L`, `covet_interior`, `covet_suspension_F`, `covet_engine`, `covet_radiator`, and front drivetrain descendants.
- Stock rear suspension is independent. Important body-side mounts are `rx1r/l` (y `1.304`), `rx2r/l` (y `0.5888`), `rx3r/l` (y `1.1627`), trailing-arm rail nodes `rx4r/l` and `rx5r/l` (y `0.8461`), and shock tops `rs1r/l` (y `1.34`).
- The rear structure begins before the rear axle: `r1r/l` at y `1.30`; `r2*` around y `1.77`; shock towers at y `1.34`. Body torsionbars explicitly rigidify the rear frame using `f4*`, `r1*`, and `r2*`.
- The stock rear wheel plane at y `1.25` is close to suspension hub nodes around y `0.846–1.289`; this is a compact-car assembly with base rear springs of `19,500 N/m` per JBeam spring entry and nominal rear brake torque `540 N·m` per rear wheel entry. Neither value is a certified load rating.
- The vanilla archive includes a mid-engine/RWD path (`covet_body_midengine`, `covet_suspension_R_midengine`, `covet_hub_R_midengine_*`, `covet_differential_R`, `covet_halfshafts_R`). It proves a driven rear Covet JBeam exists, not that a front-engine AWD combination exists or fits a camper floor.

## Candidate cut and join

**HYPOTHESIS, not an approved cut dimension:** retain the complete A-pillars, windshield, roof header, front doors, door apertures/latches and B-pillar door-closing structure, then place the coachbuilt transition immediately aft of the B-pillar/door seam. Static evidence bounds the transition region approximately between y `0.49 m` (visual door end) and the first stock rear-suspension toe-link mounts at y `0.589 m`.

This is a narrow and structurally busy region. A simple planar deletion at y `0.50 m` would sever or orphan:

- roof rails after `rf2*`;
- lower side/floor load paths after `f3*`/`f4*`;
- quarter-panel and C-pillar structure;
- the stock rear-suspension structure, beginning with `rx2*` at y `0.5888 m`;
- diagonal/torsional beams that tie the B-pillar, floor and rear frame together.

The credible approach is therefore a new project-owned perimeter bulkhead/ring at the B-pillar transition, tied into both sill/floor rails and roof/header nodes, plus longitudinal reinforced rails extending to a new rear-suspension cradle. It must not be a visual mesh seam alone.

## Walkthrough and packaging

- A real central passage is geometrically plausible because the B-pillar node span is `1.314 m` between x `±0.657 m`, but that is an outer structural span, **not clear opening width**.
- Existing floor-to-roof node spacing near the B-pillar is only about `1.0 m`; an upright cab-to-coach passage is impossible without the taller camper volume beginning immediately aft/above the cab. A crouched/step-through opening is plausible; exact clear width/height remains unmeasured.
- The opening removes the easiest transverse bulkhead. The replacement ring should route loads around it through two sill rails, two B-pillar uprights, and an overhead header, with diagonals continued rearward outside the passage envelope.
- The overcab berth must bridge above the preserved windshield/roof without loading only the thin roof nodes. Its primary supports should return to the B-pillar/header ring and coach sidewalls; the berth underside must clear door swing, sightlines and occupant head envelope.
- The camper must be wider than the 1.674 m body-mesh width. Exact exterior width is **owner/design input still required**; no width was invented as a measurement.
- The side entry, windows, rear-corner wings and swooping single-wheel arches are viable as original geometry, but each opening removes shear area and needs framed JBeam perimeters. Wheel-arch sweep must be set from articulated wheel envelopes, not the static wheel center alone.

## Structural implications and risks

1. **Primary bending:** front axle/cab loads must flow through reinforced lower rails into the rear suspension mounts; camper floor cannot rely on the removed hatchback unibody tail.
2. **Torsion:** an open walkthrough plus side door creates two large discontinuities. Closed roof/side/floor cells and crossmembers around—not through—the passage are required.
3. **Local concentration:** original `f3*`, `f4*`, `p3*`, `p4*` and `rf2*` neighborhoods need distributed joins; attaching many stiff beams to one or two Covet nodes would cause numerical stiffness and unrealistic tearing.
4. **Collision continuity:** coach wall/floor triangles need coherent overlap-free coverage and controlled breakgroups. The passage should not be sealed by collision triangles.
5. **Rear overhang:** equipment placed behind the rear axle increases rear axle load and unloads the FWD axle; heavy tanks/battery should stay low and between axles where possible.
6. **Roof/wing behavior:** wings must be light, deformable styling structures, not high-mass nodes or rigid levers on rear corners.

## Measurements still required before modeling is frozen

- Owner-approved exterior width, overall length, wheelbase range, rear overhang and target tire/wheel package.
- Driver-seat H-point, steering/seat adjustment envelope, clear passage width/height and step height from an in-game or exported measurement setup.
- Full bump/droop and steering envelopes with chosen tires; spring/damper laden and unladen ride heights.
- Exact donor cradle/rail placement relative to the Covet front axle and planned floor.
- Door aperture, window, bunk mattress and interior aisle dimensions.
- Measured node mass/axle weights/CG for the first implementation prototype.

Static inspection: **PASSED for feasibility evidence.** In-game validation: **NOT TESTED.**

