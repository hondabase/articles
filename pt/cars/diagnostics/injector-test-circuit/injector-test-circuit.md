---
summary: 'Technical overview of the USDM ECU Injector Test Circuit, which monitors fuel injector connectivity and triggers OBD Code 16.'
tags: [ecu, diagnostics, sensors, fuel-system]
applies_to:
  obd: [0, 1, 2]
complexity: beginner
---

# USDM ECU Injector Test Circuit

The Injector Test Circuit is a diagnostic feature integrated into USDM ECUs designed to verify the electrical continuity between the fuel injectors and the ECU. This circuit is responsible for triggering **Code 16** when a fault is detected.

## Operation
The ECU monitors the injector circuit to ensure that the injector solenoids are present and functioning. If the ECU fails to detect the expected electrical load or signal return from the injectors, it registers a diagnostic trouble code.

> [!IMPORTANT]
> Code 16 indicates an open or short circuit in the injector control lines. Always verify wiring harness integrity before assuming an ECU hardware failure.

## Diagnostic Reference
Use the following tool to identify the specific fault associated with the injector circuit:

::: widget error-codes :::

## Troubleshooting Steps
If you are experiencing a Code 16, perform the following checks:

* **Wiring Harness:** Inspect the injector clips and the main engine harness for signs of corrosion, frayed wires, or loose pins at the ECU connector.
* **Injector Resistance:** Measure the resistance of each fuel injector using a multimeter. Standard peak-and-hold injectors typically measure between 2–3 ohms, while saturated injectors measure 10–16 ohms.
* **Grounds:** Ensure the engine block and chassis grounds are clean and secure, as poor grounding can lead to intermittent injector circuit faults.

> [!TIP]
> If you have converted a vehicle from an OBD0/OBD1 system to a different ECU variant, ensure that the injector test circuit wiring matches the specific ECU pinout requirements to avoid false-positive error codes.