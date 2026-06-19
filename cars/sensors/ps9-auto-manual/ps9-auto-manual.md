---
summary: 'Convert an automatic transmission ECU to manual transmission operation by removing specific resistors and adding a jumper. Applies to PS9, PG7, PM6, and PM7 ECU variants.'
tags: [ecu, conversion, transmission, hardware]
applies_to:
  models: [civic, crx]
  chassis: [ef]
complexity: beginner
---

# Automatic to Manual Transmission ECU Conversion

Converting an automatic transmission ECU to manual transmission operation requires modifying the PCB to bypass automatic-specific logic. This procedure applies to PS9, PG7, PM6, and PM7 ECUs, which share the same PCB architecture.

## Modification Procedure

To convert the ECU for manual transmission use, perform the following hardware modifications:

*   **Remove Resistors:** Desolder and remove resistors **R62**, **R64**, and **R66**. These are located near the center divider of the PCB.
*   **JDM ECU Requirement:** For JDM-spec ECUs, you must also install a jumper at location **BR3**.

> [!CAUTION]
> Ensure the PCB is clean of solder bridges after removing the resistors. Use a desoldering pump or wick to clear the through-holes completely.

## PCB Reference

The following image illustrates the location of the components requiring modification.

![Automatic to Manual Conversion Points](PM7autoTOmanual.jpg)
*PCB layout showing the location of R62, R64, R66, and BR3*
