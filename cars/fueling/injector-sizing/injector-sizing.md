---
summary: 'Learn how to correctly calculate and select the appropriate fuel injectors based on your target horsepower and engine modifications to ensure optimal idle and peak performance.'
tags: [injectors, fueling, tuning, fuel-system]
applies_to:
  models: [civic, crx, del-sol, integra, prelude, accord, s2000, nsx]
  chassis: [ef, eg, ek, da, dc2, bb, cb-cd, ap1, ap2, na1-na2]
complexity: intermediate
---

# Fuel Injector Sizing and Selection

Selecting the correct fuel injectors requires balancing the flow requirements for maximum horsepower, RPM, and boost levels against the minimum flow requirements for stable idle.

## Injector Sizing Constraints

Most Honda PGM-FI systems have a minimum injector pulsewidth of approximately 1.0 millisecond. This limitation dictates the maximum usable injector size for a given engine displacement.

> [!WARNING]
> Installing injectors that are too large for the engine's displacement will result in an excessively rich air-fuel ratio at idle, as the ECU cannot command a pulsewidth short enough to maintain stoichiometric combustion. For example, 1000cc injectors are typically too large for a stock 1.6L engine.

## Injector Upgrades

When upgrading for forced induction or high-output naturally aspirated builds, ensure the chosen injectors are compatible with the vehicle's electrical system.

### Compatibility Considerations
*   **Impedance:** Determine if the injectors are **Peak and Hold** (low impedance) or **Saturated** (high impedance). 
*   **Resistor Box:** If installing low-impedance injectors into a system designed for high-impedance (or vice versa), a resistor box or injector driver may be required to prevent ECU damage or improper spray patterns.
*   **Connectors:** OEM injectors from different manufacturers often utilize unique electrical connectors. Ensure you source the appropriate pigtails for your specific injector set.

### Common Upgrade Paths
Historically, 450cc injectors from DSM (Mitsubishi/Chrysler) platforms were a common budget upgrade. As these components become rarer, modern aftermarket high-impedance injectors are recommended for better spray patterns, idle stability, and ease of tuning.

> [!TIP]
> Always verify the flow rate and impedance of any used OEM injectors before installation. Refer to professional injector flow charts to ensure the flow rate matches your target horsepower goals.

## Calculation Resources

For precise sizing, utilize the following industry-standard calculation methods:

*   **Target Horsepower:** Calculate total fuel flow requirements based on your target brake horsepower (BHP) and estimated Brake Specific Fuel Consumption (BSFC).
*   **Duty Cycle:** Aim for a maximum injector duty cycle of 80–85% at peak load to ensure injector longevity and consistent fuel delivery.