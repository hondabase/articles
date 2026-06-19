---
summary: 'Technical guide for converting an automatic P13 ECU (Prelude H22A) for use with a manual transmission.'
tags: [ecu, transmission, tuning, conversion]
applies_to:
  models: [prelude]
  chassis: [bb]
complexity: intermediate
---

# OBD1 P13 ECU: Auto to Manual Conversion

This guide outlines the hardware modifications required to convert an automatic P13 ECU (commonly used for H22A engines in Honda Preludes) for manual transmission operation.

---

## Conversion Procedure

1.  **Resistor Locations:** Locate `RP11` and `RP12` on the ECU PCB.
2.  **Configuration:** 
    *   **Automatic ECUs:** Typically feature a jumper at `RP11` with `RP12` left blank.
    *   **Manual Configuration:** Move the jumper from `RP11` to `RP12` to configure the ECU for manual transmission logic.
3.  **Alternative Configurations:** Some P13 variants may have resistors in both locations. If resistors exist in both `RP11` and `RP12`, remove both and install a jumper wire at `RP12` only.

---

## Compatibility
This conversion applies to ECUs sharing the P13 board architecture, including variants such as P11, P12, P13, P14, and P39.

*Always verify your board layout and component markings against a confirmed schematic for your specific ECU part number before soldering.*
