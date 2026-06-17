---
summary: 'An overview of engine simulator hardware used to mimic engine operation for Honda ECU development and bench testing.'
tags: [ecu, diagnostics, tuning, sensors, bench-testing]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
---

# Honda ECU Engine Simulator Reference

The Engine Simulator is a diagnostic and development tool designed to replicate the electrical signals of a running engine. It allows for the bench testing of Honda ECUs, enabling developers to verify code changes, test sensor inputs, and troubleshoot ECU hardware without requiring a physical engine.

## Purpose and Application

Engine simulators are primarily used for:
* **Firmware Development:** Validating custom ROMs and code modifications in a controlled environment.
* **Hardware Diagnostics:** Testing ECU input/output circuits, such as injector drivers, ignition outputs, and sensor signal processing.
* **Bench Calibration:** Verifying sensor scaling and data logging functionality before vehicle installation.

> [!NOTE]
> An engine simulator must accurately replicate the Crankshaft Position (CKP), Top Dead Center (TDC), and Cylinder (CYP) sensor signals to trigger the ECU's ignition and fuel injection logic.

## Technical Requirements

To effectively simulate a Honda engine, the hardware must provide:
* **Signal Generation:** Variable frequency square waves to mimic CKP/TDC/CYP sensors.
* **Load Simulation:** Resistive loads to simulate fuel injectors and IACV solenoids.
* **Sensor Emulation:** Potentiometers or voltage dividers to simulate analog inputs like the Throttle Position Sensor (TPS) and Coolant Temperature Sensor (ECT).

## Related Resources

For practical implementation details and circuit designs, refer to the following documentation:

* [Working Engine Simulator Notes](/cars/diagnostics/sim) — Technical guide for building and calibrating bench-top simulation hardware.