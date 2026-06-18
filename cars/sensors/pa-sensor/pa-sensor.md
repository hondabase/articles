---
summary: 'Technical guide to the Atmospheric Pressure (PA) sensor in Honda ECUs, explaining its role in altitude compensation and fueling adjustments.'
tags: [sensors, reference, ecu, fueling]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Atmospheric Pressure (PA) Sensor Technical Reference

The Atmospheric Pressure (PA) sensor is a critical component in Honda engine management systems, responsible for measuring ambient barometric pressure. The ECU utilizes this data to calculate air density and apply necessary fuel and ignition timing corrections based on altitude.

## Functionality
The PA sensor provides a voltage signal to the ECU that corresponds to the current atmospheric pressure. As altitude increases, atmospheric pressure decreases, resulting in thinner air. The ECU uses the PA sensor input to:

*   **Fuel Trim:** Adjust injector pulse width to maintain the target air-fuel ratio as air density changes.
*   **Ignition Timing:** Modify ignition advance maps to prevent detonation in lower-density air environments.

> [!NOTE]
> In many OBD1 Honda ECUs, the PA sensor is integrated directly onto the ECU circuit board. In some OBD2 applications, it may be an external sensor located in the engine bay.

## Sensor Characteristics
The sensor typically operates on a 5V reference signal. The output voltage scales linearly with pressure changes.

| Parameter | Specification |
| :--- | :--- |
| **Supply Voltage** | 5.0V DC |
| **Signal Type** | Analog Voltage |
| **Typical Output (Sea Level)** | ~3.8V - 4.2V |
| **Typical Output (High Altitude)** | ~2.5V - 3.0V |

## Diagnostics
If the ECU detects a signal outside of the expected operating range, it will trigger a Diagnostic Trouble Code (DTC).

::: widget error-codes :::

> [!WARNING]
> If the PA sensor fails or provides an incorrect reading, the engine may experience poor fuel economy, hesitation, or rough idling, particularly when driving through varying elevations.

## Related Components
For further information on how atmospheric pressure data is processed within the ECU fuel maps, refer to the following documentation:

*   [Pressure Atmosphere (PA) Mapping](/cars/rom/pressure-atmosphere)

{{> resistor-color-codes }}
