---
summary: 'Archived P72/P75 OBD1 MAP-byte formulas and calibration values for stock and uncorked ROM code.'
applies_to:
  obd: [1]
  ecus: [P72, P75]
complexity: advanced
tags:
  - tuning
  - sensor
  - maps
---

# OBD1 8-bit MAP calibration in millibars

This reference preserves the MAP conversion formulas and P72/P75 calibration values
documented by the original pgmfi community. Use them to understand the archived ROM
code, not as a universal calibration for every Honda ECU or MAP sensor.

> **Note:** The source describes these raw values as being for P72/P75 code and says
> most OBD1 ECUs follow the same rule. Verify the actual ROM code, fuel-cut offset, and
> sensor calibration before applying the formulas elsewhere.

## Basic MAP-byte formulas

The archived notes assume that the stock MAP sensor's maximum reading is `1764 mbar`.

Stock code halves the MAP byte:

```text
pressure_mbar = (1764 / 255) * (map_byte / 2)
```

When the ROM's MAP value is uncorked, the final division by two is removed:

```text
pressure_mbar = (1764 / 255) * map_byte
```

The same notes document these voltage formulas:

```text
stock map: volts = (5 / 255) * ((raw / 2) + fuel_cut)
boost map: volts = (5 / 255) * (raw + fuel_cut)
```

The listed stock fuel-cut value is `24`, editable at address `0x4DCC` in the referenced
code.

## Voltage conversion notes

The archived page includes these two linear conversions:

```text
inHg = 20 * volts / 1.85 - 30.81
mbar = 365.9 * volts - 29.9
```

They are derived on the page from the following points:

| Scale | Point 1 | Point 2 |
| :--- | :--- | :--- |
| Vacuum | 2.85 V = 0 inHg | 1.0 V = 20 inHg |
| Absolute pressure | 2.85 V = 1013 mbar | 1.0 V = 336 mbar |

## Archived P72/P75 calibration values

The following values are transcribed from the source. The first table uses the source's
full raw-value labels, while the second shows the corresponding halved stock-map labels.

> **Caution:** The source labels the final full-scale row as `256`, although an unsigned
> 8-bit value tops out at `255`. The value is preserved here as an endpoint label from the
> original notes.

| Source raw label | Voltage | Pressure |
| :---: | :---: | :---: |
| 0 | 0.471 V | 142.3 mbar |
| 24 | 0.706 V | 228.4 mbar |
| 48 | 0.941 V | 314.5 mbar |
| 80 | 1.255 V | 429.3 mbar |
| 128 | 1.725 V | 601.5 mbar |
| 176 | 2.196 V | 773.6 mbar |
| 208 | 2.510 V | 888.4 mbar |
| 224 | 2.667 V | 945.8 mbar |
| 240 | 2.824 V | 1003.0 mbar |
| 256 | 2.980 V | 1061.0 mbar |

| Halved stock-map label | Voltage | Pressure |
| :---: | :---: | :---: |
| 0 | 0.471 V | 142.3 mbar |
| 12 | 0.706 V | 228.4 mbar |
| 24 | 0.941 V | 314.5 mbar |
| 40 | 1.255 V | 429.3 mbar |
| 64 | 1.725 V | 601.5 mbar |
| 88 | 2.196 V | 773.6 mbar |
| 104 | 2.510 V | 888.4 mbar |
| 112 | 2.667 V | 945.8 mbar |
| 120 | 2.824 V | 1003.0 mbar |
| 128 | 2.980 V | 1061.0 mbar |

## Sensor interface

![Three-wire MAP sensor interface schematic](mapsensor.jpg)
*Archived schematic for the three-wire MAP sensor interface.*

## Related

- [MAP sensor overview](/cars/electronics/map-sensor)
- [Understanding fuel and ignition maps](/cars/electronics/understanding-maps)
