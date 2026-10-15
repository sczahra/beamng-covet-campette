# Preliminary mass and handling assessment

## Status and method

No Campette mesh, node mass, axle scale reading or CG test exists. Every Campette value below is an **ESTIMATE or parametric example**, never a measured fact. The only observed masses are BeamNG's shipped configuration metadata: Covet DX manual `1010 kg`, DXi manual `1015 kg`, FWD 1.5 GTz Turbo manual `1050 kg`, Lansdale cargo `1650 kg`, Lansdale AWD `2030 kg`, H15 van `2350 kg`, and H25 worker `2530 kg`.

Let:

- `m_i` = component mass in kg;
- `x_i` = its longitudinal CG distance aft of the front axle in m;
- `L` = wheelbase in m;
- `M = Σm_i`;
- `R_rear = Σ(m_i x_i) / L`;
- `R_front = M − R_rear`;
- `x_CG = Σ(m_i x_i) / M`.

The example uses `L = 2.815 m`, equal to the Covet front wheel plane (`−1.25`) to the Lansdale rear wheel plane (`+1.565`) **if their raw coordinates were aligned**. That is a useful packaging case, not an approved wheelbase.

## Component assumptions

| Component | Low | Nominal | High | Why uncertainty is large |
|---|---:|---:|---:|---|
| Retained Covet cab/front drivetrain | `800 kg @ 0.65 m` | `850 @ 0.70` | `900 @ 0.80` | No cut shell exists; removed rear-body mass is unknown |
| Reinforced rails/floor/join | `140 @ 1.45` | `180 @ 1.55` | `220 @ 1.70` | Gauge/topology not designed |
| Camper shell/interior/bunk | `330 @ 1.80` | `420 @ 1.90` | `550 @ 2.10` | No geometry or material takeoff |
| Tanks, battery, appliances, fluids | `100 @ 2.00` | `150 @ 2.20` | `220 @ 2.40` | Capacities and placement unknown |
| Occupants and payload | `200 @ 1.55` | `300 @ 1.70` | `400 @ 1.90` | Owner has not selected occupant/payload target |

## Calculated examples

| Scenario | Gross mass | Moment | Longitudinal CG | Front axle | Rear axle | Split F/R | 100 km/h kinetic energy | vs 1010 kg Covet |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Low | `1570 kg` | `1827 kg·m` | `1.164 m` aft of front axle | `921 kg` | `649 kg` | `58.7/41.3%` | `606 kJ` | `1.55×` |
| Nominal | `1900 kg` | `2512 kg·m` | `1.322 m` | `1007.6 kg` | `892.4 kg` | `53.0/47.0%` | `733 kJ` | `1.88×` |
| High | `2290 kg` | `3537 kg·m` | `1.544 m` | `1033.5 kg` | `1256.5 kg` | `45.1/54.9%` | `883 kJ` | `2.27×` |

Calculation example for nominal rear axle: `(850×0.70 + 180×1.55 + 420×1.90 + 150×2.20 + 300×1.70) / 2.815 = 892.4 kg`.

These broad results show feasibility, not acceptability. The high case makes the rear axle dominant and erodes FWD traction. Neither Covet front-axle capacity nor Lansdale donor capacity is published in the inspected data, so **no gross or payload rating is approved**.

## Center of gravity and stability

- Longitudinal CG is highly sensitive to rear overhang. For any item moved `Δx`, rear axle load changes by `m·Δx/L`; moving a 100 kg tank 0.8 m forward on a 2.815 m wheelbase removes about `28 kg` from the rear axle and adds it to the front.
- CG height is **UNKNOWN**. A planning range of `0.75–1.05 m` is an estimate for sensitivity analysis only. The overcab bunk, roof and cupboards raise it; floor-mounted water/battery lower it.
- A wider rear track (~1.60 m Lansdale reference versus ~1.42 m Covet) helps static rollover margin, but no threshold can be claimed until actual CG height, tire compliance and suspension roll stiffness are measured.
- The side door, tanks and galley can create lateral imbalance. Final configurations need left/right wheel-weight checks in empty and loaded states.

## FWD traction and grade behavior

Static front fraction in the examples ranges from `45.1%` to `58.7%`. An idealized traction ceiling is `F = μ R_front g`; the corresponding no-transfer acceleration ceiling is `a/g = μ·(front fraction)`. With `μ=0.4` this gives only about `0.18–0.23 g`; with `μ=0.8`, `0.36–0.47 g`. These are theoretical estimates: acceleration transfers load rearward, so real FWD launch and hill-start limits will be lower.

Risks: wheelspin on wet grades, torque steer, front tire overload, high clutch/converter heat, and reduced steering authority under power. Keep permanent heavy equipment ahead of or close to the rear axle, avoid excessive rear overhang, and validate the laden front normal load rather than targeting a rear-heavy motorhome stance.

## Braking

- Kinetic energy from 100 km/h is `E = ½Mv²`; the examples require `1.55–2.27×` the single-stop energy of the 1010 kg Covet before accounting for larger tires or grades.
- Base Covet brake entries are `1350 N·m` front and `540 N·m` rear; sport/race options exist. Lansdale standard entries are `2520/850 N·m`, with rear discs `1200–1350 N·m`. Torque values alone do not establish stopping distance or fade performance.
- Brake bias must follow actual dynamic axle loads. A rear donor brake cannot be combined with untouched front bias by assumption.
- Required tests include repeated 100–0 km/h stops, downhill fade, ABS behavior, split-µ stability and parking-brake hold at the approved gross mass.

## Power, cooling and steering

- The FWD 1.5 GTz Turbo shipped metadata (`151 hp`, `200 N·m`, `1050 kg`) shows a vanilla higher-output Covet path, but at 1900 kg its metadata power-to-weight would fall from `7.0` to `12.6 kg/hp`, before increased aerodynamic drag.
- A tall/wide coach increases frontal area and sustained load. Cooling adequacy is **UNKNOWN**; static radiator presence is not evidence of hill-climb heat rejection. Validate coolant/oil/transmission temperatures at gross mass and low-speed/high-load conditions.
- Front tire, wheel bearing, hub, steering rack, strut tower and spring loads may exceed the hatchback context. Steering effort, bump steer and alignment under load require in-game measurement.
- Stability risks include crosswind yaw, snap load transfer, rear roll steer, understeer from front overload and oversteer if the rear axle/brake balance is too aggressive.

## Preliminary recommendation

Use `1900 kg` only as a **nominal engineering test point**, with `1570–2290 kg` retained as the uncertainty envelope. Do not publish a payload or GVWR until a modeled mass audit and in-game axle/CG/load tests establish limits. A first prototype should keep front static load at or above roughly half of gross mass as a design target, subject to tire and axle capacity evidence—not as a final specification.

Static calculations: **PASSED.** Measured Campette mass/CG/axle loads: **NOT AVAILABLE.** In-game handling, braking, cooling and traction: **NOT TESTED.**

