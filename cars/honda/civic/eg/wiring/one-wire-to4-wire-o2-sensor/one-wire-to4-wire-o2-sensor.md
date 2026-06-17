---
summary: 'Learn how to enable O2 sensor heater circuitry on OBD1 ECUs like the P05 and P08 by adding the necessary transistor components.'
tags: [ecu, sensors, wiring, conversion, diagnostics]
applies_to:
  obd: [1]
  models: [civic]
  chassis: [eg]
complexity: beginner
---

# Enabling O2 Sensor Heater Circuitry on OBD1 ECUs

Certain OBD1 ECUs, such as the P05 and JDM P08, lack the internal circuitry required to drive a 4-wire heated O2 sensor. Failure to enable this circuit will result in a diagnostic trouble code (DTC). The following modifications allow for the integration of the O2 heater control.

## P05 ECU Modification
To enable O2 heater functionality on a P05 ECU, you must populate the missing transistor circuit.

*   **Component:** Transistor Q30
*   **Part Number:** C144 (or equivalent NPN switching transistor)

## JDM P08 ECU Modification
JDM ECUs lacking heater circuitry require an SMT transistor to be installed on the underside of the PCB.

*   **Component:** Transistor Q15
*   **Part Number:** MMBT4401 (SMT version of the 2N4401 general-purpose NPN switching transistor)

> [!IMPORTANT]
> Ensure the transistor is oriented correctly according to the PCB silkscreen markings. Improper orientation or soldering may result in damage to the ECU's driver circuit.

> [!TIP]
> These components are standard electronic parts and can be sourced through major electronics distributors such as Digi-Key or Mouser.