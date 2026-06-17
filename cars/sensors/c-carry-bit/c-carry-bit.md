---
summary: 'An overview of the carry bit (C) functionality within 8051 and Oki 66k architectures, focusing on arithmetic overflow tracking and bit manipulation.'
tags: [8051, oki-66k, architecture, assembly, programming]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: advanced
---

# 8051 and Oki 66k Carry Bit (C) Reference

In the 8051 architecture, "C" denotes the carry bit. This flag is automatically updated during arithmetic operations to track overflow conditions.

## Functional Overview

The carry bit serves two primary purposes in embedded microcontroller operations:

*   **Arithmetic Overflow Tracking:** The bit is set when an arithmetic operation results in a value exceeding the capacity of the register (overflow).
*   **Bit Manipulation:** The bit acts as a temporary storage register for bit-level data transfers.

## Architecture-Specific Implementation

### Oki 66k Architecture
The Oki 66k architecture utilizes the carry flag for efficient data movement and logic operations. The following instructions provide direct access to the carry flag:

*   **MB C, x:** Moves the value of a specified source into the carry flag.
*   **MB x, C:** Moves the current state of the carry flag into a specified destination.

> [!NOTE]
> While the carry bit is primarily used for arithmetic status, its role as a single-bit buffer is critical for complex logic routines and bit-shifting operations within the 66k instruction set.