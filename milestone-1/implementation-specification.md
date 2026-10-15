# Milestone 1 implementation specification — FWD Campette first playable

Status: **PROPOSED FOR OWNER APPROVAL — IMPLEMENTATION NOT AUTHORIZED.**

Prepared 2026-10-15 from the completed Milestone 0 static audit at commit `0cdbf39cd8a432a7e8c7d9c3fb0ea26e727e6d11` and the owner's subsequent direction. This document is the approval package; it does not create a vehicle, grant permission to publish BeamNG content, or authorize BeamNG launch.

## Evidence labels

- **VERIFIED:** observed in installed BeamNG.drive `0.39.4.0.20972` or an authoritative project document.
- **CALCULATED:** arithmetic from verified values or explicitly stated assumptions.
- **ESTIMATED:** recommended design target or engineering planning range, not a measurement.
- **UNRESOLVED:** requires implementation evidence, owner choice, permission, or an in-game test.

## 1. Locked design direction

Milestone 1 must preserve:

- the recognizable vanilla Ibishu Covet hood, fascia, windshield, front doors, dashboard, front suspension and transverse FWD character;
- an original rounded canned-ham coach, wider and taller than the cab, with vintage ribbed-aluminum treatment;
- a compact overcab berth and genuine cab-to-living-area opening;
- a framed side entry, real window openings, swooping integrated single-rear-wheel arches, and small Shasta-inspired rear-corner wings;
- a reinforced lower structure and a plausible, load-bearing rear suspension.

The vanilla Soliad Lansdale FWD beam rear suspension is the preferred starting candidate, subject to engineering validation. This is not permission to transplant the entire Lansdale chassis or to treat its native configuration mass as an axle rating. AWD remains deferred.

## 2. Recommended package

### 2.1 Dimensional control envelope

| Item | Recommended Milestone 1 value | Label | Basis and control rule |
|---|---:|---|---|
| Front wheel plane | Covet y `-1.250 m` | **VERIFIED** | Vanilla Covet hub/flexbody offset; retain as the datum. |
| Rear wheel plane | y `+1.565 m` initial package | **VERIFIED** source coordinate / **ESTIMATED** Campette placement | Native Lansdale beam wheel plane when coordinates are aligned. May move only within the wheelbase band after a documented clearance review. |
| Wheelbase | `2.815 m` nominal; `2.75–2.90 m` permissible tuning band | **CALCULATED** nominal / **ESTIMATED** band | `+1.565 - (-1.250)`. Freeze before detailed arch and floor work. |
| Coach exterior width | `1.95 m` target; `1.90–2.00 m` band | **ESTIMATED** | Must exceed the verified `1.674 m` Covet body-mesh width and contain the approximately `1.60 m` Lansdale hub-center track without dually-style bodywork. |
| Overall length | `4.80 m` target; `4.70–4.95 m` band | **ESTIMATED** | Compact Class C proportion target. At the nominal wheelbase and verified approximately `0.600 m` Covet body front overhang, this implies about `1.385 m` rear overhang. |
| Overall height | `2.45 m` target; `2.35–2.55 m` band | **ESTIMATED** | Allows an immediate taller coach behind the verified `1.329 m` Covet body roof maximum; actual ground/roof relationship must be measured in the first local build. |
| Rear track datum | approximately `1.60 m` hub-center | **VERIFIED** | Lansdale beam brake/hub centers are about x `±0.80 m`; tire outer width and offset remain **UNRESOLVED**. |
| Cab/entry handedness | LHD Covet cab; entry on vehicle right/passenger side | **ESTIMATED design recommendation** | Gives a conventional curb-side coach entry while preserving an original vanilla Covet dashboard layout. Owner may override this explicitly. |

These are construction targets, not claims about a completed vehicle. If the required wheel/tire envelope, walkthrough, or axle-load test cannot fit these bands, implementation must stop for owner approval rather than silently stretching the design.

### 2.2 Cab cut, join, and walkthrough

- **VERIFIED:** Covet front-door geometry ends at y `0.48585 m`; B-pillar upper nodes `p3*` and `p4*` sit at y `0.37/0.50 m`; roof nodes `rf2*` sit near y `0.47 m`; floor nodes `f3*` sit at y `0.42 m`; the first stock rear toe-link mounts `rx2*` are at y `0.5888 m`.
- **Recommended:** keep both door apertures, latches, B-pillar door-closing faces, dashboard, windshield and front roof header. Treat y `0.47–0.59 m` as the structural transition zone, not a universal planar mesh cut. The visible cut follows the door/quarter seam while the load-bearing join distributes into `f3*`, `f4*`, `p3*`, `p4*`, and `rf2*` neighborhoods.
- **Recommended:** build a closed perimeter ring around the passage, two reinforced lower rails, an overhead header, and outboard diagonals. Do not terminate the camper on one or two stock nodes, and do not leave stock rear suspension/torsion beams orphaned.
- **ESTIMATED walkthrough targets:** `0.60 m` nominal clear width (`0.55–0.65 m` acceptable); at least `0.90 m` clear height through the preserved cab throat; at least `1.70 m` clear height immediately aft where the coach rises; no collision triangle across the opening. The approximately `1.00–1.03 m` stock floor-to-roof node proxy makes the cab throat intentionally crouched, not standing height.
- **UNRESOLVED:** trim, seat travel, camera, step height, and occupant-clearance measurements. They must be captured from the first local geometry before the passage is frozen. A failure to achieve the minimum opening is a stop condition, not grounds for a false partition.

### 2.3 Coach load paths

The first playable must use one coherent structure:

1. Twin lower rails carry cab/front reactions to the rear cradle.
2. Crossmembers support a continuous coach floor and spread suspension and equipment loads.
3. The cab-transition ring routes bending and torsion around the walkthrough.
4. Coach side sills, corner posts, waist rails and roof rails form closed side/roof cells.
5. The entry door and windows have framed perimeters tied to adjacent posts and rails.
6. The overcab bunk bears on the transition/header ring and coach sidewalls, not only on Covet roof nodes.
7. Rear-corner wings remain low-mass deformable styling structures with controlled breakgroups.

Water, battery and other dense test masses should be low and between the axles. Keep a straight protected center corridor available for a possible later AWD shaft, but install no AWD component or fake tunnel system in Milestone 1.

### 2.4 Rear suspension architecture

- **VERIFIED source:** `vehicles/lansdale/lansdale_suspension_R.jbeam`, part `lansdale_suspension_R`, with trailing-arm pivots near x `±0.68`, y `1.12`, Panhard location `rx2r`, approximately `1.60 m` hub-center track, and available `lansdale_spring_R_heavy` / `lansdale_shock_R_heavy` parts.
- **Recommended mounting strategy:** re-express the beam, trailing arms, Panhard bar, springs and dampers in Campette coordinates and attach them to a project-authored cradle tied into both lower rails and at least two crossmembers. Preserve single wheels. Do not inherit the Lansdale body shell, floor, wheelbase, front structure, or full chassis.
- **Recommended brake start:** Lansdale rear disc behavior (`lansdale_brake_R_disc`, nominal JBeam entry `1200 N·m`, parking torque `1900 N·m`) rather than the native cargo drums, subject to bias and thermal tests. These values are not ratings.
- **Initial wheel-envelope references:** the inspected Lansdale cargo rear uses a single `205/75R15` tire on a 15×7 wheel; the inspected GTz Covet uses `185/60R14` at the front. Use those vanilla combinations only to establish the first clearance envelope. Tire load capacity, final appearance, ride-height relationship and any approved vanilla alternative remain **UNRESOLVED**.
- **UNRESOLVED:** tire size/offset, exact mount coordinates, rates, damping, bump stops, travel, roll stiffness, brake bias, mount strength and deformation. Heavy spring/shock labels are only initial references.

Before exterior arch surfacing is finalized, the suspension must pass a static kinematic envelope review and an owner-run in-game bump/droop test. If the beam cannot meet ride-height, floor, or load requirements inside the approved envelope, stop and report; do not switch donors without approval.

### 2.5 Mass and axle-load targets

No Campette mass is measured and no GVWR or payload is approved.

| State | Mass target | Front/rear static target | Label / disposition |
|---|---:|---:|---|
| First empty local build | `1,550–1,750 kg` | `55–60% / 40–45%` | **ESTIMATED** control band; measure in game. |
| Nominal engineering test | `1,900 kg` | approximately `53% / 47%` | **CALCULATED** Milestone 0 case: `1007.6 kg` front, `892.4 kg` rear at `2.815 m` wheelbase. |
| Laden validation band | `1,850–2,050 kg` | keep front at or above `50%` | **ESTIMATED** test band, not a rating or promised payload. |
| Audit uncertainty case | `2,290 kg` | `45.1% / 54.9%` | **CALCULATED risk case; reject as a Milestone 1 target** unless separately engineered and approved. |

Use `R_rear = Σ(m_i x_i) / L`, `R_front = M - R_rear`, and `x_CG = Σ(m_i x_i) / M`. Record component masses and longitudinal/lateral positions as the build develops. Do not advertise payload until tire, front suspension, rear mounts, brakes, cooling and handling establish limits.

### 2.6 FWD powertrain, steering, braking, and cooling

- **Recommended baseline:** the mechanical package represented by vanilla Covet `15gtz_turbo_M.pc`: FWD 1.5 DOHC turbo, `151 hp`, `200 N·m`, sport five-speed manual, front LSD, heavy internals/mounts, sport front brakes and `covet_radiator_race`. Retain the owner-selected original Covet dashboard/handedness; do not blindly inherit that configuration's RHD trim.
- **VERIFIED cooling reference:** `covet_radiator_race` declares radiator area `0.27` and effectiveness `13000` versus `5500` for the standard radiator. This is a simulation parameter comparison, not proof of Campette thermal adequacy.
- **Steering requirement:** retain Covet front geometry; verify tire/load capacity, loaded alignment, full-lock body clearance, steering authority under power, bump steer and mount deformation.
- **Braking requirement:** begin with Covet sport front and Lansdale rear disc references, retain ABS if integration is valid, and set bias only from measured dynamic behavior. The nominal `1900 kg` case carries `733 kJ` at 100 km/h, about `1.88×` the 1010 kg audit reference.
- **Cooling requirement:** complete idle, low-speed climb and sustained-gross-load temperature tests. No static radiator parameter satisfies this criterion.
- **UNRESOLVED:** final gearbox/final drive, front tire and hub capacity, clutch durability, brake bias, fade margin and thermal limits. The manual GTz package is the proposed first baseline; changing to another powertrain is a recorded owner decision.

## 3. Provenance-safe local build architecture

Milestone 1 should use the **local-build route** unless BeamNG grants documented redistribution permission before implementation.

### Public GitHub content

The public repository may contain:

- original Campette coach, interior, structure, material-source and texture-source files created for this project;
- project-authored JBeam, configuration, scripts, validation tools and documentation, provided they do not copy substantial vanilla definitions;
- identifiers, measurements, transformations, archive hashes, version requirements and a build manifest;
- a build script that reads a user's legally installed BeamNG archive and produces the cut Covet derivative locally;
- ignore rules for extracted/generated vanilla-derived files, local builds, ZIPs, logs and private paths.

### Local/private-only content

The following must remain outside Git history and public releases absent verified permission:

- extracted `covet.dae`, vanilla textures/JBeam/material files, or other proprietary archive members;
- the cut/modified Covet mesh and any combined DAE containing vanilla-derived geometry;
- a built mod ZIP containing those derived assets;
- absolute private installation/user paths, runtime logs with identifiers, or raw game archives.

### Required local-build behavior

1. Ask for or discover the installation path without assuming it; sanitize logs.
2. Require BeamNG `0.39.4.0.20972` and verify the recorded `covet.zip` SHA-256 before using the audited transforms. A mismatch stops with an actionable version message.
3. Read only the minimum required source members into a temporary/local ignored workspace; never modify the game archive.
4. Apply project-authored deterministic operations to produce the local cut cab and combine it with original Campette work.
5. Write outputs only to an ignored build directory and, after validation, a confirmed active mods path with rollback. Never launch BeamNG.
6. Record the build version, source hashes and validation results without recording private absolute paths.

**UNRESOLVED permission question:** whether BeamNG permits public redistribution of a modified Covet mesh. Until the owner supplies a written terms citation or permission covering that exact use, the generated cab and complete ZIP remain local/private.

## 4. Milestone 1 scope and deliverables

### Included

1. A reproducible, provenance-safe local source/build layout and one local FWD configuration.
2. Preserved Covet front/cab assets through the approved local derivative workflow.
3. Original production-intent exterior coach geometry at the approved proportions: rounded profile, transition, overcab, ribbing, real entry/window openings, swooping single-wheel arches and small rear wings.
4. Original structural interior foundation: continuous floor, finished passage surfaces, overcab berth platform and wall/ceiling inner shells. Detailed appliances and interactions are deferred.
5. A coherent JBeam transition ring, lower rails, crossmembers, coach wall/roof structure, rear cradle and collision/deformation surfaces matching the visual geometry.
6. Adapted Lansdale-style FWD beam rear suspension with heavy-duty starting behavior, single wheels, working rear discs and parking brake.
7. Covet GTz-turbo-derived FWD baseline with functioning steering, fuel, cooling and brakes.
8. Static validation records plus owner-launched in-game test results, measured mass/axle/CG data, provenance manifest and resumption notes.

### Excluded

AWD; an entire Lansdale chassis; alternate donors; generic/placeholder coach bodies; fake mechanisms; detailed appliance systems; multiple trims; final damage tuning; career/economy work; third-party content; public distribution of unapproved vanilla derivatives; automatic BeamNG launch; and a claimed GVWR/payload.

## 5. Implementation sequence and gates

1. **Authorize and freeze:** approve this scope, local-build route, dimensional targets, crouched walkthrough targets, GTz FWD baseline and owner-run testing.
2. **Provenance/build foundation:** create ignore rules, manifest and deterministic local extraction/build path; validate that no vanilla source enters Git.
3. **Hard points:** establish front datum, nominal rear axle, tire envelope, transition ring, rails, crossmembers and rear cradle.
4. **Rolling structure:** integrate the beam suspension, single wheels, rear discs, front mechanical package and initial node masses; complete static parse/connectivity checks.
5. **Production-intent shell:** create the original exterior and real apertures around the validated wheel/floor/package envelope.
6. **Interior foundation:** create the genuine passage, inner skins, continuous floor and bunk platform with aligned collision surfaces.
7. **Static validation:** syntax, slots, identifiers, flexbodies, materials, paths, node/beam/triangle connectivity, mass arithmetic, clearances and provenance scan.
8. **Owner-run game validation:** deploy only to the confirmed active path with rollback, then have the owner launch BeamNG. Iterate from empty to nominal/laden tests.
9. **Closeout:** record results, unresolved failures and exact build provenance; version only a validated distributable; commit project-owned source. Public release remains a separate provenance-dependent decision.

The first visible checkpoint should be the permanent rolling structure and proportioned original shell, not a generic box. Internal diagnostic envelope meshes are allowed only temporarily and must not be delivered as the Campette body.

## 6. Acceptance and validation

### Static acceptance

- All JBeam/JSON parses and all required slots, meshes, materials and relative paths resolve.
- There are no isolated structural node clusters, duplicate critical nodes, unsupported flexbodies, or collision triangles sealing the passage.
- The ring, rails, floor, walls/roof and cradle provide traceable continuous load paths.
- Visual wheel centers and JBeam hubs agree; swept bump/droop envelopes clear arches, rails and floor.
- Exterior dimensions remain inside the approved bands, with deviations documented and owner-approved.
- Public Git contains no copied/derived proprietary file, private path, credential, log dump, archive or local ZIP.

### Owner-run in-game acceptance

- Vehicle spawns/resets and part selection works without new relevant errors.
- Front/side/rear views unmistakably show the approved Covet Campette identity; no hatchback tail, trailer gap, generic box or solid passage partition remains.
- The walkthrough is visibly continuous and its clear width/height is measured against the approved minima.
- Empty and `1900 kg` nominal test states have measured wheel loads, longitudinal/lateral CG and ride heights; laden tests stay at or above `50%` static front load.
- Full steering lock, one-wheel and full-axle bump/droop show no tire/structure intersection or link inversion.
- Suspension survives curb/ramp articulation and progressive load without persistent mount collapse, severe asymmetry or bottoming at rest.
- FWD launch/grade-start, circles, highway cruise, lane change, slalom and lift-off behavior are controllable with no critical instability.
- Single and repeated 100–0 km/h stops, split-friction stop and parking-brake hold are stable; temperatures and fade are recorded.
- Idle, low-speed climb and sustained loaded operation remain within observed safe thermal behavior; actual temperatures are recorded.
- Controlled impacts and rollover do not produce explosive instability, detached load-bearing clusters or structural intrusion inconsistent with the modeled passenger space.

Each result is recorded as `STATIC PASSED`, `IN-GAME PASSED`, `FAILED`, or `NOT TESTED`. Milestone 1 is incomplete if a required in-game result is unavailable or failed; static evidence cannot substitute for it.

## 7. Compact risk register

| Priority | Risk | Response / stop condition |
|---:|---|---|
| 1 | Proprietary Covet derivative enters public Git or release | Enforce local-only build outputs and scan history/index before every checkpoint; stop distribution absent permission. |
| 2 | Walkthrough and side door weaken torsional structure | Closed transition ring, twin rails, framed apertures and deformation tests; stop if stable continuity cannot be achieved. |
| 3 | Front or rear hardware is overloaded | Measure component and wheel loads from the first rolling build; no rating claim; reduce/reposition mass or stop for architecture approval. |
| 4 | Beam axle conflicts with floor or arches | Prove swept envelope before detailed shell surfacing; do not hide interference or change donor silently. |
| 5 | Rear-heavy/high-CG package loses FWD traction or stability | Keep dense masses low/between axles and front static fraction at least 50% in test band; dynamic tests required. |
| 6 | Brakes or cooling fail at nominal mass | Use verified higher-capacity vanilla starting parts, instrument tests, and treat failures as unresolved engineering—not cosmetic issues. |
| 7 | Scope expands before a usable vehicle exists | Deliver one permanent FWD configuration and core interior foundation; defer AWD, variants and appliance systems. |

## 8. Owner decisions and exact approval gate

The recommended defaults are:

- local-only generated Covet derivative; no public complete ZIP unless permission is verified;
- `2.815 m` nominal wheelbase, `1.95 m` coach width, `4.80 m` overall length and `2.45 m` overall height, within the stated bands;
- LHD Covet cab with the coach entry on the vehicle-right/passenger side;
- `0.60 m` nominal walkthrough width, `0.90 m` cab-throat height and `1.70 m` coach-side height minimum;
- Lansdale FWD beam architecture with project-authored mounts, heavy spring/shock starting behavior and rear discs;
- one FWD 1.5 GTz-turbo-derived, sport-five-speed baseline with high-performance radiator and Covet sport front brakes;
- `1900 kg` nominal engineering test point, at least 50% front static load in the laden validation band, with no GVWR/payload claim;
- owner-launched BeamNG testing after static validation and confirmed local deployment/rollback path.

To begin construction, the owner must explicitly state:

> I authorize Milestone 1 implementation under `milestone-1/implementation-specification.md`, including its local-only proprietary-derivative workflow, recommended dimensional and mass targets, conditional Lansdale FWD beam strategy, GTz-turbo FWD baseline, and owner-launched in-game validation. I understand that AWD, an entire Lansdale chassis, third-party assets, public distribution of unapproved BeamNG derivatives, and Milestone 2 work remain unauthorized.

Any changed default should be named in that authorization. Until then, work stops at this planning package.
