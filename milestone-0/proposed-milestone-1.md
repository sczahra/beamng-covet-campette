# Proposed Milestone 1 — production-intent FWD Campette first playable

Status: **PROPOSAL ONLY — NOT AUTHORIZED.** Milestone 0 stops after this recommendation.

## Goal

Produce the smallest local first playable that is unmistakably the approved Ibishu Covet Campette and establishes permanent architecture: preserved Covet front/cab, original rounded wider coach with the real opening and overcab berth, single rear wheels in swooping arches, small rear wings, coherent load-bearing JBeam, and a functional FWD drivetrain with an adapted vanilla Lansdale-style beam rear suspension. No generic box, intact trailer, solid cab partition, fake axle or cosmetic-only shell qualifies.

## Prerequisites and owner approvals

Before implementation, obtain one explicit authorization that answers:

1. Provenance route for the cut vanilla body: local-only generated derivative, private artifact, or documented BeamNG permission.
2. Exterior design envelope: width, overall length, wheelbase/rear overhang, roof height, entry-door side and minimum walkthrough/bunk clearances.
3. Target test masses: dry/curb, occupants, payload, fluids, and maximum gross test point. These are test targets, not public ratings.
4. Approval of the Lansdale FWD beam axle with heavy-duty spring/shock behavior as the rear strategy.
5. Exact vanilla Covet FWD engine/transmission/radiator/brake starting configuration; recommendation is the 1.5 GTz Turbo FWD path as a performance baseline, subject to owner preference and cooling/brake tests.
6. Permission for owner-launched BeamNG test sessions and local deployment path confirmation. The agent still must never launch BeamNG automatically.

## Included scope

- An isolated project-owned vehicle/mod namespace and reproducible local build process.
- Preserved vanilla Covet hood, fascia, windshield, front doors, dashboard and front suspension/drivetrain packaging.
- Original exterior coach at production-intent silhouette/detail level: rounded canned-ham profile, wider cab transition, overcab volume, real side door/window openings, swooping single-wheel arches and rear-corner wings.
- Production-intent structural interior foundation: continuous floor, visible finished passage, overcab berth platform, wall/ceiling inner surfaces, and only the fixed furniture needed to establish layout and mass distribution. No placeholder cubes as deliverables.
- New B-pillar perimeter ring, twin longitudinal rails, floor crossmembers, rear suspension cradle, roof/wall support and coherent collision triangles.
- Adapted vanilla Lansdale beam-axle kinematics with heavy spring/shock baseline, single wheels, working rear brakes and parking brake; project-specific mounts and slots.
- FWD only. AWD corridor reservation is allowed as geometry planning; no AWD parts, UI or fake mechanics.
- Basic production-intent materials using project-owned work and permitted vanilla references; no third-party assets.

## Explicit exclusions

- AWD, functional appliances/plumbing/electrics, multiple trim/config variants, advanced interior interactions, final damage tuning, career/economy integration, public release, and payload/GVWR claims.
- Any copied third-party content or public commit of unapproved BeamNG-derived assets.
- Automatic BeamNG launch, overwrite of vanilla archives, modification of existing mods, or deployment before path/rollback rules are satisfied.

## Acceptance criteria

### Visual and packaging

- From front/side/rear, the vehicle clearly reads as a Covet-based rounded baby Class C with all locked identity features.
- No stock hatchback rear geometry protrudes into the coach; no trailer gap or false partition exists.
- A continuous visible opening connects cab and living area; player camera inspection shows no hidden collision wall.
- Door, windows, bunk, arches and wings are real openings/forms with matching interior/exterior surfaces.
- At full static bump/droop and steering, tires do not intersect arches, floor, rails or coach structure.

### Structure and mechanics

- All required slots resolve; JBeam parses without errors; node/beam/triangle/flexbody groups match visible parts.
- Cab ring, rails, floor, coach walls/roof and rear cradle form continuous load paths with no isolated node clusters.
- Suspension, wheels, brakes, parking brake, steering, FWD powertrain, cooling and fuel systems function without decorative stand-ins.
- Empty and test-loaded ride heights stay within owner-approved tolerances and retain bump/droop clearance.
- Axle loads and longitudinal/lateral CG are measured for at least empty and gross test configurations and remain inside explicit test limits established before the run.

### In-game test matrix

Performed only after the owner manually launches BeamNG:

- spawn/reset, part selection and log-error review;
- static node/beam view, left/right wheel weights, CG and ride heights;
- steering lock plus one-wheel/full-axle bump and droop;
- low-speed circles, curb/ramp articulation and parking-brake grade hold;
- acceleration/grade start on dry and reduced-grip surfaces;
- 100–0 km/h single and repeated stops, split-µ stop and downhill thermal run;
- highway cruise, crosswind/lane-change/slalom and emergency lift-off;
- controlled front/side/rear impacts and rollover observation for stable deformation and passenger-space intrusion.

Results must be recorded separately as `STATIC PASSED`, `IN-GAME PASSED`, `FAILED` or `NOT TESTED`. A static pass cannot satisfy an in-game criterion.

## Dependencies and sequence

1. Resolve provenance and freeze dimensions/mass targets.
2. Establish reproducible local build namespace and baseline configuration.
3. Create the permanent cab cut/join, rails and rear cradle.
4. Integrate rear suspension/brakes and verify kinematic envelopes.
5. Build the original exterior and real apertures around the proven package.
6. Add structural interior foundation and production-intent materials.
7. Static validation, then owner-launched in-game iteration from empty to gross test mass.
8. Update documentation, version any distributable build only if one is legally/technically allowed, preserve rollback, and commit the validated milestone.

## Principal risks

- Provenance decision may limit the first playable to a local generated build rather than a public distributable.
- A donor that works at native Lansdale coordinates may need substantial re-node/mount work at the approved Campette wheelbase.
- The coach mass may exceed Covet front suspension, tire, cooling or brake capability even if the rear axle is sound.
- Walkthrough/side-door openings may require more structure and mass than the preliminary model assumes.
- Full visual quality and deformation stability may not converge in one implementation pass; failure must remain labeled incomplete rather than being replaced by placeholders.

## Completion output

If authorized and passed, Milestone 1 would produce one production-intent local FWD Campette configuration, its original project source and build instructions, recorded static/in-game results, provenance manifest, mass/axle/CG table, risks and rollback information. It would not include AWD or a public release unless separately authorized and provenance-safe.

