---
summary: 'A spark cut occurs when fuel delivery continues while ignition timing is suppressed, preventing combustion. This technique is commonly used in aftermarket engine management for rev limiting and exhaust effects.'
tags: [ecu, ignition, tuning, diagnostics]
applies_to:
  obd: [0, 1, 2]
complexity: beginner
---

# Spark Cut (Ignition Cut) Fundamentals

A spark cut occurs when the engine continues to receive fuel, but the ignition system is suppressed, preventing the combustion of the air-fuel mixture. 

> [!NOTE]
> Unlike a fuel cut, which stops the delivery of gasoline to the cylinders, a spark cut allows unburned fuel to pass through the combustion chamber and into the exhaust manifold.

## Operational Overview

*   **Mechanism:** The ECU or aftermarket ignition controller disables the signal to the ignition coil or igniter, preventing the spark plug from firing.
*   **Exhaust Effects:** Because fuel is still being injected but not ignited, the unburned mixture enters the exhaust system. In high-performance applications with hot exhaust components, this often results in audible pops or flames exiting the tailpipe.
*   **Application:** Spark cuts are frequently implemented by aftermarket engine management systems for advanced features such as launch control, flat-foot shifting, and aggressive rev limiters.

## Comparison: Spark Cut vs. Fuel Cut

The factory Honda ECU utilizes a **fuel cut** strategy for its primary limiters.

| Feature | Fuel Cut | Spark Cut |
| :--- | :--- | :--- |
| **Primary Action** | Disables fuel injectors | Disables ignition signal |
| **Factory Usage** | Rev Limiter, Speed Limiter | N/A |
| **Aftermarket Usage** | Engine protection | Launch control, anti-lag, pops/bangs |
| **Exhaust Impact** | Minimal | High (unburned fuel in exhaust) |

> [!WARNING]
> Excessive use of spark cut can lead to increased exhaust gas temperatures (EGTs), potential damage to catalytic converters, and accelerated wear on exhaust valves and turbocharger components.