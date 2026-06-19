---
summary: 'The atmospheric pressure (PA) sensor measures ambient air pressure to adjust fuel mixtures for altitude and weather-related air density changes.'
tags: [ecu, reference, tuning, rom, sensors]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Atmospheric Pressure (PA) Sensor Reference

The atmospheric pressure sensor, commonly referred to as the Barometric Pressure or PA sensor, measures ambient air pressure. Unlike a Manifold Absolute Pressure (MAP) sensor, the PA sensor operates within a narrow range centered around standard atmospheric pressure.

## Functionality
The ECU utilizes data from the PA sensor to calculate air density. This allows the engine management system to dynamically adjust fuel trim and ignition timing to compensate for variations in altitude or significant changes in weather conditions.

> [!NOTE]
> In most OBD-series Honda ECUs, the PA sensor is integrated directly onto the ECU mainboard.

## Technical Specifications
The sensor provides a voltage signal to the ECU that corresponds to the current barometric pressure. 

*   **Primary Use:** Altitude compensation and air density correction.
*   **Operating Range:** Narrow-band atmospheric pressure.
*   **Integration:** Internal to the ECU housing.

## Troubleshooting
If the ECU detects an out-of-range signal from the PA sensor, it may trigger a diagnostic trouble code (DTC) related to the barometric pressure circuit. 

::: widget error-codes :::

### Common Symptoms of Failure
*   Poor fuel economy at high altitudes.
*   Rough idle or hesitation during rapid changes in elevation.
*   Rich or lean running conditions inconsistent with engine load.

> [!WARNING]
> When inspecting the internal PA sensor, ensure the ECU case is handled in an ESD-safe environment to prevent damage to sensitive surface-mount components.
