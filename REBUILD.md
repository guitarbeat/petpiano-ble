# REBUILD.md

Living rebuild manual for the petpiano-ble repo. Updated in the same breath
as every change.

## Folder map

- `README.md` - project overview and status.
- `PROTOCOL.md` - BLE protocol findings and unknowns.
- `hardware/BOM.md` - parts lists from the open hardware package.
- `hardware/manifest.md` - original binary packages, hashes, provenance.
- `hardware/originals/` - local-only copies of the original binary
  packages. NOT pushed to GitHub (binary files cannot go through the
  GitHub tooling used here).
- `captures/` - raw BLE session logs.
- `LICENSE` - MIT.

## External dependencies and accounts

- GitHub account `guitarbeat` (Aaron Lorenzo Woods). Repo is public:
  `github.com/guitarbeat/petpiano-ble`.
- GitHub access is through Muse's GitHub connector (OAuth as guitarbeat,
  plus the Muse GitHub App installation). No personal access tokens are
  stored in this repo.
- nRF Connect for Mobile (free, Nordic Semiconductor) for BLE exploration
  from iOS.
- The Pet Piano hardware itself, plus the Purrfect Pitch app for
  ground-truth comparisons.

## Setup sequence

1. Clone `https://github.com/guitarbeat/petpiano-ble.git`.
2. Read `README.md` and `PROTOCOL.md`.
3. To keep exploring: force close Purrfect Pitch, connect to `PetPiano`
   in nRF Connect, follow the capture steps in `PROTOCOL.md`, and add new
   logs under `captures/`.
4. To publish updates: edit the text files locally, then push with the
   GitHub `push-files` flow (text only, max 16 MiB, max 2000 files).
   Binary files cannot be pushed with this tooling; document them in
   `hardware/manifest.md` instead.

## Decision log

- 2026-11-06: Repo created public as `guitarbeat/petpiano-ble`. Public
  was Aaron's choice; the point is to be the first public protocol map
  for this device.
- 2026-11-06: Binary packages (Gerbers, 3D models, BOM PDFs) are NOT in
  the repo. The GitHub push tooling used here accepts UTF-8 text only.
  Their contents are preserved as text (BOM tables, listings, SHA-256
  hashes) and the originals are kept in `hardware/originals/` locally.
  If the zips need to be in the repo, upload them through the GitHub web
  UI as a follow-up.
- 2026-11-06: MIT license. Standard pick for a findings repo; change it
  if Aaron wants a different license.
- 2026-11-05: Investigation route chosen is talking to the stock
  firmware over BLE, not reflashing. Reflashing stays the fallback
  because it risks bricking and losing stock features.
- 2026-11-05: No public protocol map, firmware repo, or Home Assistant
  integration for the Pet Piano was found. The DIY open hardware package
  from Smart Solutions for Home is hardware only, no firmware source.

## Pointers to data and credentials (never the secrets)

- BLE identity: name `PetPiano`, MAC `D0:EF:76:ED:A6:16`.
- Custom service `60462F12-9543-9999-12C8-58B459A2712D`, characteristics
  `34333333-...`, `35333333-...`, `36333333-...`, `37333333-...`
  (full UUIDs in `PROTOCOL.md`).
- Original hardware files: `hardware/originals/` (local only).
- No credentials are stored in this repo.

## Smoke test

After a rebuild or a push, check on github.com that `README.md`,
`PROTOCOL.md`, and `hardware/BOM.md` render, and that the latest commit
is on the `main` branch.

## Known gaps

- Characteristic properties and values are not yet captured.
- No key-press notification capture yet.
- No mapping of official-app actions to bytes written.
- Binary packages are not in the repo (see decision log).
