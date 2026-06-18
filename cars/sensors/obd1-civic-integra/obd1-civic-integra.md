---
summary: 'Technical reference for OBD1 Honda Civic and Acura Integra ECU pinouts, sensor configurations, and diagnostic specifications.'
tags: [ecu, wiring, obd1, sensors, honda, integra, civic]
applies_to:
  obd: [1]
  models: [civic, integra]
  chassis: [eg, dc2]
complexity: beginner
---

# OBD1 Civic and Integra ECU Reference

This document provides technical specifications and reference data for OBD1-era Honda Civic and Acura Integra Engine Control Units (ECUs).

## Overview
OBD1 ECUs were utilized in Honda and Acura vehicles from 1992 to 1995. These units manage fuel injection, ignition timing, and emissions systems based on inputs from various engine sensors.

## Diagnostic Resources
For detailed troubleshooting and error code identification, use the following tool:

::: widget error-codes :::

## ECU Pinout Reference
The following table outlines the standard connector configuration for OBD1 ECUs.

| Connector | Pins | Function |
| :--- | :--- | :--- |
| **Plug A** | 26 | Power, Ground, Injectors, IACV |
| **Plug B** | 16 | Sensors, VTEC, EGR, O2 |
| **Plug C** | 22 | Sensors, Distributor, Communication |

> [!IMPORTANT]
> Always verify wire colors against the factory service manual for your specific chassis code before performing electrical modifications.

## Common Sensor Wiring
When integrating aftermarket sensors or wideband controllers, refer to the standard wiring configurations below:

::: widget wideband-wiring-table :::

## Technical Notes
*   **Grounding:** Ensure all sensor grounds are terminated at the ECU chassis ground (Pin A24/A25) to prevent signal noise.
*   **Shielding:** Use shielded wire for sensitive signals such as the Knock Sensor and O2 sensor inputs to maintain signal integrity.

> [!TIP]
> Resistor color codes used during ECU hardware modifications are included below.

{{> resistor-color-codes }}
