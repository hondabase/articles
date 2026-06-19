---
summary: 'Technical overview of the OBD0 PK2 ECU used in the Honda B20A Prelude, featuring hardware configuration, jumper settings, and PCB compatibility.'
tags: [ecu, obd0, tuning, b20a, rom]
applies_to:
  models: [Prelude]
  chassis: [BA]
complexity: advanced
---

# Honda PK2 ECU Technical Reference

The PK2 ECU is an OBD0 unit utilized in the Honda Prelude equipped with the B20A engine. It features an external 27C256 ROM and is based on the OKI 83C154 microcontroller architecture.

## PCB Architecture and Compatibility
The PK2 and PH3 ECUs share a nearly identical printed circuit board (PCB) design, with approximately 99% hardware commonality. Due to this architectural similarity, PH3 firmware is often compatible with PK2 hardware.

> [!NOTE]
> The Jumper **BR8** appears to control the secondary O2 sensor input. On the PH3 (which lacks a secondary O2 sensor), this jumper is used to disable the input.

## Hardware Configuration
The PK2-6640 manual ECU features various configuration jumpers. While the exact function of all options remains under investigation, they are suspected to be related to transmission type or regional emissions requirements.

```carousel
![PK2 ECU Top View](pk2.jpg)
*Overview of the PK2 ECU PCB*
<!-- slide -->
![PK2-6640 Manual ECU](pk2-6640_manual.jpg)
*Canadian market PK2-6640 manual transmission ECU*
<!-- slide -->
![PK2-6640 Options Close-up](pk2-6640_manual_options.jpg)
*Detailed view of the configuration options area*
<!-- slide -->
![BR8 Jumper Detail](BR8-PK2.jpg)
*Close-up of the BR8 jumper location*
```

## Technical Specifications

| Component | Specification |
| :--- | :--- |
| **Microcontroller** | OKI 83C154 |
| **ROM Type** | External 27C256 |
| **OBD Standard** | OBD0 |
| **Engine Application** | B20A |

> [!TIP]
> For further details regarding jumper functionality and sensor pinouts, refer to the PH3 ECU documentation, as the shared PCB design allows for cross-referencing of most circuit paths.
