---
summary: 'The Vehicle Speed Sensor (VSS) sends speed pulses to the cluster and ECU. Diagnosing speedo failures and VSS-related VTEC engagement issues.'
tags: [sensor, diagnostics, wiring]
applies_to:
  obd: [0, 1, 2]
  models: [integra]
  chassis: {}
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Vehicle Speed Sensor'
    url: /pgmfi/wiki/library/vehicle-speed-sensor
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Vehicle Speed Sensor (VSS)

The Vehicle Speed Sensor (VSS) measures axle rotation speed and sends this data as electrical pulses to the ECU and the dashboard gauge cluster.

## Overview

In most Honda vehicles, the VSS generates four ground pulses per single revolution of the axle.
*   **OBD0 (Cable-Driven):** The speedometer is driven by a physical cable connected directly to the transmission. The VSS itself is an electronic reed-switch module integrated into the back of the instrument cluster.
*   **OBD1 / OBD2 (Electronic):** The VSS is an electronic sensor mounted directly on the transmission housing (above the differential). It sends electronic signals straight to the gauge cluster and the ECU.

### ECU Functions
The ECU utilizes the VSS signal for several key operations:
1.  **VTEC Engagement:** The ECU will not engage VTEC unless the vehicle is moving above a set speed threshold (typically 15 mph / 24 km/h).
2.  **Speed Limiter:** Restricts the car's top speed (most commonly found on JDM ECUs at 180 km/h / 112 mph).
3.  **Gear-Dependent Fuel Corrections:** Helps calculate appropriate engine load corrections depending on the selected gear.
4.  **Cruise Control and Idle Control:** Controls stable idle when coasting to a stop and maintains cruise control speeds.
5.  **Launch Control / 2-Step:** Custom chipped ECU ROMs use VSS input to disable launch control once the vehicle starts moving.

## Wiring Reference

### OBD1 VSS Pinout

| Pin | Wire Color | Function | Connection Point |
| :--- | :--- | :--- | :--- |
| **Pin 1** | Yellow/Black | Power | +12V Switched Power (Fuse 15) |
| **Pin 2** | Black | Ground | Chassis Ground (G101 on thermostat housing) |
| **Pin 3** | Orange (or Blue/White) | Signal | Outputs pulsed signals to ECU pin **B10** and the speedometer cluster |

## Troubleshooting

### Symptoms of VSS Failure
*   The speedometer needle drops to zero, bounces erratically, or does not move.
*   The Check Engine Light (CEL) turns on with **Code 17** (VSS failure).
*   VTEC refuses to engage (due to the ECU thinking the car is stationary).
*   Erratic idle speed when coasting to a stop.

### Diagnosing VSS Issues
If you are getting Code 17 or the speedometer is dead:
1.  **Check Power and Ground:** Inspect the 3-pin connector at the transmission. Ensure you have 12V power on the Yellow/Black wire with the key on, and good continuity to ground on the Black wire.
2.  **Inspect the VSS Drive Link:** Remove the VSS from the transmission. Between the sensor and the transmission sits a small metal drive pin (drive link). If this pin breaks or falls out, the sensor won't spin, causing it to send 0 pulses.
3.  **Frequency Test:** Using a digital multimeter with a frequency counter or an oscilloscope, probe the Orange signal wire. Raise the front wheels off the ground, spin them by hand, and verify the signal pulses between 0V and 5V.

### Bypassing JDM Speed Limiters
JDM ECUs shut off fuel when they detect a vehicle speed of 180 km/h (~112 mph).
*   **The Chipping Method (Recommended):** The cleanest way to remove the speed limiter is to disable it in the ECU's ROM software using a BIN editor (like Crome).
*   **The Frequency Limiter Method (Hardware):** If running a non-chippable ECU, you can install a frequency-limiting circuit between the VSS and the ECU. By recording the frequency at 100 mph (safely below the limit), you can build a circuit that prevents the pulse frequency sent to the ECU from ever going above that 100 mph threshold, bypassing the limiter while keeping VTEC and cruise control functional.

## Related

*   [VTEC Solenoid](/cars/wiring/vtec-solenoid)
*   [ECU Trouble Codes](/cars/diagnostics/ecu-trouble-codes)
*   [ECU Troubleshooting](/cars/diagnostics/ecu-troubleshooting)
