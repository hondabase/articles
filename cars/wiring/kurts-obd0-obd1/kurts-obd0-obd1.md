---
summary: 'Complete guide for converting 1988-1991 (OBD0) Honda wiring harnesses to run 1992-1995 (OBD1) ECUs, including engine harness modification and dash wiring conversion.'
tags: [conversion, wiring, honda-tuning, obd0-to-obd1]
applies_to:
  obd: [0, 1]
  models: [civic, crx, del-sol, integra]
  chassis: [da, dc2, ef, eg, eg-eh, ek]
complexity: advanced
---

# Honda OBD0 to OBD1 Wiring Conversion Guide

This guide details the process of converting an 1988-1991 (OBD0) Honda wiring harness to accommodate a 1992-1995 (OBD1) ECU. While focused on the D16Z6 engine installation, these principles apply to most OBD1 engine swaps into OBD0 chassis.

*   **Vehicle compatibility:** 4th generation Civic (88-91), 2nd generation CRX (88-91).
*   **Engine compatibility:** Commonly used for D16Z6 (SOHC VTEC) and D16Y8 swaps.

### Required Parts and Preparation

*   OBD0 chassis (e.g., 89 CRX Si).
*   OBD1 engine (e.g., 93 D16Z6).
*   Engine harness from the OBD1 engine (with ECU plugs).
*   OBD1 ECU (e.g., P28 manual).
*   OBD1 distributor.
*   Correct-spec fuel injectors.
*   Relevant service manuals (Chilton/Haynes/Helms).

---

## OBD0 to OBD1 Conversion Overview

The conversion process primarily involves two areas: the engine harness and the interior dash/ECU harness. The OBD1 engine harness will not plug directly into the OBD0 chassis harness due to incompatible connectors.

**Pro-tip:** Pre-built conversion harnesses are now widely available, which can save considerable time. However, this guide covers the manual wiring modification process.

---

### Engine Harness Conversion

Converting the stock OBD0 harness is required.

**Tip:** Removing the engine harness from the car is recommended for easier access and modification.

#### 1. Injection Resistor
You have two options for the fuel injectors:
*   **Retain OBD0 MPFI Injectors:** Simplest approach. Keep the stock injection resistor box.
*   **Convert to OBD1 Injectors:** Pull the `yel/blk` wire from the green injection resistor plug and relocate it into the OBD1 harness's 8-wire gray plug (which features an integrated clip connecting all `yel/blk` wires).

#### 2. Injector Wiring
*   If retaining OBD0 injectors, no changes are needed.
*   If using OBD1 injectors, replace the OBD0 injector plugs with OBD1 plugs. Match wire colors accordingly (brown, red, light blue, plain yellow). The `yel/blk` wire connects to the injection power source.

#### 3. Oxygen Sensor (O2)
A 4-wire O2 sensor upgrade is necessary.
1.  Connect the `yel/blk` wire to a switched 12V source (or the OBD1 8-wire plug).
2.  Connect the `grn/wht` wire to the existing `grn/wht` wire on the OBD0 harness.
3.  Connect the `org/blk` wire directly to the ECU pin for O2 sensor heater control.
4.  The final `white` wire is the O2 sensor signal itself. Splice the OBD1 plug wire to the existing signal wire on the OBD0 harness.

#### 4. Distributor Rewiring
There are 7-wire and 2-wire plugs. Replace the OBD0 plugs on your chassis harness with the OBD1 distributor plugs from the OBD1 engine harness. Match the wiring colors precisely between the distributor and the engine harness.

#### 5. VTEC and Oil Pressure
*   **VTEC Activation:** Add a `grn/yel` wire from the VTEC solenoid to the ECU.
*   **VTEC Oil Pressure:** Run the `black` wire to a chassis ground and the `blue/blk` wire to the ECU.

---

### Dash/Interior Wiring Conversion

You must adapt the OBD1 ECU plugs to the OBD0 interior wiring.

1.  **Build a conversion harness:** Use male ECU plugs from an OBD1 harness and female plugs from an OBD0 ECU. Solder the appropriate wires together according to the pin-out table below.
2.  **Splice wires directly:** Cut the OBD0 plugs and splice the OBD1 plug wires directly to the dash harness wires.
3.  **Repin:** Unpin OBD0 connectors if compatible with OBD1 pins (this may not work for all pins).

---

### ECU Pin-out Reference Tables

#### A Plug (1992-1995 OBD1 Plug)

| Pin | Function | 92-95 Wire |
| :--- | :--- | :--- |
| A1 | Injector 1 | brn |
| A2 | Injector 2 | red |
| A3 | Injector 3 | lt. blu |
| A4 | Main Relay | grn/yel |
| A5 | EACV | grn/wht |
| A7 | Check Engine Light | grn/org |
| A8 | A/C Clutch Relay | blk/red |
| A11 | Ign. Unit Signal | red/grn |
| A12 | Main Relay | blk |
| A13 | Main Relay | yel/blk |
| A14 | Injector 4 | yel |
| A15 | VTEC | org/wht |
| A16 | O2S Heater | org/blk |
| A17 | Main Relay | grn/yel |
| A19 | Radiator Fan | yel/grn |
| A21 | Alternator | wht/yel |
| A23 | Purge Solenoid | red |
| A24 | Ignitor Unit | red/grn |
| A25 | Ground | blk |
| A26 | "Multiground" | blk/red |

#### B Plug (1992-1995 OBD1 Plug)

| Pin | Function | 92-95 Wire |
| :--- | :--- | :--- |
| B1 | Main Relay | yel/blk |
| B3 | A/C Switch | blu/red |
| B5 | Main Relay | blu/wht |
| B6 | Sensor | org |
| B7 | Sensor | org/blu |
| B8 | Sensor | blu/grn |
| B9 | Multiground | brn/blk |
| B13 | Vehicle Speed Sensor | yel/blu |
| B14 | Sensor | wht |
| B15 | Sensor | wht/blu |
| B16 | Sensor | blu/yel |

#### D Plug (1992-1995 OBD1 Plug)

| Pin | Function | 92-95 Wire |
| :--- | :--- | :--- |
| D1 | Hazard | wht/blu |
| D2 | Knock Sensor (B-Series) | red/blu |
| D5 | Alternator | pnk |
| D6 | TPS | red/blu |
| D7 | Coolant Temp | red/wht |
| D8 | Intake Temp | red/yel |
| D9 | MAP Sensor | wht |
| D10 | MAP Sensor | yel/grn |
| D11 | MAP Sensor | grn/blu |
| D12 | Brake Switch | grn/wht |
| D13 | Service Connector | brn |
| D14 | VTEC Pressure | org/blu |
| D16 | Elec. Load Sensor | grn/red |
| D18 | O2 Sensor | wht |
| D21 | TPS | yel/wht |
| D22 | Ground | grn/wht |

**Note:** For sensor pins (marked *), ensure correct matching by color from the distributor to the ECU.
