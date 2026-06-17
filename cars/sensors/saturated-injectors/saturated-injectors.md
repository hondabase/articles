---
summary: 'Technical overview of saturated (high impedance) fuel injectors, including electrical characteristics and compatibility with Honda OBD1 systems.'
tags: [ecu, fueling, injectors, sensors]
applies_to:
  obd: [1]
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eh]
complexity: beginner
---

# Saturated (High Impedance) Fuel Injectors

Saturated injectors, commonly referred to as high impedance injectors, are the standard fuel delivery component for Honda OBD1 and later fuel injection systems.

## Electrical Characteristics
These injectors typically feature an internal resistance ranging from **12 to 16 ohms**. 

*   **Current Draw:** At 12 volts, the current draw is approximately 0.75 to 1.0 amps.
*   **Thermal Efficiency:** The lower current draw compared to peak-and-hold (low impedance) injectors results in reduced heat generation during operation.
*   **Control Method:** Saturated injectors receive a constant 12V power supply, while the ECU modulates the ground circuit to trigger the injector pulse.

> [!IMPORTANT]
> Because these injectors operate at high impedance, they do not require an external resistor box. Installing saturated injectors in a system designed for low impedance injectors without removing the resistor box will result in improper fuel delivery and potential ECU damage.

## Compatibility
Saturated injectors are native to all Honda OBD1 and newer chassis. When upgrading or replacing fuel injectors, ensure the impedance matches the requirements of your specific ECU and wiring harness configuration.

{{> injector-impedance-guide }}