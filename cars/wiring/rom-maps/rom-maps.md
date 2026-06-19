---
summary: 'An index of memory addresses and ROM map definitions for various Honda OBD1 and OBD0 ECU families, facilitating custom tuning and firmware modification.'
tags: [ecu, tuning, rom, reverse-engineering, reference]
applies_to:
  models: [accord, civic, crx, del-sol, integra, prelude]
  chassis: [bb, da, dc2, ef, eg, eg-eh, ek]
complexity: advanced
---

# ROM Map Index

This index serves as a collaborative reference for memory addresses and ROM map definitions within Honda ECU firmware. Understanding these locations is essential for reverse engineering, customizing fuel/ignition maps, and developing performance firmware.

---

## OBD1 ECU Map References
OBD1 ECUs share a largely standardized architecture, simplifying the development of custom ROM analysis tools.

*   **Civic/Integra Platforms:** Mapping for popular ECUs like the P28, P30, and P72.
*   **Performance ROMs:** References for UberData and high-resolution P72 codebases.

## OBD0 ECU Map References
OBD0 ECUs require generation-specific map definitions due to the lack of standardization across early firmware.

*   **VTEC ECUs:** Mapping for PW0 and PR3 units.
*   **Multi-Point Fuel Injection (MPFI):** Mapping for PM6 and PR4 series ECUs.

---

## Resources for ROM Development

*   **Assemblers/Disassemblers:** Tools like ASM662 allow for analyzing and reassembling ECU binary files.
*   **Conversion Formulas:** Use the [OBD1 Conversion Formulae](/cars/wiring/obd1-conversion-formulae) or [OBD0 Conversion Formula](/cars/wiring/obd0-conversion-formula) to translate hexadecimal ROM values into engineering units (RPM, fuel pulse width, spark advance).
*   **Compatibility:** For information on running different firmware codebases on unintended hardware, refer to the [OBD1 Code Compatibility Guide](/cars/wiring/obd1-code-compatibility).

---

## Technical Note
These memory locations are based on community-sourced reverse engineering. Firmware variations may exist between different production regions and ECU part numbers. **Always verify address mapping against your specific ROM codebase before applying modifications.**
