# FivePD Korean resource delivery

`FivePD-Korean-Download.zip` is an AES-256 encrypted ZIP for the repository owner. Use 7-Zip to extract it. The password is delivered separately in the private conversation and is not stored in this repository.

The archive contains a development candidate, not a guarantee of game compatibility. Back up existing resources and databases and test on a separate Windows FiveM server first. Native HUD and some native English text remain unverified or unfinished.

SHA-256 of the encrypted ZIP: `bbcd0f28c55b0e23695527bfe7c7f28b9a7ca52f82a2e1bbd1ba074c86d7f37d`

No unencrypted resource, database, runtime log, secret, or customized server configuration is committed here.

## Required SQLite vehicle-filter hotfix (2026-10-30)

Apply `FivePD-SQLite-Hotfix-20261030.zip` after the original candidate. It contains one replacement server DLL, instructions and source diff. The vehicle-type filter previously supplied an unnamed scalar to a named SQL parameter; the resulting SQLite error could stop FivePD. Existing DB, permissions, configuration and localization are not modified. 34 automated tests passed; actual Windows FiveM validation remains pending. The password is the same one shared privately for the original archive.
