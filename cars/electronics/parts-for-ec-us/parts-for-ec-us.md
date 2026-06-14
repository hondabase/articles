---
summary: 'Historic supplier part numbers for components used when socketing, modifying, or repairing Honda OBD0 and OBD1 ECUs.'
applies_to:
  obd: [0, 1]
complexity: advanced
tags:
  - ecu
  - hardware
  - reference
---

# Honda ECU component sourcing reference

This is a cleaned transcription of the component and supplier numbers collected by the
original pgmfi community for Honda OBD0 and OBD1 ECU work. Supplier catalogs change, so
use these numbers as search references and verify package, value, voltage rating, pinout,
and dimensions before ordering.

> **Warning:** Similar-looking components are not necessarily interchangeable. Check the
> ECU board revision and the replacement component's datasheet before soldering it in.

## Capacitors

| Value | Description | Board locations | Source note | Historic Digi-Key number |
| :--- | :--- | :--- | :--- | :--- |
| 22 pF | Ceramic disc capacitor | C72, C74, C75, C89 | - | `1330PH-ND` |
| 0.1 uF | Ceramic disc capacitor | C51, C52 | - | `399-2081-ND` |
| 1 uF, 35 V | Electrolytic capacitor | C60 | - | `478-1835-ND` |
| 4.7 uF | Tantalum electrolytic capacitor | C94 | - | `399-1358-ND` |
| 0.004 uF | Surface-mount capacitor | C49, C50 | JDM P30 and similar surface-mount ECUs | `399-1230-1-ND` |
| 0.00001 uF | Surface-mount capacitor | C91, C92 | JDM P30 and similar surface-mount ECUs | `399-1192-1-ND` |

## Resistors

| Value | Description | Board locations | Historic Digi-Key number |
| :--- | :--- | :--- | :--- |
| 1 kohm | 1/4 W, 5% resistor | R54 | `1.0KEBK-ND` |
| 1.2 kohm | 1/4 W, 5% resistor | R54 | `1.2KEBK-ND` |
| 220 ohm | 1/4 W, 5% resistor | R107 | `220EBK-ND` |
| 10 kohm | 1/4 W, 5% resistor | R142, R144, RM11 pins 1-2 | `10KEBK-ND` |
| 15 kohm | 1/4 W, 5% resistor | R143 | `15KEBK-ND` |
| 820 ohm | 1/4 W, 5% resistor | R66, R67 | `820EBK-ND` |
| 51 kohm | 1/4 W, 5% resistor | RM11 pins 2-3 | `51KEBK-ND` |
| 12 kohm | 1/4 W, 5% resistor | RM11 pins 3-8 | `12KEBK-ND` |

## Memory, latches, and sockets

| Component | Description or source note | Historic supplier number |
| :--- | :--- | :--- |
| SST 27SF512 | Erasable ROM for a bin file | Mouser `804-27SF5127CPG` |
| AT29C256 | Erasable ROM; listed as obsolete in source | Digi-Key `AT29C256-70PC-ND` |
| AT27C256R | EPROM; source includes the unexplained note `15/12/10` | Digi-Key `AT27C256R-70PC-ND` |
| 28-pin DIP socket | ROM socket | Digi-Key `ED3628-ND` |
| 28-pin ZIF socket | Zero-insertion-force ROM socket | Digi-Key `A347-ND` |
| 74HC373N | DIP address latch for USDM boards | Digi-Key `296-1591-5-ND` |
| 20-pin DIP socket | Tin socket for DIP latch | Digi-Key `ED3120-ND` |
| 74HC373NS | SOP address latch for JDM surface-mount boards | Digi-Key `296-8310-1-ND` |

## Transistors, diode, and connector

| Component | Board locations or use | Source cross-reference | Historic supplier number |
| :--- | :--- | :--- | :--- |
| PNP A143 | `Q101` | A143 / NTE2362 | `2SB1030ARACT-ND` |
| NPN `C144` | `Q26`, `Q30` | `C144` / C2785 / NTE2361 | `2SD1423ARACT-ND` |
| 1N4001, 1 A diode | D11 | - | `1N4001DICT-ND` |
| 0.1-inch, 4-pin friction-lock header | OBD1 `CN2` datalogging | Manufacturer `640456-4` | `A1922-ND` |
| Motorola 2.5-bar MAP sensor | Increased boost | Manufacturer note `737390003` | `MPX4250AP-ND` |

## Related

- [Introduction to ECU chipping](/cars/electronics/introduction-to-ecu-chipping)
- [OBD1 ECU chipping wire list](/cars/electronics/ecu-chipping-wirelist)
- [Archived supplier price list](prices.rtf)
