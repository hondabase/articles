---
summary: 'Technical reference for calculating 16-bit RPM values in OBD1 Honda ECUs using the standard conversion formula and Little Endian byte order.'
tags: [ecu, reference, sensors, obd1]
complexity: beginner
---

# OBD1 16-Bit RPM Calculation

To convert a 16-bit raw value into engine speed (RPM) for OBD1 Honda ECUs, use the following formula:

**RPM(x) = 1,875,000 / x**

Where **x** represents the raw 16-bit value retrieved from the ECU memory.

> [!IMPORTANT]
> All 16-bit values in OBD1 ECUs are stored in **Little Endian** byte order. When reading these values from a data stream or memory dump, ensure the bytes are swapped accordingly (Least Significant Byte followed by Most Significant Byte).

## Calculation Reference

| Raw Value (x) | Calculated RPM |
| :--- | :--- |
| 625 | 3,000 |
| 468 | 4,006 |
| 375 | 5,000 |
| 312 | 6,009 |
| 267 | 7,022 |

> [!TIP]
> This calculation is essential for custom data logging and real-time tuning applications where raw memory addresses are being polled directly from the MCU.
