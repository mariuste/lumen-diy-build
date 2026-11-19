# Lumen DIY build: a self-sourced pick-and-place machine for about 1,420 €

A self-sourced build of Opulo's open-source pick-and-place machine
[LumenPnP v4](https://github.com/opulo-inc/lumenpnp), built in Germany. Only the parts that are hard to make myself come from
Opulo: the Control Box, the two toolhead kits and the assembled ring light and endstop boards.
Everything else comes from AliExpress, eBay.de and German suppliers, and the plates are cut from
aluminium sheet and drilled in a makerspace.

All prices were checked on 19 Nov 2026, with the right variant selected on each product page.
They include shipping to Germany, EU import duty, fees and VAT. The full list with links is in
[bom/bom.md](bom/bom.md).

**Status:** parts list final, not ordered yet. The build log will follow in this repo.

## Cost summary

| Supplier | What | Total [€] |
|---|---|---|
| Opulo (US) | Control Box, 2 Toolhead Kits, Ring Light Set, Endstop Set; UPS shipping, duty, VAT, UPS fee | 538.23 |
| AliExpress | Extrusions, rails, motors, belts, cameras, nozzles, PSU, cabling, drag chain, screws, wing nuts | 443.30 |
| AliExpress import fees | 18 parcels × 5.95 € (see below) | 107.10 |
| aluminium-online-shop.de | Sheet cut to size for the three plates and the X cable chain support | 68.45 |
| SUNLU (AliExpress, DE warehouse) | 4 kg PLA+ for printed parts and 19 strip feeders | 49.58 |
| eBay.de | Small parts and special nuts, free shipping within Germany | 43.61 |
| JLCPCB | Bare PCBs: cal-fid, nozzle-cal-token, ftp | 31.99 |
| Local stock | 130 standard screws and nuts | 6.50 |
| **Subtotal** | | **1,288.76** |
| Contingency 10 % | | 128.88 |
| **Total** | | **1,417.64** |

For comparison: Opulo lists the LumenPnP kit at 1,995 USD before shipping, duty and VAT
(opulo.io, 19 Nov 2026).

## Where this build deviates from the official BOM

- **Feeders:** 19 printed strip feeders instead of Photon feeders. Opulo's feeder motor kit is
  sold out; Photon feeders can be added later. Plan and lane count: [feeder/README.md](feeder/README.md).
- **Plates:** in the official design the staging plate (600 × 120 × 3 mm) and the two build plates
  (600 × 75 × 3 mm) are powder-coated steel with tapped holes (Opulo sells a build plate for 70 USD).
  Here they are AlMg3 sheet cut to size (±0.2 mm) and only drilled: fixtures and strip feeders are
  held with M3 screws and wing nuts, so the 3.3 mm holes need no thread. The CAD files are in the
  LumenPnP repo under `src/CSM/`.
- **X cable chain support:** this 655 mm PCB carries no components and is too long for JLCPCB.
  It is cut from 2 mm aluminium sheet (655 × 44.5 mm) and drilled instead.
- **Cable harnesses:** made from a JST PH 2.0 crimp kit and 24 AWG wire instead of Opulo's
  harness kits. The motherboard uses JST PH (2.0 mm) throughout, not XH.
- **Power supply:** Mean Well LRS-150-24 with a mains cord and a 5.5 × 2.1 mm DC cable, instead
  of Opulo's 24 V 6 A desktop adapter. The mains terminals need a printed cover.
- **Cameras:** ELP 720p OV9712 modules with a 12 mm lens on top and a 3.6 mm lens at the bottom,
  chosen to approximate the field of view of Opulo's v4 camera set (33° and 120°).
- **Nozzles:** generic CP40 nozzles N045 to N75 from AliExpress.

## EU import costs in 2026

These rules changed in 2026 and affect any build that buys from China:

- Since 1 July 2026, parcels under 150 € pay a flat import duty of 3 € per tariff line
  ([zoll.de](https://www.zoll.de/DE/Fachthemen/Zoelle/Wegfall-der-150-Euro-Zollfreigrenze/wegfall-der-150-euro-zollfreigrenze_node.html)).
- Since 1 November 2026, a handling fee of 2 € per tariff line comes on top.
- Duty and fee are part of the VAT base, so each parcel with one tariff line costs 5.95 €.
- AliExpress prices shown in Germany already include VAT.
- Consequence: anything that costs less than about 6 € is cheaper from a German eBay seller with
  free shipping than from AliExpress.
- The Opulo order is above 150 €, so regular duty applies (assumed at 2 %). UPS charges a fee for
  advancing duty and VAT: 2.5 %, at least 15.77 € including VAT
  ([UPS price list 2023, via paketda.de](https://www.paketda.de/zoll/ups.html)).

## Open risks

| Item | Possible effect |
|---|---|
| AliExpress may combine parcels; the calculation assumes one parcel per listing | up to −60 € |
| Prices for special nuts on eBay are the lowest variant | about +5 to +10 € |
| Opulo duty rate assumed at 2 %, not checked per tariff number | ±5 € |
| JLCPCB promotional price applies only once per order | about +5 € |
| AliExpress prices are Black Friday prices valid until 3 Dec 2026 | likely higher afterwards |

The 10 % contingency covers these.

Not included: tools (drill, crimping tool for JST PH), print time, and the components for the
boards the machine will assemble.

## Repository layout

- `bom/` – bill of materials and costs; `bom/quotes/` for quotes and invoices
- `pcb/` – Gerber files for the bare PCBs
- `print/` – print files for strip feeders and machine parts
- `feeder/` – strip feeder plan

## Credits and license

The machine design, BOM and CAD files are by [Opulo](https://github.com/opulo-inc/lumenpnp).
This repository only documents one self-sourced build of it. It is not affiliated with or endorsed
by Opulo; Opulo and LumenPnP are trademarks of Opulo.

Documentation: CC BY-SA 4.0. Files derived from the LumenPnP design: CERN-OHL-W v2.
Details in [LICENSE](LICENSE).
