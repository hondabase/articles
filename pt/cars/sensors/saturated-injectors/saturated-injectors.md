---
summary: 'Technical overview of saturated (high-impedance) fuel injectors, including impedance specifications and electrical operation for Honda OBD1 and newer systems.'
tags: [ecu, fueling, injectors, sensors]
applies_to:
  models: [all]
complexity: beginner
---

# Saturated Fuel Injectors (High Impedance)

Saturated injectors, commonly referred to as high-impedance injectors, are the standard fuel delivery components for Honda OBD1 and newer engine management systems.

## Technical Specifications

*   **Impedance Range:** 12–16 ohms.
*   **Current Draw:** Approximately 0.75A to 1.0A at 12V.

## Electrical Operation

Saturated injectors operate by receiving a constant 12V power supply. The ECU modulates the ground circuit to trigger the injector pulse. 

> [!IMPORTANT]
> Because these injectors operate at a lower current, they generate less heat during operation compared to peak-and-hold (low impedance) injectors.

## Compatibility and Installation

*   **Resistor Box:** Not required. Saturated injectors are designed to be driven directly by the ECU injector drivers.
*   **System Integration:** These are the factory-standard injectors for all OBD1 and later Honda platforms. If upgrading from low-impedance injectors, the factory resistor box must be removed and the wiring bypassed to ensure proper operation.

{{> injector-wiring-guide }}
