# FivePD Korean resource delivery

`FivePD-Korean-Download.zip` is an AES-256 encrypted ZIP for the repository owner. Use 7-Zip to extract it. The password is delivered separately in the private conversation and is not stored in this repository.

The archive contains a development candidate, not a guarantee of game compatibility. Back up existing resources and databases and test on a separate Windows FiveM server first. Native HUD and some native English text remain unverified or unfinished.

SHA-256 of the encrypted ZIP: `bbcd0f28c55b0e23695527bfe7c7f28b9a7ca52f82a2e1bbd1ba074c86d7f37d`

No unencrypted resource, database, runtime log, secret, or customized server configuration is committed here.

## Required SQLite vehicle-filter hotfix (2026-10-30)

Apply `FivePD-SQLite-Hotfix-20261030.zip` after the original candidate. It contains one replacement server DLL, instructions and source diff. The vehicle-type filter previously supplied an unnamed scalar to a named SQL parameter; the resulting SQLite error could stop FivePD. Existing DB, permissions, configuration and localization are not modified. 34 automated tests passed; actual Windows FiveM validation remains pending. The password is the same one shared privately for the original archive.

## Optional standalone weapon wheel (2026-10-30)

Use **`FivePD-WeaponWheel-v1.1.0.zip`** for the current standalone `fivepd_weaponwheel` resource. It contains Korean installation instructions, user-supplied weapon icons, full source and verification results. Install the resource folder and add `ensure fivepd_weaponwheel` after FivePD in `server.cfg`. This package does not replace existing FivePD files or the SQLite hotfix. Use 7-Zip and the same privately shared archive password.

Hold Tab, point at a weapon, use the scroll wheel to cycle weapons within the slot, and release Tab to equip. Escape cancels. The sound plays only when changing to a different owned weapon. 33 Lua behavior checks, 7 JavaScript checks, 6 server/native-footer checks and browser interactions at four resolutions passed. Actual Windows FiveM behavior, the final audio mix and pixel-level matching of the native footer font still require game validation.

Version 1.1.0 preserves the focus/input fix from 1.0.1. It applies 98 unchanged supplied PNGs (97 selectable weapon mappings), adds persistent outward selection animation, increases size 10% over 1.0.1, removes the exterior shade, and detects real installed components from 215 known part identifiers. A native bottom-centre footer shows FivePD in blue followed by its resource version, server player count/capacity, and KST time. No player identifiers, user logs, private config or databases are included.

Equip audio is derived from **Guns by Gary**, hosted by OpenGameArt and submitted by qubodup: https://opengameart.org/content/handling-guns . Source recordings and derived compact/long-weapon Foley are CC BY-SA 3.0: https://creativecommons.org/licenses/by-sa/3.0/ . Attribution, source excerpts and processing recipe are included in the archive. The samples were trimmed, layered, filtered, compressed and given short stereo early reflections. Weapon component identifier data is from DurtyFree/gta-v-data-dumps.

Replace the entire old `fivepd_weaponwheel` folder, including `config.lua`, `fxmanifest.lua`, `web/`, and the new `server.lua`/`status_client.lua`. Older archives are retained for history; use 1.1.0 for installation.
