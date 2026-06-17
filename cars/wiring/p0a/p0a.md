---
summary: 'Technical reference for the P0A OBD1 ECU, found in 1994–1995 Honda Accord EX models (F22B engine).'
tags: [ecu, reference, tuning, honda-accord]
applies_to:
  obd: [1]
  models: [accord]
  chassis: [cb-cd]
complexity: advanced
---

# P0A OBD1 ECU Reference (Accord EX)

The **P0A** is an OBD1 ECU equipped in 1994–1995 Honda Accord EX models featuring the F22B engine.

---

## Technical Data

### RAM Map
| Location | Description | Notes |
| :---: | :--- | :--- |
| **00C0** | MAP Sensor | Raw Input |
| **00C1** | TPS Sensor | 8-bit scaling |
| **00C2** | RPM (16-bit) | System-wide RPM reference |
| **00C5** | ECT Sensor | Sensor input voltage |
| **00C6** | VSS | Vehicle speed (km/h) |

### ROM Map
| Location | Description | Notes |
| :---: | :--- | :--- |
| **0C90** | Checksum Jump | Instruction to disable checksum |
| **1997** | Speed Limiter | 0–255 km/h |
| **6000–603F** | Low-Cam Fuel | 1x40 Scalar |
| **6050–6059** | Map Scalar | 1x10 Table |
| **63F8–64C7** | Low-Cam Ignition| 8-bit Advance |

---

## Technical Note
The P0A board shares architectural similarities with the Prelude P13. Many memory locations are derived from early P13 documentation. Always verify address mapping against your specific ROM codebase to ensure accurate table identification.
