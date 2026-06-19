---
summary: 'Troubleshooting guide for common configuration errors, MAP sensor column rescaling issues, and VTEC bytes modifications in TurboEdit OBD0 tuning software.'
tags: [tuning, rom, software, diagnostics, obd0]
applies_to:
  models: [civic, crx]
  chassis: [ef]
complexity: intermediate
---

# Troubleshooting Common TurboEdit (TE) Issues

TurboEdit is a ROM editing suite for OBD0 Honda ECUs, primarily the PM6. Because OBD0 ECUs utilize an 8-bit processor structure and limited memory space, custom codebases (such as the `ng` series) require specific configuration rules.

## 1. Active Check Engine Lights (CEL)

Before attempting to tune or calibrate a custom ROM, ensure the vehicle is free of active trouble codes.

> [!IMPORTANT]
> If a sensor error triggers a CEL, the ECU will enter backup or "limp" mode, using conservative ignition and fueling lookups.

* **The Fix:** Diagnose and resolve all mechanical and electrical sensor faults prior to tuning. A map cannot be correctly calibrated if the ECU is bypassing its normal ROM tables.

## 2. Clipped Pulse Widths (Incorrect Fuel Multiplier)

This issue typically occurs when scaling maps for larger fuel injectors in `ngXX` codebases. If you copy a map or input new values, you may find the values cap out or display incorrectly.

### The Math Constraint

Because the OBD0 ECU is an 8-bit platform, the decimal value stored at any map coordinate address (`Dec At Addy`) cannot exceed 255. In the `ng` codebase, the raw byte value is translated to injector pulse width (in milliseconds) using the following formulas:

$$a = 2^{\text{Column Multiplier}}$$

$$\text{Pulsewidth (ms)} = \frac{\text{Dec At Addy} + \frac{224}{a}}{\frac{208}{a}}$$

If the column multiplier is manually configured too low (for example, set to `3`), the maximum achievable pulse width is restricted to **10.88 ms**, regardless of engine load.

* **The Fix:** In TurboEdit, navigate to **Tools** -> **Options** and ensure the fuel multiplier option is set to **Auto Detect**. This allows the software to scale the multiplier dynamically to prevent clipping.

## 3. MAP Sensor Column Alignment (Stock vs. `ng48`)

When migrating map tables from a stock OBD0 BIN to a custom `ng48` codebase, copy-pasting tables directly causes severe tuning issues.

### The Shift in Pressure Columns

Directly pasting cell values shifts the load index because the pressure column headers (MAP index) are scaled differently between factory ROMs and `ng48` ROMs.

| Map Column | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 | 15 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Stock (inHg)** | 26 | 24 | 22 | 21 | 19 | 18 | 16 | 14 | 13 | 11 | 9 | 8 | 4 | 1 | 1.3 psi |
| **`ng48` (inHg)** | 31 | 29 | 26 | 24 | 22 | 20 | 18 | 16 | 14 | 12 | 10 | 8 | 5 | 2 | 0 psi |

Values that once controlled a stable factory engine idle are shifted into cells that represent heavy deceleration, causing the engine to run lean or stall.

* **The Fix:** Use a map translation spreadsheet to interpolate and scale the fuel/ignition values to match the correct pressure headers before inserting them into the custom BIN.

## 4. VTEC Activation Failure in `ng60`

When using VTEC conversion scripts or custom boards on an OBD0 ECU, the software VTEC toggle button in the TurboEdit user interface may not function correctly.

* **The Fix:** Use a hex editor to manually overwrite the VTEC control bytes in the `ng60` ROM BIN at the following offsets:

| Offset | Value |
| :--- | :--- |
| **0x2882** | `0x21` |
| **0x2888** | `0xA3` |
