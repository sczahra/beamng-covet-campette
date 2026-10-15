# Asset provenance and redistribution constraints

## Provenance register for this audit

| Source | Creator / owner shown by source | Version / identity | Use in Milestone 0 | Redistribution status |
|---|---|---|---|---|
| Project governance and design documents | Project owner | Starting commit `a0ff7e30c12b363b606d893723707d5e158322c4`; D-012 authorization | Requirements and approval evidence | Project-owned documentation; repository contains no project-wide license grant |
| Vanilla Ibishu Covet archive | BeamNG / BeamNG GmbH | BeamNG `0.39.4.0.20972`; `covet.zip` SHA-256 `68D369CDDA446DEEAF5BC78C738D7A4E7FB81B8FCF6D3F39AF7C247FA911AD47` | Read-only geometry/JBeam/config reference | Proprietary game content; not copied into repository; no redistribution permission established by this audit |
| Vanilla Soliad Lansdale archive | BeamNG / BeamNG GmbH | Same game build; `lansdale.zip` SHA-256 `74F087479A09245856AB4B37B65A65694FB2A80C8DB42A72A26DE97D0C9FD305` | FWD beam rear and AWD reference | Same restriction |
| Vanilla Gavril H-Series archive | BeamNG / BeamNG GmbH | Same game build; `van.zip` SHA-256 `D4690075A7FD09201FEAD9743DDC8A19D7EF8DCDFEDBFF2AA151515B1A331FEF` | Load-bearing live-axle/brake comparison | Same restriction |
| Vanilla common vehicle archive | BeamNG / BeamNG GmbH | Same game build; `common.zip` SHA-256 `2A3CAC24928CC8AFE4371E782EA494B272FE6B3FFE5905C5D3E077B08EC713DB` | Confirmed shared pickup donor locations | Same restriction |
| Vintage Shasta-like campers | Various real products/photographs; no specific file acquired | Styling category only | General rounded canned-ham inspiration | No image, mesh, drawing or trademark asset acquired or approved; avoid replica geometry and copied graphics |
| Original Campette geometry/JBeam/materials | To be project-created in a later approved milestone | Does not yet exist | None in Milestone 0 | Ownership/license decision pending; cannot claim a project-wide license yet |
| Third-party assets/dependencies | None | None | None | Not approved |

## Audit handling

- Vanilla ZIPs were opened read-only. Selected text members were streamed and `covet.dae` was parsed in memory; no extracted vanilla file was written to the repository.
- Documentation records paths, identifiers, coordinates, hashes and engineering observations only. It embeds no mesh, texture, JBeam body, material, configuration or binary dump.
- User/private paths are sanitized. Archive hashes identify the exact local evidence without redistributing it.
- No third-party model, code, image, library or plugin was downloaded or integrated.

## Implementation provenance gate

Milestone 1 must resolve a critical source-control issue: preserving the literal vanilla Covet front while cutting away its rear normally produces a modified/derived vanilla mesh. Under the active project rules that artifact must not be committed to the public repository without explicit permission.

Decision-ready options, requiring owner approval and license review:

1. **Local build pipeline:** public repository stores only project-owned geometry/scripts/instructions; an authorized local build step reads the user's installed `covet.dae` and creates a local-only derived body. The generated proprietary derivative and ZIP remain untracked/unpublished.
2. **Separate private artifact storage:** keep any derived vanilla body outside the public repository with access and redistribution controls; public source still cannot claim a complete distributable build.
3. **Verified permission:** obtain and record explicit BeamNG permission/terms that cover the intended derivative redistribution before committing or releasing it.

Rebuilding a lookalike front from scratch would undermine the locked “vanilla Covet front” identity and is not an approved substitution. Covering the intact hatchback rear with a camper shell would fail the real walkthrough and production-intent quality bar.

This is a project policy/provenance conclusion, not legal advice. No permission beyond the owner’s project authorization was inferred.

