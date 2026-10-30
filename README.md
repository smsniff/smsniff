# FivePD Korean resource delivery

## Current v2.2.0 — Korean records, station staff and locker uniforms

[Download the incremental update](https://github.com/smsniff/smsniff/raw/refs/heads/fivepd-korean-delivery/FivePD-Interface-NPC-Update-v2.2.0.zip) — ordinary ZIP, no password, approximately1MB, for the existing v2.1.x installation. Stop the server and merge `[fivepd]` and `fivepd_fieldops` into `D:\txData\FiveMBasicServerCFXDefault_E351AA.base\resources`; restart and reconnect. Keep bracketed names, Config, Data and DB. `fivepd_update_status` reports2.2.0. The cumulative `FivePD-Operations-UI-Latest.zip` and versioned `FivePD-Operations-Update-v2.2.0.zip` contain the same changes plus earlier updates. The incremental archive contains only changed runtime files and a short Korean guide, and leaves the unchanged wheel alone.

Vehicle records now localize all160 emitted color names and bundled GTA model/manufacturer labels; the old Brand field actually stored model codes, so model and real manufacturer are shown separately (Seminole / Canis). Stored values, plates and custom addon identifiers remain unchanged. Document names and dates are localized, as are report default labels/actions, loading text and related-person gender/date choices. Report IDs and user-written narratives remain unchanged. Existing English shooter titles are displayed and searched in Korean. Incident IDs show short prefixes, extend collisions on the current page, and expose the full ID on hover without changing references.

Language loading uses the actual resource root, isolates invalid optional language files and removes the developer TEST locale. Updated Korean and English runtime dictionaries are included. The settings list shows Korean language names and includes the currently selected language with a checkmark instead of hiding it.

Station beacons are replaced with local role-appropriate NPCs and idle scenarios. Staff stream within65m and despawn beyond90m, with a12-actor cap, bounded model loading and cleanup; no network actors are added. Approach and pressE for existing authorized equipment/vehicle/desk menus or the locker. The server checks membership, access, active health/session, on-foot state and locker distance for each wardrobe request. Members may dress before starting duty. The wardrobe saves the original outfit once per session, cancels delayed changes if injured or moved away, and restores clothing on resource stop. Clothing is supported for native male/female freemode models; unsupported character models receive an explanation and are never forcibly changed. Model, face, hair, health, armor and weapons are untouched. Modules for streaming, presets, wardrobe native logic, UI and server authorization are separate.

[Download the Mission Row MLO registration patch](https://github.com/smsniff/smsniff/raw/refs/heads/fivepd-korean-delivery/FivePD-MissionRow-MLO-Compat-v1.0.1.zip) — approximately2.5KB. **The original MLO assets are not included or rehosted.** First extract the user-supplied `mission_row_station_rampart.zip` into `resources/[maps]/mission_row_station_rampart`, with `fxmanifest.lua` and `stream` directly inside. Then merge this compatibility patch's `[maps]` folder into `resources`. Before the existing FivePD startup lines, add once:

```cfg
set fivepd_missionrow_layout "rampart"
ensure mission_row_station_rampart
```

Restart the server and reconnect. `missionrow_status` reports essential map file presence and active paths. The patch registers all six YTYPs explicitly. The opt-in profile requires a started map and actual core assets, and moves only unchanged default armory/locker points in memory; custom coordinates and persisted settings are preserved. The replacement MLO's deliberate removal of the original interior is retained. Other Mission Row replacement maps should not run simultaneously.

Validation: original83,143,957-byte MLO ZIP CRC and all252 RSC7 streams passed; binary metadata was inspected for placement, rooms and gun lockers. Actual CitizenFX server/client builds,56 existing SDK tests,29 configuration/recovery/catalog/profile tests,139 server-adapter simulation checks and native checks20 lifecycle/14EMS/12teleport/17NPC/22wardrobe passed. The NUI suite passed173 tests with2 existing skipped; the additional selected-language regression and report-form check passed. Compiled record lookup/report creation/language save, existing operations/map/radio/logo workflows, medical and wardrobe flows passed at1366×768,1920×1080,2560×1440 and3440×1440. The incremental ZIP was overlaid on v2.1.1 and matched every cumulative runtime file while preserving sample private recovery/configuration. Actual Windows FiveM rendering, doors/collision, NPC ground alignment, terrain, multiplayer navigation and in-game performance remain unverified.

## Earlier hotfix v2.1.1 — field initialization and teleport

[Download FivePD-FieldOps-Fix-v2.1.1.zip](https://github.com/smsniff/smsniff/raw/refs/heads/fivepd-korean-delivery/FivePD-FieldOps-Fix-v2.1.1.zip) — ordinary ZIP, no password, 0.44 MB. For an existing v2.1.0 installation, stop the server and merge its `[fivepd]` folder into `D:\txData\FiveMBasicServerCFXDefault_E351AA.base\resources`. Restart and reconnect. `fivepd_update_status` reports 2.1.1. Keep bracketed names and all Config/Data/DB files. No configuration reset or server.cfg change is required.

Json.NET appended configured stations to the constructor's default station list. The valid shipped one-station configuration therefore became duplicate mission-row stations and failed validation, blocking the entire field service including teleport. The configured station list now replaces the fallback list; omitted lists still receive the default and genuinely empty/duplicate lists remain invalid. Only the server DLL and two deployment identification files changed. User settings and recovery data are preserved.

Validation: reproduced three failing configuration regression cases before the fix; all26 configuration/recovery tests,130 actual server-adapter checks with the shipped configuration, and56 existing SDK server tests now pass. Actual CitizenFX SDK build succeeded. The cumulative v2.1.1 archive differs from v2.1.0 in exactly these three runtime files and installation text. ZIP CRC, encryption absence and config/data exclusion were checked. Live Windows FiveM behavior remains to be checked after installation.

[FivePD-Operations-UI-Latest.zip](https://github.com/smsniff/smsniff/raw/refs/heads/fivepd-korean-delivery/FivePD-Operations-UI-Latest.zip) and `FivePD-Operations-Update-v2.1.1.zip` include the same fix for cumulative installation.

## Previous cumulative update v2.1.0 — complete wheel, readable UI, URL images and admin teleport

**[Download FivePD-Operations-UI-Latest.zip](https://github.com/smsniff/smsniff/raw/refs/heads/fivepd-korean-delivery/FivePD-Operations-UI-Latest.zip)** — ordinary ZIP, no password, approximately9.9MB. Versioned filename: `FivePD-Operations-Update-v2.1.0.zip`. Runtime files and a short Korean installation/use guide only.

Stop the server, back up outside `resources`, then merge the archive's `[fivepd]` and `fivepd_fieldops` folders into `D:\txData\FiveMBasicServerCFXDefault_E351AA.base\resources`. Keep the bracketed group. The actual resources are:

- `resources/[fivepd]/fivepd` — existing core update.
- `resources/[fivepd]/fivepd_weaponwheel` — complete weapon-wheel1.2.0, a sibling of the core, with its own manifest/data/UI/fonts/audio. Do not put it inside the core folder.
- `resources/fivepd_fieldops` — existing field operations/medical resource.

Keep the existing FivePD startup configuration, and ensure `fivepd_fieldops` and `fivepd_weaponwheel` start after the core. Restart and reconnect. Core Data, DB, general/custom configuration and unchanged fieldops configuration are not included. The complete wheel includes its default config; back up and restore any wheel-specific custom settings if applicable. Original dependency versions and SQLite vehicle filtering fix remain intact.

The core window is narrower, important text is larger, and map viewports retain4:3 aspect ratio. Admin-only map point/marker teleport uses server-owned tickets tied to player/ped/bucket/deadline, checks role/access/activity/on-foot state again before completing, streams ground safely and releases cancelled/expired loading state. Ordinary players cannot initiate or finish another player's request. Department/rank editors now accept public HTTP(S) direct PNG/JPG/WebP URLs with preview instead of file uploads; legacy saved PNG images still work. The server validates references and never fetches arbitrary URLs. Recommended256×256px and200KB; HTTPS recommended.

The previous two-file wheel compatibility patch could leave an incomplete or mismatched wheel. This release supplies the complete resource. Early client diagnostics remain available if a later data/UI script fails, missing old configuration fields receive defaults, frontend import errors are surfaced, native Tab input can open the wheel if the saved command mapping did not fire, and medical/teleport locks remain respected. Game F8: `weaponwheeldebug`. Server console: `weaponwheel_status` (active path and file completeness), `fivepd_active_path` (core2.1.0 and wheel1.2.0 location/version).

Validation: actual CitizenFX SDK build;56 server tests;128 server adapter simulation checks;12 native teleport checks including queued-cancellation races;20 lifecycle and14 physical-AI native checks;37 wheel Lua,7 wheel model and6 footer checks;162 NUI tests passed (2 pre-existing skipped). Compiled operations/URL/teleport-permission workflows, medical UI and complete wheel interactions passed at1366×768,1920×1080,2560×1440 and3440×1440. Package CRC, literal bracketed layout, complete wheel file identity and preservation of existing Data/configuration were verified. Live FiveM gameplay/streaming behavior, terrain/AI navigation and performance still require in-game verification.

## Earlier folder-layout correction v2.0.1

The user's existing running core is inside `resources/[fivepd]/fivepd`. **Keep the `[fivepd]` group name including brackets.** Copying `Libraries` and `fxmanifest.lua` into the outer group does not update the nested `fivepd` resource. The previous root-level destination advice was incorrect for this installation.

After already applying v2.0.0, use **[FivePD-Core-Path-Fix-v2.0.1.zip](https://github.com/smsniff/smsniff/raw/refs/heads/fivepd-korean-delivery/FivePD-Core-Path-Fix-v2.0.1.zip)**. Stop the server, back up outside `resources`, then merge the archive's `[fivepd]` and `fivepd_fieldops` folders into `resources`. It updates the nested core and preserves the bracketed group and user data. The already started `fivepd_fieldops` resource stays in its existing location. Keep existing FivePD startup settings and ensure `fivepd_fieldops` is started after the core. Restart the server and reconnect.

For the complete cumulative patch, **[FivePD-Operations-UI-Latest.zip](https://github.com/smsniff/smsniff/raw/refs/heads/fivepd-korean-delivery/FivePD-Operations-UI-Latest.zip)** now contains the corrected core layout plus the same field resource and wheel compatibility files. The wheel files must be merged into the existing wheel resource at its actual location. Do not rename bracketed group folders or delete existing resources.

A read-only server command `fivepd_update_status` prints the active core path, package `2.0.1`, the unchanged `2.0.0` compiled UI identity, and field resource state. It does not expose private data or alter gameplay. A simulated extraction matching the screenshot's nested layout passed, preserved existing user-data and outer files, and the diagnostic command's source checks and stale/missing UI cases passed. Gameplay DLL and compiled UI bytes are unchanged from v2.0.0; live FiveM behavior remains subject to in-game verification.

The independent field-resource command `fivepd_active_path` also reports the actual core path and `core update = 2.0.1`, even if the core bootstrap has a problem. It is console-only and read-only.

## Superseded cumulative operations update v2.0.0 (2026-10-30)

**[Download FivePD-Operations-UI-Latest.zip](https://github.com/smsniff/smsniff/raw/refs/heads/fivepd-korean-delivery/FivePD-Operations-UI-Latest.zip)** — ordinary ZIP, no password. The versioned archive is `FivePD-Operations-Update-v2.0.0.zip`. This updates an existing Korean FivePD installation and the already installed weapon wheel; it includes all previous operations UI changes.

Runtime files and a short Korean `적용법.txt` only. Stop the server, back up the current resource folders, and merge/overwrite the included `fivepd`, `fivepd_fieldops`, and `fivepd_weaponwheel` folders under `D:\txData\FiveMBasicServerCFXDefault_E351AA.base\resources`. Keep existing folders, dependencies, DB, saved data, and custom configuration. The wheel folder contains two compatibility/font updates and must be merged into the installed wheel. `D:\server` is unchanged. Run in this order:

```cfg
ensure fivepd
ensure fivepd_fieldops
ensure fivepd_weaponwheel
```

B opens the redesigned officer desk with duty/support actions and a live incident/officer map. F4 is a compact field menu with fixed duty controls; F6 is officer radio. Administrators can register department logos and global/department rank insignia, with format/size guidance and shared validation/cache. Mission Row provides station entry, designated armory and garage access. The same supplied station PNG is included for MDT and GTA native map textures.

The independent `fivepd_fieldops` resource provides station selection, downed/death UI and physical EMS workers. Server-side FivePD modules remain authoritative for permissions, recovery deadlines, CPR and routing buckets. Downed players have five minutes for treatment and an officer-down emergency action. On-duty officers can start timed CPR nearby. Extra firearm damage can finish the patient. Death waits fifteen seconds before the fixed station respawn, with a slow original motivational line, quiet Foley and bundled fonts. When no healthy on-duty responder is available, a capped server-controlled AI ambulance approaches from a remote road and a paramedic performs physical CPR. Map polling stops when closed, medical timers stop when inactive, and workers/entities have explicit cleanup.

Validation: actual CitizenFX SDK server/client builds, 47 existing server tests, 20 recovery-rule tests, 92 server/native simulation checks, 20 native lifecycle checks, 14 physical AI checks, 34 weapon wheel checks, and 162 NUI tests passed (2 existing skipped). Compiled UI interactions passed at four resolutions, including image upload/synchronization, map removal/routing, duty/radio and injury/death flows. Simulations do not establish actual Windows FiveM multiplayer/OneSync behavior, AI navigation, final native texture appearance, or in-game performance; these still need live verification.

No user database, runtime logs, saved branding/recovery data, credentials, source recordings, source maps, tools or verification files are included. Existing SQLite vehicle-filter correction and original dependency versions are preserved.

## Earlier basic operations UI v1.0.0 (2026-10-30)

Download **[FivePD-Operations-UI-v1.0.0.zip](https://github.com/smsniff/smsniff/raw/refs/heads/fivepd-korean-delivery/FivePD-Operations-UI-v1.0.0.zip)**. This earlier release is a small, **unencrypted update for the existing Korean FivePD installation**, containing only replacement client/server DLLs, changed compiled NUI files, one runtime alert sound and a short Korean installation guide. Merge its `fivepd` directory into the existing resource while the server is stopped, restart and reconnect. It is separate from the standalone weapon-wheel update below.

B opens the operations desk with a duty shortcut and vehicle/equipment links. F4/F10/F11 use mouse-friendly menus with shared navigation. FivePD administrators can select and save department logos in department settings; logos persist in `fivepd/Data/department-branding.json` and appear for department members. F6 opens the duty-only officer radio chat and alert waypoint action. Server-authoritative backup/panic packets reach every authorized on-duty connected officer, including officers without an assigned patrol unit and other departments. Alerts show the requesting officer's position; panic adds a restrained emergency tone. Dispatch system messages type progressively; chat is rendered as plain text. Existing incident backup/F1 assignment is preserved.

The original SQLite vehicle-filter fix remains in the replacement server DLL. No DB, permissions, custom configuration, weapon-wheel files, source recordings or test tools are included or overwritten. Keep the generated branding JSON when updating. This patch needs the original resource's unchanged dependencies and assets.

Validation: 47 server tests, 159 NUI tests (2 existing skipped), 14 server transport/native simulation checks, 13 client native-boundary simulation checks, and Chromium interaction flows at 1366×768, 1920×1080, 2560×1440 and 3440×1440 passed. Replacement assemblies retain the original assembly versions and dependency references. Windows FiveM multiplayer behavior and the final in-game audio mix have not been directly verified.

## Earlier downloads

`FivePD-Korean-Download.zip` is an AES-256 encrypted ZIP for the repository owner. Use 7-Zip to extract it. The password is delivered separately in the private conversation and is not stored in this repository.

The archive contains a development candidate, not a guarantee of game compatibility. Back up existing resources and databases and test on a separate Windows FiveM server first. Native HUD and some native English text remain unverified or unfinished.

SHA-256 of the encrypted ZIP: `bbcd0f28c55b0e23695527bfe7c7f28b9a7ca52f82a2e1bbd1ba074c86d7f37d`

No user database, runtime log, secret, or customized server configuration is committed here. Earlier original-resource archives remain encrypted. The standalone weapon wheel is now provided as an ordinary unencrypted ZIP at the user's request.

## Required SQLite vehicle-filter hotfix (2026-10-30)

Apply `FivePD-SQLite-Hotfix-20261030.zip` after the original candidate. It contains one replacement server DLL, instructions and source diff. The vehicle-type filter previously supplied an unnamed scalar to a named SQL parameter; the resulting SQLite error could stop FivePD. Existing DB, permissions, configuration and localization are not modified. 34 automated tests passed; actual Windows FiveM validation remains pending. The password is the same one shared privately for the original archive.

## Optional standalone weapon wheel (2026-10-30)

Current download: **`FivePD-WeaponWheel-Latest.zip`** (full resource) or **`FivePD-WeaponWheel-Patch-Latest.zip`** (cumulative patch from 1.1.0). These are ordinary ZIPs without a password. They contain only the runtime `fivepd_weaponwheel` folder and a short Korean `적용법.txt`; tools, audio source recordings and verification files are excluded. Windows built-in Extract All works. Versioned 1.1.1 FULL/PATCH filenames are also retained.

Version 1.1.1 adjusts wheel/icon proportions, bundles a local condensed digit font, redraws the thin component badge outlines, enlarges footer text slightly and removes parentheses around its version. The reference's exact original font/component artwork was unavailable; this is a visual reconstruction, not a certified pixel-identical copy. Apply the patch only to 1.1.0 or later in this series; otherwise use the full resource ZIP.

Hold Tab, point at a weapon, use the scroll wheel to cycle weapons within the slot, and release Tab to equip. Escape cancels. The sound plays only when changing to a different owned weapon. 33 Lua behavior checks, 7 JavaScript checks, 6 server/native-footer checks and browser interactions at four resolutions passed. Actual Windows FiveM behavior, the final audio mix and pixel-level matching of the native footer font still require game validation.

Version 1.1.0 preserves the focus/input fix from 1.0.1. It applies 98 unchanged supplied PNGs (97 selectable weapon mappings), adds persistent outward selection animation, increases size 10% over 1.0.1, removes the exterior shade, and detects real installed components from 215 known part identifiers. A native bottom-centre footer shows FivePD in blue followed by its resource version, server player count/capacity, and KST time. No player identifiers, user logs, private config or databases are included.

Equip audio is derived from **Guns by Gary**, hosted by OpenGameArt and submitted by qubodup: https://opengameart.org/content/handling-guns . Derived compact/long-weapon Foley is CC BY-SA 3.0: https://creativecommons.org/licenses/by-sa/3.0/ . Attribution is included under `web/sounds/`. The samples were trimmed, layered, filtered, compressed and given short stereo early reflections. Source recordings and tools remain in the workspace, outside the runtime ZIP. Weapon component identifier data is from DurtyFree/gta-v-data-dumps. The bundled digit font is a renamed numeric subset of Bebas Neue, SIL OFL; its license is included.

For a full install, replace the entire `fivepd_weaponwheel` folder. For the 1.1.0-based patch, merge/overwrite its resource folder into the existing installation. Older archives are retained for history; use 1.1.1 or the Latest links for current installation.
