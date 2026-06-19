---
summary: 'A directory of conversion formulas for OBD0 ECU ROM maps, including scaling factors for RPM, fuel, ignition, and VTEC parameters.'
tags: [ecu, tuning, rom-scaling, obd0]
applies_to:
  models: [civic, crx, integra]
  chassis: [da, ef]
complexity: intermediate
---

# OBD0 ECU ROM Map Conversion Formulas

This guide provides the necessary conversion formulas for translating hex values in OBD0 ROM maps into readable engineering units. These formulas are essential for effective ECU tuning and modification.

---

## Conversion References

*   **16-Bit RPM:** Used for rev limiters, target idle speed, and other 16-bit RPM-based parameters.
*   **VSS (Vehicle Speed Sensor):** Formula for converting RAM location `06Ch` into actual vehicle speed.
*   **Fuel Maps:** Used to convert raw hex values in fuel tables into injector pulse width (milliseconds).
*   **Ignition Maps:** Used to convert hex map values into degrees of spark advance.
*   **VTEC Activation:** Scaling factors for VTEC engagement parameters.
*   **8-Bit Rev Limit:** Specific scaling for rev-limiters on OBD0 VTEC-capable ECUs.

---

## Technical Note
These conversion formulas are specific to the OBD0 architecture. Always verify that your specific ROM codebase supports these scaling factors, as variations may exist between different ECU part numbers or regional firmwares.
