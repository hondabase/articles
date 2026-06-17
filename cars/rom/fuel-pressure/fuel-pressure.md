---
summary: 'Learn how adjusting static fuel pressure affects fuel delivery and injector performance in Honda fuel systems.'
tags: [tuning, fuel, injectors, diagnostics]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Fuel Pressure Tuning and Specifications

Increasing static fuel pressure is a method to increase the total volume of fuel delivered by the injectors. However, excessively high fuel pressure can negatively impact injector response times, potentially sacrificing the precision and crispness of fuel delivery.

## OEM Specifications

Honda OEM fuel pressure should be maintained within the following range:

*   **Target Pressure:** 38–42 psi

> [!IMPORTANT]
> While increasing fuel pressure can compensate for fuel delivery limitations, it does not replace the need for properly sized injectors for your specific power goals.

## Considerations for Tuning

When adjusting fuel pressure, consider the following technical impacts:

*   **Injector Latency:** Higher fuel pressure increases the force required for the injector solenoid to open the pintle. This can lead to increased dead times (latency), which may require adjustments to the ECU's injector compensation tables.
*   **Spray Pattern:** Operating significantly outside of the manufacturer's designed pressure range may degrade the injector's spray pattern, leading to poor atomization and combustion efficiency.
*   **Pump Load:** Higher static pressure increases the load on the fuel pump, which may reduce the pump's total flow capacity at high RPM and high duty cycles.

> [!TIP]
> Always verify fuel pressure using a calibrated mechanical gauge connected to the fuel rail service port while the engine is idling and the vacuum reference line is disconnected.