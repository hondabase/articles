---
summary: 'Technical reference for OBD1 Honda ECU routines, including documentation on I/O operations and specific A/C control logic for the P30 JDM 203 ROM.'
tags: [ecu, reference, tuning, rom, sensors, obd1]
applies_to:
  models: [civic, del-sol, integra]
  chassis: [eg, eh]
complexity: beginner
---

# OBD1 Honda ECU Routine Reference

This document provides technical references for commented routines found within OBD1 Honda ECU firmware.

## P30 (203) ROM Analysis

The JDM P30 203 ROM serves as a primary reference for understanding how I/O operations are executed in OBD1 Honda ECUs. These routines are generally applicable across the broader OBD1 Civic and Integra ECU family.

### Routine Documentation

*   **[I/O Operations](/cars/ecu/doc-ecu-school):** Detailed breakdown of how the ECU handles input and output signals.
*   **[203_AC](/cars/diagnostics/203-ac):** Analysis of the A/C control routine specific to the JDM P30 203 calibration.
*   **[A/C Cut Routine](/cars/diagnostics/ac-cut-routine):** Logic governing the deactivation of the A/C compressor under high-load conditions.

> [!NOTE]
> While these routines are documented based on the P30 203 ROM, the underlying logic is shared across most OBD1 Honda/Acura ECU variants.
