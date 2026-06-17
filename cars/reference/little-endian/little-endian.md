---
summary: "An overview of the Little Endian memory storage format used by processors in Honda ECU architectures, including the OKI 66k."
tags: [reference, ecu, architecture, memory]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Little Endian Memory Format

Little Endian is a method of storing multi-byte data values in memory. This architecture is utilized by various processors found in Honda ECUs, most notably the OKI 66k series.

## Data Storage Logic

In a Little Endian system, the **least significant byte (LSB)** is stored at the lowest memory address. When the processor reads a multi-byte value, it interprets the first byte encountered as the lowest order of magnitude.

### 16-Bit Value Calculation

For 16-bit values, the memory layout consists of two bytes. The value is calculated using the following formula:

**Value = (Second Byte × 256) + First Byte**

> [!NOTE]
> This is distinct from Big Endian architecture, where the most significant byte is stored at the lowest memory address. Always verify the byte order when parsing raw hex dumps or binary calibration files from the ECU.

### Example
If a 16-bit memory address contains the hex values `0x34` followed by `0x12`:

*   **First Byte (LSB):** `0x34`
*   **Second Byte (MSB):** `0x12`
*   **Result:** `(0x12 * 256) + 0x34` = `0x1234` (Decimal 4660)