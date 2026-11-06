# Original binary packages

The Pet Piano hardware started as an open DIY project by Sebastian at Smart
Solutions for Home. The original packages below are binary files, and the
tooling used to publish this repo only pushes text, so the packages
themselves are not stored in git. Their contents are preserved here as text
(BOM tables in `BOM.md`, listings below) and the originals are kept locally
in `hardware/originals/`.

## Files

| File | Size | SHA-256 |
| --- | --- | --- |
| `09B612FD-EEBE-4385-9B70-47D53B07F105-pet_piano_3D_model.zip` | 8,989,552 | `ff8de86ca172ca9b858f7b3e73986227bc1742d0662bb7701fc48b713a4b484d` |
| `Pet-Piano-PCB.zip` | 986,669 | `b139f3574aac984aba0686032b574e146cd25d5a52fdaa25f5d06a3eb4698b9a` |
| `PetPiano-v.1.0-BOM.pdf` | 58,210 | `e079be42443c4d63559e3d82b12c099b51c8df086751c45476380c2cf04a4950` |
| `PetPiano-v.1.0-PCB-BOM.pdf` | 69,057 | `921cc3f2e2ead37b1bb253ffc8958b651ee96f0501b82f94cd5fbed3787a630b` |

## `Pet-Piano-PCB.zip` contents

Gerber files for the main PCB (v.1.1), drill files, assembly drawings.

- `PCB/Gerber Files/GerberFiles/` - copper_top.gbr, copper_bottom.gbr,
  silkscreen_top.gbr, silkscreen_bottom.gbr, soldermask_top.gbr,
  soldermask_bottom.gbr, solderpaste_top.gbr, solderpaste_bottom.gbr,
  profile.gbr, vcut.gbr, gerber_job.gbrjob
- `PCB/Gerber Files/DrillFiles/` - drill_1_16.xln
- `PCB/Gerber Files/Assembly/` - PickAndPlace PDF, component placement PNG
- `PCB/PetPiano - production detail.pdf`
- `PCB/V-CUT.PNG`

## `pet_piano_3D_model.zip` contents

3MF models for 3D printing, in three groups.

- `3D Files/Dispenser/` - Base, Bowl, Brush, Conteiner v.2.1 250mm,
  Impeller Enclosure, Impeller, Impeller-base
- `3D Files/Enclosure/` - Back, Bottom, Front Up, Front, Front-Bottom,
  Hinge-Holder, Keyboard Support, Left Filler, Left, Right Filler, Right,
  Top
- `3D Files/Keyboard/` - Black v.1.0, Frame, White v.1.0

## Provenance

Files are dated December 2023 to February 2024 and come from the free DIY
package published with Sebastian's Smart Solutions for Home build video
("DIY Smart Pet Feeder / Piano for your pet!"). The 3D models were offered
free ($0.00) from his store. The commercial Pet Piano sold at
thepetpiano.com is based on this design.

If the binary packages need to live in this repo, upload them through the
GitHub web UI (Releases or a direct file upload) as a follow-up.
