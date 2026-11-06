# Pet Piano BLE protocol

Everything known so far about how the Pet Piano talks over Bluetooth LE.
Captured against a bought retail unit, November 5, 2026.

## Device

| Field | Value |
| --- | --- |
| Advertised name | `PetPiano` |
| BLE MAC | `D0:EF:76:ED:A6:16` |
| Vendor | Espressif Inc. (OUI) |
| Signal at capture | -58 dBm (strongest nearby) |
| Transport | Bluetooth LE only |
| Official app | Purrfect Pitch (iOS, by Aaron Benitez) |

The piano accepts one BLE connection at a time. While the official app is
connected, the piano stops advertising and will not show up in a scanner.
Force close the official app before scanning with nRF Connect.

The official FAQ confirms the transport: the piano currently operates off
of Bluetooth, with WiFi planned later for remote access and updates.

## Services

Two services were discovered on November 5, 2026 (nRF Connect log in
`captures/nrf-connect-2026-11-05.log`).

### 1. Alert Notification Service (standard, 0x1811)

Standard BLE service with these characteristics:

- Supported New Alert Category
- New Alert
- Supported Unread Alert Category
- Unread Alert Status
- Alert Notification Control Point

Probably boilerplate from the BLE stack. Not yet known to carry any
piano-specific function.

### 2. Custom service `60462F12-9543-9999-12C8-58B459A2712D`

This is the control channel. Four characteristics, no descriptors:

| Short name | Full UUID |
| --- | --- |
| 34 | `34333333-2222-2222-1111-111100000000` |
| 35 | `35333333-2222-2222-1111-111100000000` |
| 36 | `36333333-2222-2222-1111-111100000000` |
| 37 | `37333333-2222-2222-1111-111100000000` |

## Unknowns (in order of priority)

1. Properties of each of the four characteristics (Read, Write, Notify,
   or a mix). Read them in nRF Connect.
2. Current values of each characteristic.
3. What the piano sends when a key is pressed. Enable notifications on
   the Notify-capable characteristics, then press a key and record what
   arrives.
4. What the official app writes when changing a setting (Tutor mode,
   daily portion limit, play times, melody assist, song selection).
   Record the bytes for each action.
5. Whether any characteristic needs pairing, bonding, or a write
   handshake before it accepts commands.

## How to capture

1. Force close Purrfect Pitch.
2. Open nRF Connect, scan, connect to `PetPiano`.
3. Expand service `60462F12-9543-9999-12C8-58B459A2712D`.
4. For each of the four characteristics, note its properties and read
   its value.
5. Enable notifications where offered, press a piano key, and save the
   log. Export the log and add it under `captures/`.

## Hardware map (from the PCB BOM)

Useful if the fallback plan is ever needed: reflash the ESP32 with custom
firmware instead of talking to the stock firmware.

| Part | Role |
| --- | --- |
| U1 Ai-Thinker ESP32-WROOM-32E-N16 | Main MCU, 16 MB flash |
| U4 MAX98357A | I2S audio amplifier (speaker) |
| U8 MCP23017 | 16-bit I/O expander, reads the 18 keys |
| U2 DRV8838 | DC motor driver (treat dispenser) |
| U3 DS3231 | Real-time clock (scheduled feedings) |
| U7 SL353LT | Hall sensor (dispenser rotation) |
| J5 | Coin cell holder (RTC backup) |
| JP2 | microSD card slot (sounds and songs) |
| JP1 | 6-pin header, likely the programming header |
| S1-S18 | Panasonic ESE11SV1 key switches |

Reflashing risks bricking the unit and losing the stock tutor mode and
songs. Back up the stock firmware with esptool (`read_flash`) before
flashing anything.
