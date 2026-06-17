---
summary: 'Technical reference for the Honda Engine Coolant Temperature (ECT) sensor, including ECU lookup tables and temperature conversion data for OBD1 systems.'
tags: [ecu, reference, tuning, rom, sensors, diagnostics]
applies_to:
  obd: [1]
  models: [all]
complexity: intermediate
---

# Engine Coolant Temperature (ECT) Sensor Reference

The Engine Coolant Temperature (ECT) sensor measures the temperature of the engine coolant. This data is critical for the ECU to determine fuel enrichment, ignition timing, and idle control strategies.

![Stock Honda ECT sensor](honda_stock_coolant_temp.jpg)

> [!IMPORTANT]
> The following data is derived from laboratory testing of a 1993 EDM CRX OBD1 sensor. While these values are standard for Honda OBD1 applications, minor variations may occur based on sensor age and environmental conditions.

## ECU Temperature Conversion Table

The ECU utilizes an internal lookup table to convert raw sensor voltage (represented as an 8-bit hex value from 0–255) into a readable temperature value. The following array represents the temperature mapping for values 255 down to 0.

| Hex Index (Dec) | Temp (°C) | Hex Index (Dec) | Temp (°C) |
| :--- | :--- | :--- | :--- |
| 255–210 | -1 | 100 | 30.7 |
| 209 | 0 | 80 | 44.0 |
| 180 | 6.0 | 60 | 60.0 |
| 160 | 12.0 | 40 | 75.0 |
| 140 | 21.0 | 20 | 95.0 |
| 120 | 26.0 | 0 | 101.0 |

### Full Temperature Array
The following data represents the conversion array used by the ECU firmware:

```text
Array( -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, -1#, 0#, 0.5, 1#, 1.6, 2.2, 2.9, 3.5, 4.1, 4.7, 5.4, 6#, 6.5, 7#, 7.5, 8#, 8.5, 8.9, 9.4, 9.8, 10.3, 10.7, 11.1, 11.6, 12#, 12.3, 12.7, 13#, 13.5, 13.9, 14.4, 14.8, 15.3, 15.7, 16.2, 16.6, 17.1, 17.5, 17.8, 18.2, 18.5, 18.9, 19.3, 19.8, 20.2, 20.6, 21#, 21.4, 21.8, 22.3, 22.7, 23.1, 23.5, 23.9, 24.2, 24.6, 24.9, 25.3, 25.6, 26#, 26.3, 26.7, 27#, 27.4, 27.8, 28.1, 28.5, 28.9, 29.3, 29.6, 30#, 30.3, 30.7, 31#, 31.3, 31.7, 32#, 32.3, 32.7, 33#, 33.4, 33.7, 34.1, 34.4, 34.8, 35.1, 35.5, 35.9, 36.2, 36.6, 36.9, 37.3, 37.6, 38#, 38.4, 38.8, 39.1, 39.5, 39.9, 40.3, 40.6, 41#, 41.4, 41.8, 42.1, 42.5, 42.9, 43.3, 43.6, 44#, 44.4, 44.8, 45.3, 45.7, 46.1, 46.5, 46.9, 47.3, 47.8, 48.2, 48.6, 49#, 49.5, 50.1, 50.6, 51.2, 51.7, 52.3, 52.8, 53.4, 53.9, 54.5, 55#, 55.5, 56#, 56.5, 57#, 57.5, 58#, 58.5, 59#, 59.5, 60#, 60.5, 61#, 61.7, 62.4, 63.1, 63.8, 64.5, 65.2, 65.9, 66.6, 67.3, 68#, 68.7, 69.4, 70.1, 70.8, 71.5, 72.2, 72.9, 73.6, 74.3, 75#, 75.8, 76.6, 77.5, 78.3, 79.1, 79.9, 80.7, 81.5, 82.4, 83.2, 84#, 85.2, 86.4, 87.7, 88.9, 90.1, 91.3, 92.6, 93.8, 95#, 96.7, 98.3, 100#, 101#, 101#, 101#, 101#, 101#, 101#, 101#, 101#, 101#, 101#, 101#, 101#, 101#, 101#, 101#, 101#, 101#, 101#, 101#, 101#, 101#, 101#, 101#, 101#)