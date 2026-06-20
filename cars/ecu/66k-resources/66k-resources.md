---
summary: 'Comprehensive resource list for the Oki 66K processor family used in Honda OBD1 and OBD2 ECUs, including assemblers, disassemblers, and syntax definitions.'
tags: [ecu, reference, tuning, rom, sensors, oki-66k]
applies_to:
  models: [accord, civic, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, eg, eh, ek, em, ep, na1, na2]
complexity: advanced
---

# Oki 66K Processor Resources

This document provides a centralized reference for the Oki 66K processor family, which serves as the foundation for most Honda OBD1 and OBD2 engine control units.

## Documentation

*   **[66k Assembler Docs](/cars/diagnostics/66k-assembler-docs):** Official factory documentation regarding the Oki 66xxx processor architecture.
*   **66k Operations:** A comprehensive list of standard 66xxx assembler operations and their specific implementation within PGM-FI systems.

## Utilities

### Assemblers and Disassemblers

*   **[ASM662](/cars/diagnostics/asm662):** Open-source assembler/disassembler for the Oki Nx8/200 66k processor series.
*   **66507 DASM:** Specialized disassembler for the OBD2 Oki `66507` processor.

### Development Environment Support

*   **jEdit Mode Definition:** `assembly-Oki66k.xml` provides syntax highlighting and structure for the jEdit text editor.
*   **okiedit:** A Win32-based syntax-highlighting editor specifically designed for 66k assembly development.
*   **TextPad Syntax:** Custom syntax definition files for TextPad 4.6 to support 66k assembly formatting.

> [!NOTE]
> Ensure that your development environment is configured for the specific processor variant (e.g., 66507 vs. 66200) to avoid instruction set mismatches during disassembly or assembly.
