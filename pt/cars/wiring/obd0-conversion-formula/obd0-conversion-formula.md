---
summary: 'OBD0 conversion formulas for RPM, vehicle speed, fuel, ignition timing, and VTEC parameters. The 16-bit OBD0 RPM formula is used for rev limiters, target idle, and most other 16-bit RPM values in the ROM.'
tags: [ecu, reference, tuning, rom, sensors, wiring, conversion, diagnostics, obd0, rpm, vtec]
complexity: intermediate
---

# OBD0 Conversion Formulas

OBD0 conversion formulas are essential for translating hexadecimal ROM values into real-world parameters used by the engine control unit. The following formulas define conversions for RPM, vehicle speed, fuel injection timing, ignition advance, and VTEC control.

## OBD0 16-Bit RPM Conversion

The 16-bit OBD0 RPM formula is used for:
- Rev limiters
- Target idle speed
- Most other 16-bit RPM values stored in the ROM

This parameter appears throughout the fuel and ignition maps and requires proper conversion for accurate tuning.

## OBD0 Vehicle Speed (VSS) Conversion

The OBD0 VSS conversion translates values stored in RAM address `06Ch` into vehicle speed readings. This parameter is critical for speed-dependent fuel and ignition adjustments.

## OBD0 Fuel Injection Conversion

The OBD0 fuel conversion formula transforms hexadecimal values in fuel maps into pulse width duration measured in milliseconds (ms). Accurate fuel conversion ensures proper air-fuel ratio across all operating conditions.

## OBD0 Ignition Timing Conversion

The OBD0 ignition conversion formula converts hexadecimal ignition map values into crankshaft advance angle measured in degrees (°). This conversion directly affects engine performance and knock resistance.

## OBD0 VTEC Conversion

The OBD0 VTEC formula handles conversion of VTEC control parameters, determining when the variable valve timing system engages.

## OBD0 vs. OBD1 Rev Limiter Differences

OBD0 VTEC ECUs use an OBD0 8-bit rev limiter formula, which differs from the standard 16-bit RPM conversion. This distinction is important when tuning VTEC-equipped vehicles with OBD0 engine management systems.

> [!IMPORTANT]
> All ROM tuning requires accurate understanding of these conversion formulas. Incorrect conversions will result in improper fuel delivery, ignition timing, and VTEC engagement.
