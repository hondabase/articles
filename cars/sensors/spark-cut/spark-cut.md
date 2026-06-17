---
summary: 'A spark cut occurs when fuel delivery continues while ignition timing is suppressed, preventing combustion. This technique is commonly used in aftermarket ignition systems for performance effects.'
tags: [ecu, ignition, tuning, rev-limiter]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Spark Cut Ignition Strategies

A spark cut occurs when the engine continues to receive fuel, but the ignition system is inhibited, preventing combustion. This process allows unburnt fuel to pass through the combustion chamber and into the exhaust manifold.

> [!CAUTION]
> Spark cutting results in unburnt fuel entering the exhaust system. Prolonged use can lead to excessive heat buildup, damage to catalytic converters, and potential exhaust component failure.

## Implementation and Usage

Spark cuts are typically implemented via aftermarket ignition controllers or programmable engine management systems. While the factory ECU utilizes a fuel cut strategy for rev and speed limiting, spark cutting is often employed for specific performance applications, such as:

*   **Anti-Lag Systems (ALS):** Maintaining turbocharger spool by igniting fuel in the exhaust manifold.
*   **Launch Control:** Managing engine output during standing starts.
*   **Exhaust Effects:** Generating combustion events within the exhaust system.

## Comparison: Spark Cut vs. Fuel Cut

| Feature | Fuel Cut | Spark Cut |
| :--- | :--- | :--- |
| **Combustion** | Ceases due to lack of fuel | Ceases due to lack of ignition |
| **Exhaust State** | Lean/Air-only | Rich/Unburnt fuel |
| **Primary Use** | Factory safety/Economy | Performance/Turbo spooling |
| **Component Stress** | Low | High (Exhaust/Turbo) |

> [!NOTE]
> Factory Honda ECUs are programmed to use fuel-based limiting strategies to protect the catalytic converter and maintain engine longevity. Modifying these parameters to implement spark-based limiting requires a standalone or modified ECU environment.