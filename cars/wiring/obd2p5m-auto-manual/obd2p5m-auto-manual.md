---
summary: 'Convert an OBD2 P5M ECU from automatic to manual transmission by relocating the 0-ohm SMD resistor.'
tags: [ecu, conversion, obd2, p5m, transmission]
applies_to:
  models: [accord, civic, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, dc2, dc5, ek, em-ep, na1-na2]
complexity: beginner
---

# OBD2 P5M ECU Automatic to Manual Conversion

This procedure modifies the P5M ECU to support manual transmission operation by reconfiguring the board's internal logic via a resistor swap.

## Procedure

To convert the ECU, relocate the 0-ohm SMD resistor (marked with "000") from the bottom of the PCB to the top.

1.  **Locate:** Identify the 0-ohm SMD resistor at location **RP13** on the bottom of the PCB.
2.  **Remove:** Carefully desolder the resistor from **RP13**.
3.  **Install:** Solder the same resistor onto the pads at location **RP14** on the top of the PCB.

> [!CAUTION]
> Use a temperature-controlled soldering station and appropriate flux. The PCB traces are delicate; excessive heat may cause the pads to lift from the board.

> [!TIP]
> Ensure the resistor is properly seated and the solder joints are clean to prevent intermittent connection issues or ECU communication errors.
