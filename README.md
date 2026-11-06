# petpiano-ble

Reverse-engineering the Bluetooth LE protocol of the Pet Piano so its owners
can build their own app for it.

The Pet Piano is a miniature piano and treat dispenser for cats and dogs,
made by Aaron Benitez (Aaron's Animals). The official companion app is called
Purrfect Pitch. It works, but it is not good, so this project maps out how the
piano talks over Bluetooth and documents everything needed to write a
replacement app.

This is an independent project by a Pet Piano owner. It is not affiliated
with Pet Piano, Aaron's Animals, or Smart Solutions for Home.

## Status

Early. As of November 6, 2026:

- The piano was confirmed to talk over Bluetooth LE, not WiFi. The official
  FAQ says the same: it runs on Bluetooth now, with WiFi planned later.
- The piano advertises as `PetPiano`, MAC `D0:EF:76:ED:A6:16` (Espressif).
- Two BLE services were found. One is the standard Alert Notification
  Service. The other is a custom service with four characteristics. That
  custom service is the control channel.
- What each characteristic does is still unknown. See `PROTOCOL.md`.

No one had published a protocol map for this device before this project.

## Hardware

The piano runs on an ESP32 (Ai-Thinker ESP32-WROOM-32E-N16, 16 MB flash).
The board also has an I2S audio amp (MAX98357A), a 16-bit I/O expander
reading the 18 keys (MCP23017), a DC motor driver for the dispenser
(DRV8838), a real-time clock (DS3231), a Hall sensor, a microSD slot for
sounds, and a 6-pin programming header (JP1). Full parts lists are in
`hardware/BOM.md`.

The hardware itself started as an open DIY project by Sebastian at Smart
Solutions for Home, who built the original piano for Aaron's Animals and
published a step-by-step build guide with free 3D models. The commercial
product came later. The open hardware files are summarized in
`hardware/manifest.md`.

## Repo layout

- `PROTOCOL.md` - everything known about the BLE protocol, and what is
  still unknown.
- `hardware/BOM.md` - parts lists from the open hardware package.
- `hardware/manifest.md` - the original binary packages (Gerbers, 3D
  models), with SHA-256 hashes and provenance.
- `captures/` - raw logs from BLE exploration sessions.
- `REBUILD.md` - how this repo is put together and how to rebuild it.

## A note on the binary files

The original Gerber, BOM PDF, and 3D model packages are binary files, and
the tooling used to publish this repo only pushes text. Their contents are
preserved here as text (BOM tables, file listings, hashes) in `hardware/`.
The originals are the free DIY package from Smart Solutions for Home. See
`hardware/manifest.md` for details.

## License

MIT. See `LICENSE`.
