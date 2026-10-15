# AWD feasibility

## Verdict

**CONDITIONAL, technically credible but not ready for implementation.** The installed vanilla Lansdale provides a complete transverse-engine AWD chain at a compatible vehicle scale, and the Covet's current front transaxle already uses a modular `transfercase` device name. However, the Campette has no verified driveshaft corridor, rear subframe package, matched ratios, fuel/exhaust layout or structural mounts. AWD is not authorized for Milestone 1 unless the owner explicitly changes that scope.

## Verified vanilla options

### Lansdale AWD chain — preferred reference

Installed BeamNG 0.39.4.0.20972 files and identifiers:

- `vehicles/lansdale/lansdale_tranfercase.jbeam` (the shipped filename is spelled `tranfercase`): `lansdale_transfer_case_AWD`, a `splitShaft` named `transfercase`, input `gearbox`, viscous split, `primaryOutputID:2`, `viscousCoef:15`, `viscousTorque:500`.
- `vehicles/lansdale/lansdale_differential_F.jbeam`: `torsionReactorF` consumes `transfercase` output 2; `differential_F` and `lansdale_halfshaft_F` drive the front wheels.
- `vehicles/lansdale/lansdale_differential_R.jbeam`: `lansdale_driveshaft` consumes `transfercase` output 1; `lansdale_differential_R` consumes `driveshaft`; `lansdale_halfshaft_R` drives rear shafts `wheelaxleRL/RR`.
- `vehicles/lansdale/lansdale_suspension_R_independant.jbeam`: rear subframe, driven hubs and optional differential slot.
- Shipped `38_SE_AWD_A.pc` selects all of those parts, rear disc brakes, heavy transverse leaf and heavy struts, with matching 3.43 front/rear final drives. Its metadata weight is `2030 kg`.

This is evidence of a coherent vanilla AWD architecture. It is not permission to copy those files into the public repository and not proof of fit in the Campette.

### Covet-native pieces

- `covet_transaxle.jbeam` provides slot `covet_transfercase`; stock `covet_transfercase_FWD` is a shaft named `transfercase` from `gearbox` with `outputPortOverride:[2]`.
- `covet_differential_F.jbeam` already consumes `transfercase` output 2 through `torsionReactorF`.
- The archive also contains a 3-wheel locked transfer-case variant, proving the slot can have more than one output in vanilla, but that novelty part is not a suitable Campette mechanism.
- Mid-engine Covet parts provide a driven rear independent suspension and `covet_differential_R`, but its differential input is `gearbox` and its rear transaxle assumes a rear engine. It is not a ready AWD rear axle.

The least invasive logical strategy is therefore a new project-owned Covet-compatible AWD transfer-case definition following the vanilla Lansdale connection pattern, combined with a suitably placed driven rear assembly. That still requires implementation and testing well beyond this audit.

## Packaging constraints

1. **Driveshaft corridor:** a shaft from the transverse front transaxle to the rear differential must pass below the walkthrough and coach floor without intersecting exhaust, fuel tank, water tanks, crossmembers or suspension travel.
2. **Floor height:** a continuous center tunnel conflicts with a low, level living floor. Raising only a narrow tunnel may be acceptable, but clear walkthrough height is already constrained near the cab.
3. **Rear differential/subframe:** the preferred FWD beam axle cannot simply become driven. AWD likely requires the Lansdale independent rear subframe or a separately approved driven axle, changing mounts, wheel arches, floor and deformation behavior.
4. **Final-drive matching:** front and rear effective rolling radius and final-drive ratios must match; static file names are insufficient. Mismatch creates continuous wind-up or viscous coupling heat.
5. **Fuel/exhaust:** the stock Covet fuel tank and exhaust occupy underfloor/rear space. The Lansdale AWD config uses AWD-specific fuel tank and exhaust parts; equivalent original packaging would be required.
6. **Crash behavior:** driveshaft and differential beams need controlled breakgroups so they do not spear the cabin or unrealistically hold a crushed coach together.
7. **Mass and traction:** AWD adds mass and parasitic loss but mitigates the rear-load-transfer traction problem. It does not solve tire, brake, cooling or axle-load limits.

## Blockers and required evidence

- Owner-approved AWD milestone and acceptance criteria.
- Frozen FWD coach floor, wheelbase, axle position and tank/exhaust package.
- Measured driveline corridor and joint angles at bump/droop.
- Selected rear suspension/axle architecture and matching wheel/tire effective radius.
- Ratio map from gearbox through both final drives, plus torque capacity assumptions.
- Static JBeam powertrain connectivity test followed by user-launched in-game no-load, articulation, coast-down, thermal and failure tests.

## Recommendation

Keep Milestone 1 FWD. Reserve a straight, protected center corridor and avoid placing permanent tanks across it, but do not add a decorative shaft, inactive differential or fake selectable-AWD UI. After the FWD Campette is structurally stable, authorize a separate AWD feasibility prototype based on the Lansdale split-shaft/independent-rear architecture.

Static source inspection: **PASSED.** Packaging: **UNVERIFIED.** AWD implementation and in-game test: **NOT AUTHORIZED / NOT TESTED.**

