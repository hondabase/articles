---
summary: "Technical reference for converting 8-bit high cam table scale values to real-world RPM for OBD1 Honda ECUs."
tags: [ecu, tuning, sensors, obd1]
applies_to:
  obd: [1]
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: intermediate
---

# OBD1 8-bit High Cam RPM Conversion

This formula is used to convert 8-bit high cam table scale values to real-world RPM.

## Conversion Formula

If *x* represents an 8-bit high-cam scale RPM value, the conversion to RPM is calculated as follows:

**Hi Cam RPM(x) = (1,875,000 * x) / 53,248**

> [!NOTE]
> The divisor **53,248** is equivalent to **D000h** in hexadecimal.

## Assembly Implementation

The following assembly logic demonstrates the fixed-point math used by the ECU to process these values:

| Instruction | Opcode / Notes |
| :--- | :--- |
| `MOV er2, 0ach` | 0805 0 02 00 B5AC4A |
| `MOV er0, #0d000h` | 0808 0 02 00 449800D0 |
| `CLR A` | 080C 1 02 00 F9 |
| `DIV` | 080D 1 02 00 9037 |
| `DIV` Logic | (er0, A) = (er0, A) / er2 |
| `LB A, r0` | 0817 0 02 00 78 |
| `JNE label_081f` | 0818 0 02 00 CE05 |
| `label_081f: STB A, 0aah` | 081F 0 02 00 D5AA |

> [!IMPORTANT]
> The register **r0** contains the least significant byte of **er0**, which represents the most significant word of the quotient. Ensure overflow conditions are handled according to the specific ECU ROM structure when implementing this logic in custom code.