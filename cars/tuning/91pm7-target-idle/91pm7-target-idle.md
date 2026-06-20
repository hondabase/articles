---
summary: 'Learn how to modify the target idle RPM in OBD0 PM7 ECU ROMs by locating and adjusting the hex idle target string.'
tags: [ecu, tuning, idle, obd0]
applies_to:
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: beginner
---

# Modifying Target Idle RPM in OBD0 PM7 ECUs

To adjust the target idle RPM in an OBD0 PM7 ECU, you must locate and modify the hex idle target string within the ROM file.

## Idle Target Identification
The idle target values are stored as a string of six hexadecimal values representing different engine operating conditions. 

> [!IMPORTANT]
> All values must be calculated using the **OBD0 16-bit RPM formula**.

### Example Modification
In the `PM7FOR6_12-15-02.BIN` ROM, the default idle target string is:
`0A08 09C4 0964 0A77 09C4 0964`

To set a constant target idle of 1000 RPM, replace all six values in the string with the hex equivalent for 1000 RPM:
`0753 0753 0753 0753 0753 0753`

## Reference
{{> obd0-16bit-rpm-formula }}
