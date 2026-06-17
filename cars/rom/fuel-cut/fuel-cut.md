---
summary: 'A fuel cut disables fuel delivery to the engine, typically triggered by rev limiters, launch control, or boost cut routines.'
tags: [ecu, tuning, rom, sensors, fuel-system]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Fuel Cut Operation and Theory

A fuel cut occurs when the ECU completely disables fuel delivery to the engine. This mechanism is primarily utilized as a safety or performance strategy within the following routines:

*   **Rev Limiter:** Prevents engine over-revving by cutting fuel at a specified RPM threshold.
*   **Launch Control:** Limits engine speed during a standing start to optimize traction.
*   **Boost Cut:** Protects the engine from over-boost conditions by cutting fuel when manifold pressure exceeds a programmed limit.

## Technical Considerations

> [!NOTE]
> Fuel cut rev limiters are often perceived as harsh. Because the fuel supply is interrupted, the engine may experience a momentary lean condition during the cut cycle.

### Comparison with Spark Cut
While the stock Honda ECU utilizes a fuel cut for its limiter routines, many aftermarket ignition systems employ a **spark cut** instead. 

*   **Fuel Cut:** Stops the delivery of fuel. It is the standard method for factory ECUs.
*   **Spark Cut:** Interrupts the ignition signal to the spark plugs. This is often considered less harsh on the engine internals, as it prevents the combustion of unburnt fuel in the exhaust stream, though it can lead to raw fuel accumulation in the exhaust system if used excessively.

> [!IMPORTANT]
> The stock Honda ECU does not support spark cut functionality. Any implementation of spark-based limiting requires an external aftermarket ignition controller.