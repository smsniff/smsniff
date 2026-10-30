# FivePD Korean resource delivery

## Current folder-layout correction v2.0.1

The user's existing running core is inside `resources/[fivepd]/fivepd`. **Keep the `[fivepd]` group name including brackets.** Copying `Libraries` and `fxmanifest.lua` into the outer group does not update the nested `fivepd` resource. The previous root-level destination advice was incorrect for this installation.

After already applying v2.0.0, use **[FivePD-Core-Path-Fix-v2.0.1.zip](https://github.com/smsniff/smsniff/raw/refs/heads/fivepd-korean-delivery/FivePD-Core-Path-Fix-v2.0.1.zip)**. Stop the server, back up outside `resources`, then merge the archive's `[fivepd]` folder into the existing `resources/[fivepd]`. It updates the nested core and preserves the bracketed group and user data. The already started `fivepd_fieldops` resource stays in its existing location. Keep existing FivePD startup settings and ensure `fivepd_fieldops` is started after the core. Restart the server and reconnect.

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
