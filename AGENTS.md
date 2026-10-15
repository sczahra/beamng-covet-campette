# Covet Campette: Codex operating instructions

Status: **APPROVED AND ACTIVE as of 2026-10-15.**

## Mandatory start-of-task procedure

1. Read this file, `PROJECT_RULES.md`, `DESIGN.md`, `DECISIONS.md`, `PROGRESS.md`, and `ASSETS.md` before changing anything. Resolve contradictions by stopping for owner approval; do not choose silently. The most recent explicit owner decision supersedes older plans, but must be recorded in `DECISIONS.md`.
2. Establish the requested milestone, acceptance criteria, current branch/commit, available context, and whether this is **research-only** or **implementation**. If ambiguous, ask one targeted question.
3. Inspect existing files and the user's actual environment before installing tools: application versions, executable paths, working status, BeamNG version, user folder, active mods directory, Blender, Python, Git, and any current mod ZIP. Do not assume standard Windows paths.
4. For proposed donor assets, inspect exact vanilla files and their provenance. Separate verified facts, assumptions, and unknowns. Do not treat conceptual renderings as meshes or JBeam.
5. State a concise plan and estimated time, identify what will become visible/playable at the end, and checkpoint before substantive changes.

## Decision authority: guided autonomy

**Allowed without new approval, strictly within an approved milestone:** edit project-owned code and original geometry; fix ordinary defects; change implementation details that preserve agreed functionality and appearance; test, document, commit validated milestones; and deploy validated ZIPs as described below.

**STOP and request explicit owner approval BEFORE:** changing target design, scope, architecture or milestone; replacing requested parts with substitutes; incorporating any third-party asset or dependency; copying or publishing BeamNG proprietary assets; discarding prior work; deleting irreversible data; taking shortcuts that weaken the approved quality target; adopting a new donor vehicle; or creating unrelated systems. When blocked, report cause, evidence, options, tradeoffs and recommendation, then wait. Do not spin in retry loops.

**Exception for original custom geometry:** The owner has expressly approved creating an **original canned-ham camper body** for this project, including the necessary original camper interior and structural joins once their milestone is authorized. This is not permission to invent alternate bodies, filler assets or unrelated mechanics.

## Non-negotiable design constraints

See `DESIGN.md`. Core identity: recognizable vanilla Ibishu Covet front; newly modeled rounded Shasta-*inspired* baby Class C rear, wider than cab; actual walkthrough; overcab berth; swooping integrated rear wheel openings with **single rear wheels**; small vintage rear-corner wings. Rear suspension must be suitably load-bearing. Base FWD planned; AWD is a planned optional configuration, **not approved to implement until its own milestone**. Do not copy a commercial Shasta or third-party mesh verbatim.

## Work sequencing and quality

- Do **read-only feasibility and provenance audit first**, before Blender/JBeam modification. Verify the Covet cut/join geometry, structural load path, candidate rear axle, wheelbase, mass budget, camper dimensions, and candidate AWD packaging. Record what cannot yet be verified.
- Each implementation milestone must make permanent, representative progress toward a recognizable, eventually playable Campette. Do not replace promised results with generic boxes, dummy mechanics, or cosmetic mock-ups. Temporary internal diagnostic artifacts may be used only when identified as diagnostics and kept out of deliverables.
- Prefer vanilla BeamNG mechanical systems and project-owned geometry. No third-party asset, library, model or dependency without explicit case-by-case approval **even if free or permissively licensed**.
- Avoid creating unsupported mechanisms. If a donor component cannot be adapted, stop rather than improvising a different vehicle.
- Physically connected parts must have coherent JBeam structure, mounting nodes, suspension/drivetrain connections, collision/deformation handling, and matching visual geometry. Mesh edits alone do not count as functioning features.

## Repository, assets and licensing

- Never edit BeamNG installation files or original shipped ZIPs. Work only in an isolated project workspace.
- Public GitHub repo should store original project source, scripts, instructions, non-proprietary evidence and manifests. Do **not** commit copied vanilla meshes, textures, JBeam, proprietary game assets, game installation paths with private user data, unauthorized third-party content, or binary game dumps.
- Use vanilla references locally when permitted, and document which stock source/part/version is required. For each newly introduced external asset, record URL, creator, license, modifications and owner's approval in `ASSETS.md` before integration.
- Do not assert a project license for the entire mod until owner approval. Keep legal/license uncertainties visible.

## Validation and delivery

- Validate syntax, JSON/JBeam structure, slot references, node/beam integrity, mesh identifiers, relative paths, texture references, and ZIP structure using available tooling. Do not claim actual in-game success from static checks alone.
- For load-bearing, walkthrough, doors, suspension and drivetrain, use BeamNG in-game tests **only when the user launches it and testing is permitted**. The agent must **never automatically launch BeamNG**. Record tests as `STATIC PASSED`, `IN-GAME PASSED`, `FAILED`, or `NOT TESTED` separately.
- Every validated change that updates the distributable mod increments its version (do not silently reuse a previous version). The repo may have research-only documentation commits without releasing an empty mod.
- After a build passes the applicable available validation checks, automatically deploy it as a versioned ZIP to the **confirmed active** BeamNG mods directory. **Before replacing/removing** an existing installed Campette ZIP, save a verified rollback copy and preserve prior working builds. Deploy atomically where practical; keep the previous working version if validation or deployment fails. Never auto-launch BeamNG or claim gameplay verification that was not performed.
- If the active mod path is unknown or inaccessible, stop deployment and ask; do not guess a destination or declare success.

## Checkpoints, reporting and resource limits

- Make early, frequent recoverable checkpoints; use dedicated branches as appropriate. Commit at every **validated milestone** with clear messages. Do not commit broken build artifacts as releases.
- Update `PROGRESS.md` and `DECISIONS.md` as milestones progress; keep `ASSETS.md` current. Include source commit, version, changelog, validation results, deployment path, rollback location and remaining risks in reports when applicable.
- When approaching tool, time or usage limits, preserve files/findings/scripts first. Stop new large experiments, record exact resumption steps, and avoid duplicated work.
- Show progress for user-run scripts/commands, with estimated completion times and non-destructive defaults. Warn before potentially destructive actions.

## Definition of done for an implementation milestone

A milestone is done only when its owner-approved acceptance criteria are satisfied; original source is saved; relevant tests are run and honestly reported; the project remains recoverable; documents are updated; changes are committed; any distributable update is versioned and deployed only as permitted above; and no unauthorized scope substitutions occurred. If any requirement cannot be met, mark it incomplete.
