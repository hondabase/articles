---
summary: 'Overview of converting automatic Honda ECUs for manual transmission use through software or hardware modifications.'
tags: [ecu, tuning, conversion, transmission]
applies_to:
  obd: [0, 1, 2]
  brand: Acura/Honda
  models: [civic, crx, del-sol, integra, prelude]
  chassis: [bb, da, dc2, ef, eg, eg-eh]
complexity: intermediate
---

# Automatic to Manual ECU Conversion

Most automatic transmission Honda ECUs can be converted for use with manual transmissions. This conversion can typically be achieved via either software programming or specific hardware modifications on the ECU circuit board.

---

## Conversion Methods

### Software Method
Many third-party ECU management solutions (e.g., custom ROMs) allow you to disable the automatic transmission check. This enables an automatic ECU to run a manual transmission engine without triggering diagnostic codes (such as Code 19: Auto Trans Lockup Solenoid).

### Hardware Method
It is possible to physically modify the ECU circuit board to configure it for manual transmission logic. This method is highly specific to the ECU's circuit board design and requires careful identification of the board revision.

---

## Conversion Resources

The following links provide specific procedures for various ECU models:

*   **OBD0 PS9/PG7/PM7/PR5:** Converting to manual logic.
*   **OBD0 PR4:** Converting an automatic OBD0 PR4 to manual.
*   **OBD1 Civic/Integra:** Converting automatic 92-95 ECUs.
*   **OBD1 P08/P30 JDM:** Converting JDM mini-style ECUs.
*   **OBD1 P13 (Prelude):** Converting 92-95 H22A ECUs.
*   **OBD2 P5M (Prelude):** Converting 97-01 H22A PCMs.

*Please refer to specific technical documentation for your exact ECU part number and board layout before attempting hardware modifications.*
