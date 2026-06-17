---
summary: 'An overview of latching logic gates, such as the 74HC373, used to hold and preserve the state of I/O lines in ECU hardware.'
tags: [ecu, hardware, logic, electronics]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Latch Logic and ECU Implementation

A latch is a digital logic circuit used to hold or preserve the state of an input signal. In ECU hardware, latches are critical for maintaining stable data states across I/O lines.

## Functionality
Latches, such as the [74HC373](/cars/rom/74hc373), act as transparent logic gates. When the enable signal is active, the output follows the input; when the enable signal is inactive, the output is "latched" or held at its last state regardless of changes to the input.

> [!NOTE]
> Latches are frequently used in ECU memory addressing and data bus management to ensure that signals remain stable during read/write operations.

## Common Applications
* **Data Bus Buffering:** Isolating the MCU from the data bus to prevent signal degradation.
* **Address Decoding:** Holding address bits stable while the memory chip performs a read or write cycle.
* **I/O Expansion:** Allowing a limited number of MCU pins to control a larger number of peripheral devices.

## Technical Specifications
The 74HC373 is an octal transparent latch with 3-state outputs. It is commonly found in OBD1 and OBD2 ECU designs to interface the microcontroller with external ROM or RAM chips.

| Feature | Specification |
| :--- | :--- |
| **Logic Family** | HC (High-speed CMOS) |
| **Configuration** | Octal (8-bit) |
| **Output Type** | 3-State |
| **Function** | Transparent Latch |

{{> resistor-color-codes }}