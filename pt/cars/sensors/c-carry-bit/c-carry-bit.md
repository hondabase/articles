---
summary: 'An overview of the Carry (C) bit functionality within 8051 and Oki 66k architectures, focusing on arithmetic overflow and bit manipulation.'
tags: [8051, oki66k, architecture, assembly, registers]
applies_to:
  obd: [0, 1, 2]
complexity: advanced
---

# 8051 and Oki 66k Carry (C) Bit Reference

In the 8051 architecture, "C" denotes the Carry bit. This flag is primarily used to record arithmetic overflows; when an arithmetic operation exceeds the register's capacity, the Carry bit is set to indicate the overflow state.

## Functional Overview

The Carry bit serves two primary roles in low-level system operations:

*   **Arithmetic Overflow:** Automatically tracks carry-out operations during addition or borrow operations during subtraction.
*   **Bit Storage:** Acts as a single-bit register for temporary data storage and bit-level transfer operations.

## Architecture-Specific Implementation

### Oki 66k Integration
The Oki 66k architecture extends the utility of the Carry bit through dedicated instructions, allowing for efficient interaction between the flag and memory or register locations.

> [!IMPORTANT]
> Use the following instructions to interface directly with the carry flag in Oki 66k environments:

| Instruction | Description |
| :--- | :--- |
| `MB C, x` | Move bit from location `x` to the Carry flag. |
| `MB x, C` | Move bit from the Carry flag to location `x`. |

> [!TIP]
> The Carry bit is frequently utilized in bit-masking routines and conditional branching logic where a single-bit state must be preserved across instruction cycles.