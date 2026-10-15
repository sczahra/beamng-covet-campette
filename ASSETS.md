# Asset, donor and license register

Status: **Milestone 0 research complete. Vanilla donors inspected read-only; no asset incorporated.**

## Asset rules
- Original Campette meshes, textures and JBeam can be created only during an approved implementation milestone.
- BeamNG vanilla vehicle assets can be inspected locally, subject to BeamNG terms, but proprietary vanilla meshes, textures, JBeam and archives must not be copied into a public GitHub repository without authorization.
- No third-party asset, plugin, mesh, texture, mod, code or library is approved merely because it is free or under a permissive license. **Obtain explicit owner approval first.**
- For each approved external dependency, document author, exact source URL and version, license and evidence, modifications, attribution, permissions, checksums and how it is used.
- 'Free to download' is not equivalent to redistribution permission.

## Candidate donors
| Component | Source | Status |
|---|---|---|
| Front fascia, cab, front doors, dashboard, controls, engine and FWD steering | Vanilla Ibishu Covet | **Owner-confirmed foundation; inspected read-only.** Any cut/derived mesh remains local/private absent verified redistribution permission. |
| Reinforced rear suspension | Vanilla Soliad Lansdale FWD beam axle | **Owner-confirmed preferred starting candidate, conditional on engineering validation.** Not an unconditional donor approval and not permission to use the whole Lansdale chassis. |
| Optional driven rear axle and AWD system | Vanilla Soliad Lansdale AWD chain / independent rear reference | Static feasibility inspected; deferred and not authorized for Milestone 1. |
| Canned-ham camper shell, integrated cab transition | Original project geometry | Concept approved; modeling milestone pending |
| Camper door, glazing, interior and equipment | Original project geometry with permitted vanilla references | Design/engineering pending |
| Styling reference | Vintage 1960s Shasta-like canned-ham campers | Inspiration only, no copying of model assets |
| Third-party donor meshes | None | None approved |

## Milestone 0 inspected vanilla evidence — 2026-10-15

Inspection used installed BeamNG.drive `0.39.4.0.20972` (build 20972) archives read-only. No vanilla member was copied into this repository.

| Archive / component | SHA-256 / identifiers | Audit result |
|---|---|---|
| `content/vehicles/covet.zip` | `68D369CDDA446DEEAF5BC78C738D7A4E7FB81B8FCF6D3F39AF7C247FA911AD47`; `covet_body`, `covet_suspension_F`, `covet_suspension_R` and related front/rear drivetrain parts | Required front/cab source confirmed; cut/join and derived-mesh provenance remain implementation gates |
| `content/vehicles/lansdale.zip` | `74F087479A09245856AB4B37B65A65694FB2A80C8DB42A72A26DE97D0C9FD305`; FWD `lansdale_suspension_R`, AWD `lansdale_suspension_R_independant`, `lansdale_transfer_case_AWD` | Preferred base rear-suspension reference and preferred later AWD architecture |
| `content/vehicles/van.zip` | `D4690075A7FD09201FEAD9743DDC8A19D7EF8DCDFEDBFF2AA151515B1A331FEF`; `van_axle_R` | Load-bearing/brake reference; rejected for base FWD packaging |
| `content/vehicles/common.zip` | `2A3CAC24928CC8AFE4371E782EA494B272FE6B3FFE5905C5D3E077B08EC713DB`; shared pickup suspension files | D-Series confirmed but rejected from detailed study as dominated by H-Series for this concept |

Detailed paths, evidence and redistribution constraints are in `milestone-0/asset-provenance.md` and `milestone-0/rear-suspension-options.md`.

## Proposed Milestone 1 storage boundary

If Milestone 1 is approved, public Git may contain original Campette geometry/material source, project-authored JBeam and scripts, measurements, transforms, hashes, manifests, documentation and validation results. It must not contain extracted or modified vanilla meshes, textures, JBeam/material files, game archives, complete local ZIPs containing vanilla derivatives, private absolute paths or raw logs. The proposed builder reads a verified local BeamNG installation and writes all vanilla-derived output to ignored local storage. This boundary is a planning recommendation, not implementation authorization or a project-wide license grant.

## Intake questions before any third-party import
Identify: author, original URL, model format and topology, materials/textures, exact license, credit and redistribution obligations, extra dependencies, permission decision, and why existing vanilla/original options are insufficient. Stop until approved.
