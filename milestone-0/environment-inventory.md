# Environment inventory

Audit date: 2026-10-15. Inspection was read-only. Paths containing the Windows account name are written with `%USERPROFILE%`.

## Tooling

| Item | Status | Version / evidence | Sanitized location |
|---|---|---|---|
| Git | **VERIFIED LOCAL — working** | `git version 2.54.0.windows.1`; repository queries succeeded | `C:\Program Files\Git\cmd\git.exe` |
| Python | **VERIFIED LOCAL — working** | CPython `3.12.6`; version command and in-memory ZIP/XML parsing succeeded | `C:\Program Files\Python312\python.exe` |
| Python launcher | **VERIFIED LOCAL — working** | Reports Python `3.12.6` | `C:\Windows\py.exe` |
| Blender | **VERIFIED LOCAL — working CLI** | Blender `4.5.3 LTS`, build date 2025-09-09; `--version` succeeded | `C:\Program Files\Blender Foundation\Blender 4.5\blender.exe` |
| PowerShell | **VERIFIED LOCAL — working** | Used for the audit; a sandbox provider emitted a harmless `InitializeDefaultDrives` warning on many invocations | System-provided |
| Windows tar/bsdtar | **VERIFIED LOCAL — working** | Listed and streamed ZIP members without extraction | System-provided `tar` command |
| 7-Zip CLI | **NOT FOUND ON PATH** | `7z` command unavailable; not required | — |

No software or Python package was installed or upgraded.

## BeamNG.drive

| Item | Finding | Status |
|---|---|---|
| Registration | Steam App ID `284160` is registered as BeamNG.drive | **VERIFIED LOCAL** |
| Installation | `%ProgramFiles(x86)%\Steam\steamapps\common\BeamNG.drive` | **VERIFIED LOCAL** |
| Executable metadata | Product/File version `0.39.4.0.20972` | **VERIFIED LOCAL; executable not launched** |
| Build evidence | `integrity.json`: `buildbot build 20972 ... 07/08/2026`; Steam manifest build ID `24617469` | **VERIFIED LOCAL** |
| Steam state | Installed depot `284161`, manifest `5975039348266591145`; manifest reports state flag `4` | **VERIFIED LOCAL** |
| Vanilla vehicle content | `content\vehicles\*.zip` readable; Covet, Lansdale, H-Series and common archives inspected by streaming selected members | **VERIFIED LOCAL** |
| Game runtime | Not started and not tested, per authorization | **IN-GAME NOT TESTED** |

### User folder and mods path

- Installation `startup.ini` exists and has an empty `UserPath`, so it does not supply a custom override. **VERIFIED LOCAL.**
- `%USERPROFILE%\Documents\BeamNG.drive` exists. Its old logs explicitly identify that same directory as the default user path, but those logs date from 2021. **VERIFIED LOCAL, stale runtime evidence.**
- `%USERPROFILE%\Documents\BeamNG.drive\mods` exists and contained two top-level ZIPs plus one unpacked mod at audit time; no filename matched Campette/Covet-Campette. Some contents had 2026 modification dates. **VERIFIED LOCAL filesystem state.**
- The current-version `%LOCALAPPDATA%\BeamNG.drive` candidate did not exist. **VERIFIED LOCAL.**
- Because BeamNG was not launched and no current log states the resolved user path, `%USERPROFILE%\Documents\BeamNG.drive\mods` is an **observed candidate, not a confirmed active runtime mods path**. Deployment is outside Milestone 0 regardless.

Safe later confirmation, only when the owner authorizes runtime testing and manually starts/exits BeamNG: inspect the newest `beamng.log` for `Virtual Filesystem: user path`, then confirm the corresponding `mods` directory. Do not infer the active path from recency alone.

## Repository baseline

- Remote: `https://github.com/sczahra/beamng-covet-campette.git`
- Branch: `main`
- Starting commit: `a0ff7e30c12b363b606d893723707d5e158322c4`
- Starting tree: clean immediately after cloning into the initially empty workspace.
- No pre-existing user changes were present to overwrite or discard.

## Access limitations

- No BeamNG runtime measurements, vehicle spawning, node visualization, weight-pad readings, suspension cycling, or driving tests were performed.
- Installed archives were never modified. Selected text members were streamed for inspection; the DAE was parsed in memory. No vanilla asset was copied into the repository.
- Windows sandboxing changed the process-level `%LOCALAPPDATA%`; actual shell-folder locations were cross-checked through the registry and explicit read-only existence tests.

