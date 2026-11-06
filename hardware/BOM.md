# Pet Piano hardware BOMs

Transcribed from the open hardware package (PetPiano v.1.0 BOM and
PetPiano v.1.0 PCB BOM, February 2024 files). The original PDFs are binary
and live in `hardware/originals/` locally; see `manifest.md`.

## Assembly BOM (PetPiano v.1.0)

| No. | Qty | Name | Category | Material | Notes |
| --- | --- | --- | --- | --- | --- |
| 1 | 1 | Right | Enclosure | MDF | Custom |
| 2 | 1 | Left | Enclosure | MDF | Custom |
| 3 | 1 | Back | Enclosure | MDF | Custom |
| 4 | 1 | Bottom | Enclosure | MDF | Custom |
| 5 | 1 | Front Bottom | Enclosure | MDF | Custom |
| 6 | 1 | Keyboard Support | Enclosure | MDF | Custom |
| 7 | 1 | Front | Enclosure | MDF | Custom |
| 8 | 1 | Front Up | Enclosure | MDF | Custom |
| 9 | 1 | Top | Enclosure | MDF | Custom |
| 10 | 1 | Right Filler | Enclosure | MDF | Custom |
| 11 | 1 | Left Filler | Enclosure | MDF | Custom |
| 12 | 1 | Hinge Holder | Enclosure | MDF | Custom |
| 13 | 2 | Hinge 25/15mm | Enclosure | Metal | Stock |
| 14 | 8 | Wood screw 2.5/8mm | Enclosure | Metal | Stock |
| 15 | 1 | Impeller-base | Dispenser | PETG/ABS | Custom |
| 16 | 1 | Impeller | Dispenser | PETG/ABS | Custom |
| 17 | 1 | Conteiner (v.2.1, 250mm) | Dispenser | PETG/ABS | Custom |
| 18 | 1 | Impeller Enclosure | Dispenser | PETG/ABS | Custom |
| 19 | 1 | Base | Dispenser | PETG/ABS | Custom |
| 20 | 2 | Brush | Dispenser | TPU | Custom |
| 21 | 1 | DC Motor FT-49OGM500-530K | Dispenser | Electronic | Stock |
| 22 | 1 | Bolt M3/15mm flat head | Dispenser | Metal | Attaches Impeller-base to motor shaft |
| 23 | 4 | Bolt M3/8mm conical head | Dispenser | Metal | Mounts motor onto Base |
| 24 | 4 | Wood screw 3.5/10mm | Dispenser | Metal | Mounts Base to wooden foundation |
| 25 | 1 | Wires with crimp connector JST ZH1.5-3P | Dispenser | Wire | Stock/Custom |
| 26 | 1 | Rotation sensor | Dispenser | PCB | Custom |
| 27 | 1 | Frame | Keyboard | PETG/ABS | Custom |
| 28 | 1 | White Keys | Keyboard | PETG/ABS | Custom |
| 29 | 1 | Black Keys | Keyboard | PETG/ABS | Custom |
| 30 | 1 | Main PCB | Keyboard | PCB | Custom |
| 31 | 5 | Bolt M3/25mm conical head | Keyboard | Metal | Attaches keys to Frame |
| 32 | 2 | Wood screw 3.5/25mm conical head | Keyboard | Metal | Attaches keyboard to casing |
| 33 | 1 | Speaker 3W/8Ohm 78/78mm | Speaker | Electronic | Stock |
| 34 | 1 | Wires with crimp connector JST XH2.54-2P | Speaker | Wire | Stock/Custom |
| 35 | 4 | Bolt M3/15mm flat head | Speaker | Metal | Stock |
| 36 | 1 | AD-DC Adapter 9VDC | Power Supply | Electronic | Stock |
| 37 | 1 | Battery Compartment 6xAA | Power Supply | PETG/ABS | Stock |
| 38 | 1 | DPST Rocker Switch | Power Supply | Electronic | Stock |
| 39 | 1 | 5.5mm x 2.5mm Female DC Power Jack | Power Supply | Electronic | Stock |
| 40 | 5 | Bolt M3/15mm flat head | Dispenser/Speaker | Metal | Impeller-base to motor shaft, and speaker |
| 41 | 8 | Nut M3 | Dispenser/Speaker | Metal | Motor mount and speaker |
| 42 | 7 | Magnet 5/2mm | Dispenser/Enclosure | Magnet | For Impeller and Lid |
| 43 | 5 | Wires with crimp connector JST XH2.54-2P | Dispenser/Power Supply | Wire | Motor and power supply |

## PCB BOM (PetPiano v.1.0, main board)

Key parts. Full LCSC part numbers are in the original PDF.

| Qty | Designator | Comment | Description |
| --- | --- | --- | --- |
| 29 | R1, R3-R5, R7, R9-R11, R14-R33, R40 | 12k | Resistors 0603 |
| 2 | R34, R35 | 4k7 | Resistors 0603 |
| 4 | R36-R39 | 10k | Resistors 0603 |
| 1 | R2 | 634k | Resistor 0603 |
| 1 | R41 | 15k | Resistor 0603 |
| 1 | R13 | 2.4k | Resistor 0603 |
| 1 | R12 | 20k | Resistor 0603 |
| 1 | R42 | 6.8k | Resistor 0603 |
| 1 | R8 | 1k | Resistor 0603 |
| 4 | C3, C4, C12, C14 | 10uF | Electrolytic capacitors |
| 27 | C2, C6, C9, C10, C13, C15-C33 | 100n | Capacitors 0603 |
| 2 | C1, C5 | 1u | Capacitors 0603 |
| 1 | J5 | - | Coin cell battery holder BS-06-B4AK001 |
| 1 | JP2 | - | Memory card connector GT-TF003-H0185-01 (microSD) |
| 1 | U2 | - | Motor driver, DC brush, DRV8838DSGR |
| 1 | U3 | - | Real-time clock DS3231MZ+TRL |
| 1 | U1 | - | Ai-Thinker ESP32-WROOM-32E-N16 |
| 1 | U6 | - | LD1085D2T33R low-dropout regulator (3.3V) |
| 1 | U5 | - | LD1086D2T50TR low-dropout regulator (5V) |
| 1 | U4 | - | Audio amplifier MAX98357AETE+T (I2S) |
| 4 | D1-D4 | - | Schottky diodes B5819W |
| 1 | U8 | - | 16-bit I/O expander MCP23017-E/SS |
| 1 | Q3 | - | N-channel MOSFET 2N7002 |
| 3 | Q1, Q2, Q4 | - | P-channel MOSFET AO3401A |
| 1 | U7 | - | Hall sensor SL353LT |
| 2 | SW1, SW2 | - | Momentary switches TS-1087S-01526 |
| 5 | J1, J2, J3, J8, J9 | 1x2 pin | Connectors XH2.54-2P |
| 1 | J7 | 1x2 pin | Connector B2B-PH-K-S |
| 2 | J4, J6 | 1x3 pin | Connectors B3B-ZR |
| 18 | S1-S18 | - | Switches, Panasonic ESE11SV1 (keys) |
| 1 | JP1 | 1x6 pin | Pin header (likely programming header) |
| 1 | STATUS_LED | Red 3mm | Status LED |
