---
summary: 'Technical reference for calculating 8-bit Throttle Position Sensor (TPS) values in OBD1 Honda ECUs, including the conversion formula and WOT voltage scaling.'
tags: [ecu, sensors, tuning, obd1]
complexity: beginner
---

# OBD1 8-Bit TPS Scaling Reference

The OBD1 ECU processes Throttle Position Sensor (TPS) data using an 8-bit integer value. This reference provides the formula for converting raw hexadecimal ECU data into a percentage of throttle opening.

## Conversion Formula

To calculate the throttle percentage from an 8-bit TPS value ($x$), use the following formula:

$$\text{TPS}(x) = \left( \frac{\text{hex\_to\_dec}(x)}{229.5} \right) \times 100\%$$

## Wide Open Throttle (WOT) Calibration

The ECU defines Wide Open Throttle (100%) based on a voltage threshold of 4.5V. The 8-bit scaling is derived as follows:

*   **WOT Voltage:** 4.5V
*   **Reference Voltage:** 5.0V
*   **Calculation:** $(4.5 / 5.0) \times 255 = 229.5$

> [!NOTE]
> The value **229.5** represents the raw 8-bit integer value corresponding to 100% throttle opening. Values exceeding this threshold are typically clamped by the ECU firmware.
