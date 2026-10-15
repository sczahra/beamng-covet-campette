# Vanilla rear-suspension options

## Scope and evidence

Only installed vanilla BeamNG.drive 0.39.4.0.20972 content was considered. Configuration weights demonstrate the native context in which a system is used; they are **not axle ratings or payload certifications**. JBeam bound parameters are not direct wheel-travel measurements.

## Comparison

| Candidate | Static evidence | Compatibility and risks | Audit disposition |
|---|---|---|---|
| **Lansdale beam axle, heavy springs/shocks** | `lansdale_suspension_R.jbeam`: part `lansdale_suspension_R`, displayed as “Beam Axle Rear Suspension”; wheel plane y `1.565`, brake/hub centers x about `±0.80`; trailing-arm pivots `rx1rr/ll` x `±0.68`, y `1.12`; Panhard mount `rx2r`; heavy spring/shock slots exist. Standard limiter ranges `0.20/0.16`; heavy shock entries use `0.10/0.08` (JBeam bound parameters). Cargo config `22_cargo_A` is FWD, `1650 kg`, uses this beam axle with `lansdale_spring_R_heavy` and `lansdale_shock_R_heavy`. Rear drum brake torque `850 N·m`; rear disc options `1200–1350 N·m`. | Closest vanilla architecture to a compact FWD load carrier; 1.60 m hub-center track is 0.18 m wider than Covet's ~1.42 m and suits a wider coach visually. Mounts and body node names are Lansdale-specific and cannot be dropped into Covet unchanged. Capacity still must be validated under Campette mass. Beam axle occupies a lateral/vertical volume across the floor but needs no differential/driveshaft for base FWD. | **Preferred base-FWD reference/donor strategy; CONDITIONAL.** Adapt geometry and concepts into project-owned integration, preserving vanilla provenance and verifying loads. |
| **Lansdale independent driven rear** | `lansdale_suspension_R_independant.jbeam`: part `lansdale_suspension_R_independant`; subframe mounts `rx1*..rx5*`, hub nodes near x `±0.736..0.794`, y `1.427..1.653`; rear differential slot and halfshafts; heavy transverse leaf and heavy strut options; limiter `0.15/0.15`, standard strut bound `0.105/0.065`. AWD config `38_SE_AWD_A` is `2030 kg`. | Correct scale and complete driven independent architecture; more mounting points, more intrusion, differential/subframe mass and driveshaft/exhaust/fuel-tank conflicts. It adds complexity not needed for FWD and is explicitly outside Milestone 1 unless separately approved. | **Preferred AWD research baseline; not for base Milestone 1.** |
| **Stock Covet independent rear, reinforced** | `covet_suspension_R.jbeam`; ~1.42 m hub-center track; base spring entry `19,500 N/m`; base rear brakes `540 N·m`; shock-top nodes `rs1*`, multiple body mounts from y `0.589..1.34`; base bounds `0.10/0.09`, coilover bump-stop `0.08/0.08`. | Best slot/node compatibility and narrowest packaging. It is designed in a ~1010–1070 kg hatchback context; simply raising spring rate does not establish arm, hub, mount, brake or fatigue capacity. Narrow track under a wider high coach worsens rollover margin and wheel-arch proportions. | **Rejected as the production-intent default unless later load testing proves a comprehensive reinforced redesign.** Useful only as baseline evidence. |
| **Gavril H-Series live axle / leaf spring** | `van_suspension_R.jbeam`: `van_axle_R`, driven live axle, leaf mounts y `1.45/2.61`, hub centers x about `±0.81`, wheel plane y `2.037`; shock bounds `0.14/0.05`; axle limiter `0.35/0.06`; rear brakes `2200 N·m`, heavy `3900 N·m`. H15/H25 configurations are shipped at `2350/2530 kg`. | Strong load-bearing reference and appropriate ~1.62 m track, but physically large/heavy, requires a differential and rear-driveline accommodation, assumes frame rails and leaf mounts unlike the Covet, and is mechanically inappropriate as a dead axle for the base FWD configuration. Native weights do not prove Campette axle capacity. | **Rejected for base FWD; retain as load-path/brake reference.** Could only re-enter with owner approval for a materially different architecture. |
| **Gavril D-Series/common pickup rear assemblies** | Installed in `common.zip` under `vehicles/common/pickup/pickup_suspension_R*.jbeam` and matching differential files. | Full-size body-on-frame architecture and similar disadvantages to H-Series; no evidence it offers a closer package than the directly inspected H-Series. | **Rejected from detailed study as dominated by H-Series for this use.** |
| **MD-Series single-leaf rear** | Installed paths `vehicles/md_series/md_series_suspension_R_single_leaf*.jbeam`; medium-duty platform. | Grossly oversized mass/track/frame architecture for the baby Class C concept. | **Rejected early.** |

## Recommendation

Use the **Lansdale FWD beam axle with heavy-duty spring and damper behavior as the Milestone 1 donor reference**, not as a blind file transplant. Place its wheel centers to satisfy an owner-approved wheelbase and camper arch shape, construct project-owned reinforced rail/cradle nodes, and adapt the suspension links/brakes coherently. Retain single rear wheels.

Why this leads: it is vanilla, compact, FWD-compatible without fake rear driveline parts, visibly suitable for a wider body, already used with heavy components in a 1650 kg cargo configuration, and has fewer floor intrusions than the driven independent option. Why it remains conditional: track, ride height, rate, damping, braking balance, mount loads and deformation response have not been tested on a Campette.

## Required validation

- Static node/beam/slot validation and exact no-load geometry.
- In-game wheel alignment, droop/bump, tire/body clearance and laden/unladen ride-height measurements.
- Progressive payload tests up to the owner-approved gross target, observing mount deformation and bottoming.
- Straight-line and split-µ braking, parking brake, brake heat/fade, curb strike and one-wheel bump tests.
- Slalom/lane-change, crosswind/side-slope and curb/ramp articulation tests.

Static donor inspection: **PASSED.** Physical compatibility: **CONDITIONAL.** In-game tests: **NOT TESTED.**

