---
summary: 'Technical guide on converting 8-bit hex values from OBD1 ECU low-cam tables into readable RPM values.'
tags: [ecu, tuning, rom-scaling, obd1]
applies_to:
  obd: [1]
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: advanced
---

# OBD1 8-Bit Low-Cam RPM Scaling

OBD1 ECU ROMs use 8-bit hex values to define RPM-based parameters within the low-cam fuel and ignition tables. Converting these hex values into actual engine RPM requires applying specific piecewise linear scaling formulas.

---

## Scaling Formula

The RPM value is determined by the input hex value (Y, ranging from 0 to 255) using a four-stage piecewise linear scale:

| Hex Range | RPM Range |
| :--- | :--- |
| `00h`–`40h` | 500 – 1,000 RPM |
| `40h`–`80h` | 1,000 – 2,000 RPM |
| `80h`–`C0h` | 2,000 – 4,000 RPM |
| `C0h`–`FFh` | 4,000 – 8,000 RPM |

### Calculation Logic
The conversion relies on the following piecewise logic:

1.  **Q =** Integer part of `Y / 64`
2.  **R =** Remainder of `Y / 64`
3.  **RPM =** `(2^Q) * (IntegerPart(R * 500 / 64) + 500)`

---

## Technical Implementation Notes

This piecewise approach defines four distinct linear slopes, which is how the OBD1 ECU architecture handles RPM scaling across different load ranges.

*   **Precision:** These formulas are approximations used by the ECU firmware. Minor variations may occur compared to ideal continuous exponential scales.
*   **Tuning Tools:** Modern ROM editing software (e.g., Crome, Hondata, HTS) handles this scaling automatically. This reference is primarily for those developing custom ROM analysis or diagnostic tools.

*Always verify your calculated values against a known baseline ROM in your editing software to ensure accuracy.*
