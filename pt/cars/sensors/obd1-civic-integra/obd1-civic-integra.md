---
summary: 'A comprehensive reference guide for OBD1 engine control units found in 1992–1995 Honda Civic and Acura Integra models.'
tags: [ecu, obd1, honda, acura, diagnostics]
applies_to:
  obd: [1]
  models: [Civic, Integra]
complexity: beginner
---

# OBD1 Honda Civic and Acura Integra ECU Reference

This guide provides technical specifications and identification data for OBD1 engine control units (ECUs) used in 1992–1995 Honda Civic and Acura Integra platforms.

## ECU Identification
OBD1 ECUs are identified by a three-character code stamped on the ECU casing. These codes denote the specific engine, transmission, and regional calibration of the unit.

> [!NOTE]
> ECU compatibility is determined by the internal hardware configuration and the specific engine management requirements (e.g., VTEC vs. non-VTEC, manual vs. automatic transmission).

## Common OBD1 ECU Variants

| ECU Code | Engine | Vehicle | Transmission | VTEC |
| :--- | :--- | :--- | :--- | :--- |
| P05 | D15B7 | Civic DX | Manual | No |
| P06 | D15B7 | Civic DX | Manual | No |
| P07 | D15Z1 | Civic VX | Manual | No |
| P28 | D16Z6 | Civic Si/EX | Manual | Yes |
| P30 | B16A | Del Sol VTEC | Manual | Yes |
| P61 | B17A1 | Integra GSR | Manual | Yes |
| P72 | B18C1 | Integra GSR | Manual | Yes |
| P75 | B18B1 | Integra LS/RS | Manual | No |

## Diagnostic Resources
For detailed troubleshooting and error code definitions, refer to the integrated diagnostic tools below.

::: widget error-codes :::

## Wiring and Pinouts
For specific sensor wiring and ECU pinout configurations, refer to the following reference:

{{> ecu-pinout-reference }}

> [!IMPORTANT]
> Always verify the ECU part number against the vehicle's chassis harness before attempting to start the engine to prevent damage to the ECU or engine sensors.