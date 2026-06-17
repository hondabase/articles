---
summary: 'Eliminate the persistent cruise control or upshift indicator light on modified OBD1 P05 ECUs by removing resistor R135.'
tags: [ecu, p05, diagnostics, wiring]
applies_to:
  obd: [1]
  models: [civic]
  chassis: [eg]
complexity: beginner
---

# Disabling Cruise Control and Upshift Indicator Lights on P05 ECUs

When modifying P05 ECUs, users may encounter a solid cruise control indicator light when utilizing an EX instrument cluster, or a solid upshift indicator light when utilizing a CX/VX instrument cluster. This behavior is caused by the ECU signaling through pin D18.

## Technical Overview

The cruise control and upshift indicator circuits share pin D18 on the OBD1 P05 ECU. In certain modified configurations, this circuit remains active, causing the indicator to illuminate constantly.

> [!IMPORTANT]
> The cruise control and upshift light signals are routed through resistor **R135**. Removing this component breaks the connection to pin D18, effectively disabling the indicator light.

## Procedure

1. Open the ECU housing to access the main PCB.
2. Locate resistor **R135** on the circuit board.
3. Desolder and remove **R135** from the board.
4. Verify that the solder pads are clean and no bridges remain.
5. Reassemble the ECU and test the instrument cluster for the absence of the indicator light.

> [!TIP]
> Ensure the ECU is disconnected from the vehicle harness before performing any internal modifications to prevent electrical shorts.