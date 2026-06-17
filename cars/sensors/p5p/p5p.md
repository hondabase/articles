---
summary: 'Technical overview of the P5P OBD2 ECU used in the JDM Honda Prelude Type-S, detailing its hardware specifications and application.'
tags: [ecu, p5p, prelude, obd2, jdm]
applies_to:
  obd: [2]
  models: [prelude]
  chassis: [bb]
complexity: beginner
---

# P5P OBD2 ECU Technical Reference

The P5P is an OBD2-compliant Engine Control Unit (ECU) utilized in the Japanese Domestic Market (JDM) 1997–2000 Honda Prelude Type-S.

## Overview
The P5P ECU is specifically calibrated for the H22A engine found in the Type-S trim. It features unique fuel and ignition mapping designed to support the higher compression ratio and specific intake/exhaust characteristics of the Type-S powerplant.

> [!IMPORTANT]
> The P5P is an OBD2-spec ECU. Ensure compatibility with your vehicle's wiring harness and immobilizer system before installation, as JDM units may lack the immobilizer circuitry found in North American (USDM) counterparts.

## Hardware Specifications
*   **Market:** JDM (Japanese Domestic Market)
*   **Vehicle Application:** 1997–2000 Honda Prelude Type-S
*   **Engine:** H22A
*   **OBD Standard:** OBD2

## Diagnostic Support
For troubleshooting and diagnostic assistance, refer to the integrated error code database:

::: widget error-codes :::

## Compatibility Notes
*   **Immobilizer:** As a JDM-spec ECU, the P5P may not include the immobilizer hardware required for USDM vehicles. Use of this ECU in a USDM chassis may require an immobilizer bypass or specific wiring modifications.
*   **Sensor Scaling:** The P5P utilizes standard Honda OBD2 sensor scaling. If you are integrating wideband oxygen sensors or aftermarket monitoring equipment, refer to the following wiring reference:

::: widget wideband-wiring-table :::