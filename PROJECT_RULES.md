# Project rules and change control

Status: **APPROVED AND ACTIVE as of 2026-10-15.**

## Purpose
Produce a high-quality, recognizable, functioning BeamNG.drive mod of a compact Covet-based Class C motorhome. Optimize for a coherent playable result, not impressive-looking but unusable infrastructure.

## Priority order
1. Most recent **explicit** owner approval, recorded in `DECISIONS.md`.
2. Safety, lawful licensing, integrity of game/user files.
3. `AGENTS.md` operating and stop conditions.
4. `DESIGN.md` locked vehicle identity and approved milestone requirements.
5. Implementer preferences, only within those boundaries.

Conflicts require owner approval. Do not interpret silence as authorization.

## Approval gates
- **Research/audit:** Read-only inspection and documented recommendations. Do not begin making vehicle assets under a research-only task.
- **Implementation:** Begin only after owner approves a clearly scoped milestone and acceptance criteria.
- **Substitutions:** Ask first for any changed design, donor, mechanism, third-party source or reduction in scope.
- **New original geometry:** The original canned-ham shell is approved in principle, but details and individual implementation milestones still require authorization.
- **Release/deployment:** A validated distributable update is automatically deployed with rollback, without starting BeamNG, once active mod path and permission to write there are verified. Never treat static validation as in-game verification.

## Data protection
Work outside vanilla installation archives. Check versions/paths and existing installed software before installs. No deletion/overwrite without backup, recoverability and approval for destructive changes. Log potential data-loss and accuracy risks.

## No faux deliverables
No placeholder bodies, fake interiors, stand-in engines, or screenshot-only progress in place of approved features. Diagnostics are allowed when explicitly identified as non-deliverables. No premature success claims.

## Ownership and provenance
Do not assume permission to redistribute BeamNG base assets or any third-party work. Original project creations should be tracked; third-party assets must be preapproved and provenance-recorded. A public repo is **not** a license grant.

## Engineering requirements
Physical JBeam and visual geometry must agree. Validate frame/join stiffness, structural continuity, wheel/axle clearance, laden/unladen ride height, suspension travel, traction, braking, cooling, and stable crash response as capabilities become testable. Record measurable results rather than assertions.

## Versions and rollback
Use semantic versioning once distributable builds exist. Every delivered mod update gets a new version; preserve previous working ZIP; fail safely on interrupted deployment. Record deployed version, commit, tests and rollback path. Do not automatically launch the game.

## Documentation routine
Before each task: read project docs. After each task: document verified findings, changed files, uncertainties, next actions and how to resume. Keep updates concise and useful; make checkpoint commits for validated milestones.
