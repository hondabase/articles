---
summary: 'Reference guide for historic supplier part numbers for electronic components used in the modification and repair of Honda OBD0 and OBD1 ECUs.'
tags: [ecu, hardware, reference, components, repair]
applies_to:
  obd: [0, 1]
  models: [civic, del-sol]
  chassis: [eg, eh]
complexity: advanced
---

# Honda ECU Component Sourcing Reference

This document provides a reference for component specifications and historic supplier part numbers for Honda OBD0 and OBD1 ECU hardware. Supplier catalogs and inventory availability change frequently; use these numbers as search references and verify package, value, voltage rating, pinout, and dimensions against current datasheets before ordering.

> [!WARNING]
> Similar-looking components are not necessarily interchangeable. Always verify the ECU board revision and the replacement component's datasheet before soldering.

## Capacitors

| Value | Description | Board Locations | Historic Digi-Key Number |
| :--- | :--- | :--- | :--- |
| 22 pF | Ceramic disc capacitor | C72, C74, C75, C89 | `1330PH-ND` |
| 0.1 uF | Ceramic disc capacitor | C51, C52 | `399-2081-ND` |
| 1 uF, 35 V | Electrolytic capacitor | C60 | `478-1835-ND` |
| 4.7 uF | Tantalum electrolytic capacitor | C94 | `399-1358-ND` |
| 0.004 uF | Surface-mount capacitor | C49, C50 | `399-1230-1-ND` |
| 0.00001 uF | Surface-mount capacitor | C91, C92 | `399-1192-1-ND` |

## Resistors

| Value | Description | Board Locations | Historic Digi-Key Number |
| :--- | :--- | :--- | :--- |
| 1 kohm | 1/4 W, 5% resistor | R54 | `1.0KEBK-ND` |
| 1.2 kohm | 1/4 W, 5% resistor | R54 | `1.2KEBK-ND` |
| 220 ohm | 1/4 W, 5% resistor | R107 | `220EBK-ND` |
| 10 kohm | 1/4 W, 5% resistor | R142, R144, RM11 pins 1-2 | `10KEBK-ND` |
| 15 kohm | 1/4 W, 5% resistor | R143 | `15KEBK-ND` |
| 820 ohm | 1/4 W, 5% resistor | R66, R67 | `820EBK-ND` |
| 51 kohm | 1/4 W, 5% resistor | RM11 pins 2-3 | `51KEBK-ND` |
| 12 kohm | 1/4 W, 5% resistor | RM11 pins 3-8 | `12KEBK-ND` |

## Memory, Latches, and Sockets

| Component | Description | Historic Supplier Number |
| :--- | :--- | :--- |
| SST 27SF512 | Erasable ROM | Mouser `804-27SF5127CPG` |
| AT29C256 | Erasable ROM (Obsolete) | Digi-Key `AT29C256-70PC-ND` |
| AT27C256R | EPROM | Digi-Key `AT27C256R-70PC-ND` |
| 28-pin DIP socket | ROM socket | Digi-Key `ED3628-ND` |
| 28-pin ZIF socket | Zero-insertion-force ROM socket | Digi-Key `A347-ND` |
| 74HC373N | DIP address latch (USDM) | Digi-Key `296-1591-5-ND` |
| 20-pin DIP socket | Tin socket for DIP latch | Digi-Key `ED3120-ND` |
| 74HC373NS | SOP address latch (JDM) | Digi-Key `296-8310-1-ND` |

## Transistors, Diodes, and Connectors

| Component | Board Locations | Cross-Reference | Historic Supplier Number |
| :--- | :--- | :--- | :--- |
| PNP A143 | Q101 | A143 / NTE2362 | `2SB1030ARACT-ND` |
| NPN C144 | Q26, Q30 | C144 / C2785 / NTE2361 | `2SD1423ARACT-ND` |
| 1N4001 | D11 | 1 A Diode | `1N4001DICT-ND` |
| 4-pin header | CN2 (Datalogging) | 0.1-inch friction-lock | `A1922-ND` |
| MAP Sensor | Boost applications | Motorola 2.5-bar | `MPX4250AP-ND` |

## Related
- [Introduction to ECU Chipping](/cars/rom/introduction-to-ecu-chipping)
- [OBD1 ECU Chipping Wire List](/cars/wiring/ecu-chipping-wirelist)