# Strip feeder plan

This build uses 19 printed strip feeders and no motorised feeders for now. They hold all tape widths
my two target boards need, for runs of up to 5 boards.

## The strip feeders

The print files come from the LumenPnP release
[v4.2.0](https://github.com/opulo-inc/lumenpnp/releases/tag/v4.2.0) (`Autobom-LumenPnP-v4.2.0.zip`,
folder `export/`). All variants are 120 mm long and take tape up to 6.5 mm deep.

| Variant | Strips per feeder | Footprint [mm] | PLA per feeder |
|---|---|---|---|
| 8 mm | 3 | 40.4 × 120 | about 15 g |
| 12 mm | 3 | 44.4 × 120 | about 16 g |
| 16 mm | 2 | 44.4 × 120 | about 13 g |
| 24 mm | 1 | 26.4 × 120 | about 7 g |
| 32 mm | 1 | 34.4 × 120 | about 8 g |
| Adjustable, 32 mm and wider (left + right half) | 1 | 2 × 32.1 × 120 | about 6 g |

Strips per feeder are from Opulo's product page. PLA weights are estimated from the STL volume at
about 60 % fill.

Each feeder is held with 2 M3 × 10 button head screws and 2 M3 wing nuts; the adjustable feeder
needs 4 of each (2 per half). The BOM specifies ultra-low-profile button heads. This build uses
ISO 7380, which should be checked for tape clearance.

## Parts per strip

A 120 mm strip holds about 110 mm of usable tape:

| Tape pitch | Parts per strip |
|---|---|
| 2 mm | 55 |
| 4 mm | 27 |
| 8 mm | 13 |
| 16 mm | 6 |
| 24 mm | 4 |

A part with 19 placements per board at 4 mm pitch therefore needs one strip per board.

## Lanes needed

Counted per part number, for the larger of the two boards per tape width (the boards run one after
the other):

| Tape width | Lanes, 1 board | Lanes, 5 boards | Feeders printed |
|---|---|---|---|
| 8 mm | 25 | 29 | 10 × 8 mm |
| 12 mm | 4 | 4 | 2 × 12 mm |
| 16 mm | 1 | 1 | 1 × 16 mm |
| 24 mm | 2 | 2 | 2 × 24 mm |
| 24 or 32 mm (not yet known) | 1 | 1 | 1 × 24 mm + 1 × 32 mm |
| 44 mm (module, 24 mm pitch) | 1 | 2 | 2 × adjustable |
| **Total** | | | **19 feeders** |

One part comes in a tray, not on tape. It is placed by hand.

## Hardware

| Item | Qty | Source |
|---|---|---|
| ISO 7380 M3 × 10 | 42 (2 × 17 + 4 × 2) | AliExpress, 50-pack |
| Wing nut DIN 315 M3 | 42 (plus 12 for fixtures per BOM) | AliExpress, 6 × 10-pack |

Prices are in [../bom/bom.md](../bom/bom.md).

## Later: Photon feeders v2, self-built

Opulo released a redesigned motorised feeder,
[v2.0.0](https://github.com/opulo-inc/feeder/releases/tag/v2.0.0), on 18 Nov 2026. It fits every
LumenPnP version and is worth it for parts with many placements per board. It is not part of the
total in [../bom/bom.md](../bom/bom.md) yet.

Bought from Opulo, a 5-pack costs 495 USD (99 USD per feeder). Self-built with hand-assembled PCBs,
estimated per feeder (prices checked 19 Nov 2026):

| Item | Source | Per feeder |
|---|---|---|
| Bare PCB `feeder-mobo-ott` (71.6 × 80 mm, 2 layers) | JLCPCB, 10 pcs | about 0.50 USD |
| PCB components (about 60 parts, STM32F030, MAX3078E, 2× DRV8837) | LCSC, for 10 boards | about 9.60 USD |
| Drive motor, peel motor and brass drive wheel ("Feeder Motors and Drive Wheel") | Opulo, currently sold out | 19.95 USD |
| 2 compression springs, pick window spring, 11 M3 flat head screws, M2.5 set screw | AliExpress / local stock | about 1 € |
| 9 printed parts | own print, about 72 g PLA | about 1 € |

That is about 30 USD per feeder before shipping, import fees and VAT. The machine also needs the
slot boards on the feeder rails once: Opulo's Feeder Connection Kit (155 USD, up to 50 feeders). Its
slot boards carry 1-Wire EEPROMs pre-programmed with the slot address, so buying it is simpler
than building it. Both Opulo items can go into the main Opulo order to avoid a second shipment.

Open points:

- The Opulo motor kit is sold out. Off-the-shelf right-angle motors with encoder (1218-N20 worm
  gear motor with Hall encoder, about 8 € on AliExpress) have a lower gear ratio than the 1:1030
  N30 motor in the BOM, so the Photon firmware would need adjusting, and the longer shaft makes
  the feeder wider. The brass drive wheel is only available from Opulo.
- LCSC stock on 19 Nov 2026: AP63203WU 0 pcs, MAX3078E 27 pcs, STM32F030C8T6 141 pcs.
- The DRV8837 is a 2 × 2 mm WSON package: reflow or hot air, not a soldering iron.

## Space on the plates

The feeders take about 780 mm of plate edge in total. The staging plate (600 × 120 mm) takes the
feeders across its width next to the board fixture. The rest go lengthwise on the two build plates
(600 × 75 mm), five per plate.
