---
summary: 'Overview of the Oxygen (O2) Sensor heater circuit, its function in maintaining sensor accuracy, and integration with Honda OBD ECUs.'
tags: [ecu, sensors, diagnostics, wiring]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Oxygen (O2) Sensor Heater Circuit

The **Oxygen (O2) Sensor heater circuit** is the key difference between modern 4-wire sensors and legacy 1-wire sensors.

---

## Purpose
An O2 sensor must reach a specific operational temperature before it can provide an accurate signal to the ECU.
*   **1-Wire Sensors:** Rely entirely on exhaust heat, resulting in long "open-loop" warmup times.
*   **4-Wire Sensors (Heated):** Utilize an internal electric heating element to quickly bring the sensor to its optimal temperature range, enabling faster closed-loop operation and improved emissions control.

## ECU Integration
If you are upgrading from a 1-wire to a 4-wire O2 sensor, the ECU must be modified to support the heater control circuit.

*   **ECU Support:** The ECU requires a dedicated driver circuit to manage the heater element.
*   **Troubleshooting:** If the heater circuit is absent or malfunctioning, the ECU will typically trigger **Code 41 (O2 Sensor Heater Malfunction)**.

*For specific instructions on adding heater circuitry to your ECU or disabling Code 41 in your ROM, refer to your ECU-specific ROM mapping documentation.*
