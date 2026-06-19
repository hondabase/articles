---
summary: 'Technical reference for calculating Throttle Position Sensor (TPS) percentage from raw 8-bit ECU data in OBD1 Honda systems.'
tags: [ecu, sensors, tps, tuning, obd1]
applies_to:
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eh]
complexity: beginner
---

# OBD1 8-bit TPS Scaling Reference

The Honda OBD1 ECU processes Throttle Position Sensor (TPS) input as an 8-bit value. This value represents the voltage signal converted into a digital range.

## Calculation Formula

To convert a raw 8-bit hexadecimal TPS value into a percentage, use the following formula:

**TPS(x) = (HexToDec(x) / 229.5) * 100**

Where:
*   **x**: The raw 8-bit hexadecimal value from the ECU.
*   **HexToDec(x)**: The decimal equivalent of the hexadecimal input.

## Wide Open Throttle (WOT) Reference

At Wide Open Throttle (WOT), the sensor outputs approximately 4.5V. The ECU maps this voltage to the 8-bit digital range as follows:

*   **Voltage:** 4.5V
*   **Calculation:** (4.5V / 5.0V) * 255 = 229.5
*   **Result:** 229.5 (Decimal) represents 100% throttle position.

> [!NOTE]
> The value 229.5 is the theoretical maximum for the 8-bit TPS range in the OBD1 ECU architecture. Values exceeding this may indicate sensor calibration issues or wiring faults.
