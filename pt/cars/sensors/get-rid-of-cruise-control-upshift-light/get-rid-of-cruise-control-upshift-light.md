---
summary: 'Learn how to disable the persistent Cruise Control or Upshift indicator light on OBD1 Honda ECUs by removing resistor R135.'
tags: [ecu, diagnostics, wiring, modification]
applies_to:
  obd: [1]
  models: [Civic, Integra]
  chassis: [EG, DC]
complexity: beginner
---

# Disabling the Cruise Control and Upshift Indicator Light

When modifying certain OBD1 ECUs (such as the P05), users may encounter a persistent Cruise Control indicator light when using an EX instrument cluster, or a persistent Upshift indicator light when using a CX/VX instrument cluster. This issue is caused by the ECU outputting a signal to pin D18.

## Technical Overview

The Cruise Control and Upshift indicator circuits share the same ECU output pin: **D18**. By tracing the circuit on the PCB, it is determined that the signal path is governed by resistor **R135**.

> [!IMPORTANT]
> Removing resistor R135 will permanently disable the signal output to pin D18, effectively turning off the indicator light on the instrument cluster.

## Procedure

1.  **Access the ECU:** Open the ECU casing to expose the main PCB.
2.  **Locate R135:** Identify the resistor labeled **R135** on the board.
3.  **Removal:** Desolder and remove the R135 resistor from the PCB.
4.  **Verification:** Reassemble the ECU and verify that the indicator light no longer remains illuminated during operation.

> [!NOTE]
> This modification is specific to OBD1 ECUs where the D18 pin is utilized for indicator light control. Ensure your specific ECU board layout matches the R135 configuration before proceeding.