---
summary: 'Step-by-step procedure to convert an OBD0 PR3 ECU from automatic to manual transmission by relocating the R68 resistor.'
tags: [ecu, obd0, pr3, transmission, modification]
applies_to:
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: beginner
---

# OBD0 PR3 ECU Automatic to Manual Conversion

Converting an OBD0 PR3 ECU from automatic to manual transmission requires a physical modification to the PCB to change the transmission configuration logic.

## Procedure

1. Locate the resistor labeled **R68** on the ECU PCB. It is positioned near the center divider of the board.
2. Desolder the resistor from the **R68** position.
3. Solder the same resistor into the empty footprint labeled **R67**.

> [!CAUTION]
> Ensure the ECU is disconnected from all power sources before performing any soldering. Use a temperature-controlled soldering station to prevent damage to the PCB traces.

## Component Location

The following carousel illustrates the board layout and the specific resistor locations required for this modification.

```carousel
![PR3 PCB Overview](pr3_board_top.jpg)
*Top view of the OBD0 PR3 PCB showing the R67 and R68 resistor locations.*
<!-- slide -->
![Resistor Detail](pr3_resistor_zoom.jpg)
*Close-up view of the R67 and R68 footprints.*
```

{{> soldering-best-practices }}
