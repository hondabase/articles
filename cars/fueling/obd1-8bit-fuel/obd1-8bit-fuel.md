---
summary: 'Technical reference for calculating fuel pulse width and duty cycle using 8-bit ROM table values in Honda OBD1 engine management systems.'
tags: [ecu, tuning, fuel, sensors, obd1]
applies_to:
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: beginner
---

# OBD1 8-Bit Fuel Calculation Reference

In Honda OBD1 ROM editors, fuel table values are stored as 8-bit integers. To interpret these values into meaningful fuel metrics, use the following mathematical conversions.

## Fuel Value Calculation
Given a table value **v** and a multiplier **m**, the fuel value is calculated as:

**Fuel(v, m) = (v * m) / 4**

The resulting value is proportional to the fuel mass entering the engine, with an effective range of 0–16256.25.

## Pulse Width and Duty Cycle
To determine the relationship between the ROM table value and injector performance, use the following formulas:

### Pulse Width (PW)
**PW (ms) = (v * m) / 400 + 0.60ms**

### Duty Cycle
**Duty Cycle = (RPM * (v * m + 240)) / 24,000,000**

> [!IMPORTANT]
> These formulas are derived from empirical data and represent theoretical calculations. Always verify fuel delivery and injector duty cycle using real-time data logging and wideband oxygen sensor feedback.

> [!NOTE]
> The constant **0.60ms** in the pulse width formula accounts for injector latency (dead time). This value may vary depending on the specific injector hardware installed.
