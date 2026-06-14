---
summary: 'Resistor swap procedure to convert an OBD0 PR3 ECU from automatic to manual transmission.'
applies_to:
  obd: [0]
  ecus: [PR3]
complexity: beginner
tags:
  - ecu
  - reference
---

# OBD0 PR3 Auto to Manual Conversion

To convert an automatic transmission OBD0 PR3 ECU to a manual transmission configuration:

1. Locate the resistor marked **`R68`** on the ECU board (located near the center divider of the PCB).
2. Desolder and move the resistor from **`R68`** to the empty footprint at **`R67`**.

Refer to the high-resolution board diagram below for the exact resistor location:

![OBD0 PR3 ECU automatic to manual transmission resistor modification location](OBD0_pr3-auto-manual.jpg)
