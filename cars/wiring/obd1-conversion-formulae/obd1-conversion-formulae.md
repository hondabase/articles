---
summary: 'Index of scaling formulas for converting raw hex values in OBD1 ECU ROM maps into readable engineering units.'
tags: [ecu, tuning, rom-scaling, obd1]
applies_to:
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: beginner
---

# OBD1 ECU ROM Conversion Formulas

This index provides reference formulas for translating raw hexadecimal values from OBD1 ECU ROM maps into human-readable engineering units. These formulas are necessary for understanding and modifying fuel, ignition, and sensor tables.

---

## Scaling Formula Index

| Parameter | Type | Application |
| :--- | :--- | :--- |
| **Low-Cam RPM** | 8-Bit | Low-cam fuel/ignition tables, VTEC crossover. |
| **High-Cam RPM** | 8-Bit | High-cam fuel/ignition tables. |
| **RPM (General)** | 16-Bit | Rev limiters, target idle, system-wide RPM values. |
| **MBar (Pressure)** | 8-Bit | Absolute pressure scale used in all fuel/ignition tables. |
| **Fuel** | 8-Bit | Fuel injection pulse width values. |
| **Advance** | 8-Bit | Ignition spark timing advance. |

---

## Technical Note
These scaling formulas provide the mathematical foundation used by ROM editor software. When developing custom ROM analysis tools, ensure that your codebase correctly implements the specific bit-depth conversion logic (8-bit vs. 16-bit) to ensure table integrity.
