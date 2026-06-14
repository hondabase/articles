---
summary: 'Wiring conversion guide and pinout translation tables to run an automatic OBD2a Accord using an automatic OBD1 Integra ECU and separate TCU.'
applies_to:
  obd: [1, 2]
complexity: advanced
tags:
  - conversion
  - wiring
  - hardware
---

# Automatic Accord OBD2-to-OBD1 ECU and TCU conversion

Unlike Honda Civics of the same era, which integrate transmission lockup controls directly inside the ECU, automatic Honda Accords utilize a separate **Transmission Control Unit (TCU)** or transmission computer. 

When converting a USDM 5th-generation (1996–1997) automatic Accord from OBD2a to OBD1 for tuning (e.g., adding forced induction), standard manual-transmission OBD2-to-OBD1 jumper harnesses will not work because they do not route the essential TCU communication signals. 

This guide, based on hardware development documented by community researcher Bird333,
describes the parts, pin mapping, and harness construction used on that conversion.

> **Warning:** This is a community-developed conversion for a specific USDM parts
> combination. Verify every pin against the factory service manuals for the donor ECU,
> TCU, and vehicle before applying power. An incorrect connection can damage the ECU,
> TCU, harness, or vehicle.

## 1. Required components

To run an automatic OBD2a Accord (e.g., 1996 LX Sedan with an F22B2 engine) on an OBD1 ECU and TCU, you will need:

1. **Automatic OBD1 P75 ECU**: The archived guide specifies a 1994-1995 automatic
   Integra P75. It describes labels ending in **`-P75-A5x`** for US 49-state units or
   **`-P75-L5x`** for California units, with `5` identifying an automatic ECU.
2. **OBD1 Accord TCU**: An automatic transmission control unit from a 1994–1995 non-VTEC Accord (F22B2 engine).
3. **Modified ROM bin file**: A chipped EPROM burned with a compatible automatic Integra
   ROM. The archived guide used the USDM OBD1 `332` ROM and copied suitable fuel and
   ignition maps into it.
4. **Wiring Schematics**: Factory service manuals for the 1994–1995 Accord (to trace the TCU), 1994–1995 Integra (to trace the ECU), and 1996 Accord (to trace the OBD2a engine harness).

---

## 2. Jumper harness construction parts

If you choose to fabricate your own custom conversion harness rather than modifying an aftermarket harness, you will need:

* **20 AWG Wire**: Approximately 100–120 feet.
* **18 AWG Wire**: Approximately 10–20 feet (for high-current power and ground lines).
* **OBD1 ECU Plugs**: Tyco / AMP connectors:
  * Two 26-pin plugs (Tyco `#174516-6`)
  * Two 22-pin plugs (Tyco `#174515-6`)
  * One 16-pin plug (Tyco `#174514-6`)
* **OBD2a Female Plug Header**: One 104-pin male pin header (Tyco `#179686-6` or desoldered from a scrap OBD2a ECU).
* **Connector Terminals**:
  * 65x Small contact pins (Tyco `#175061-1` or gold-plated `-2`)
  * 26x Large contact pins (Tyco `#173631-1` or gold-plated `-2`)
* **Terminal Crimper**: Standard open-barrel crimp tool (e.g., Molex or Tyco `#WM9999-ND`).

---

## 3. OBD2a Accord to OBD1 ECU and TCU pinout translation

The table below maps the wiring routing from the vehicle's **1996–1997 OBD2a Accord engine harness plugs** to the new **OBD1 P75 ECU** and **OBD1 F22B2 TCU** pins:

| 1996-97 OBD2a Accord Plug/Pin | 1994 Accord TCU Pin | 1994 Accord ECU Pin (Ref) | OBD1 P75 ECU Pin | Signal Name / Function |
| :---: | :---: | :---: | :---: | :--- |
| **A01** | - | A02 | **A02** | Injector 4 Control |
| **A02** | - | A05 | **A05** | Injector 3 Control |
| **A03** | - | A03 | **A03** | Injector 2 Control |
| **A04** | - | A01 | **A01** | Injector 1 Control |
| **A05** | - | N/C | **N/C** | No Connection |
| **A06** | - | A11 | **A06** | Primary O2 Sensor Heater |
| **A08** | - | A04 | **A04** | VTEC Solenoid (VTS) *(Optional)* |
| **A09** | - | A26 | **A26** | Logic Ground 1 (LG1) |
| **A10** | - | A23 | **A23** | Power Ground 1 (PG1) |
| **A11** | A23 | - | - | TCU Ignition Power Input |
| **A11** | - | A25 | **A25** | Ignition Power 1 (IGP1) |
| **A12** | - | A09 | **A09** | IACV Control |
| **A13** | - | A10 | **N/C** | Engine Mount Control Solenoid (MCS) |
| **A15** | - | A20 | **A20** | EVAP Purge Control Solenoid |
| **A16** | - | A07 | **A07** | Fuel Pump Relay Control (FLR) |
| **A17** | A22 | A15 | **A15** | A/C Clutch Relay Control |
| **A18** | - | A13 | **A13** | Check Engine Light (MIL) |
| **A19** | - | A16 | **A16** | Alternator Control (ALT C) |
| **A20** | - | A21 | **A21** | Ignition Control Module (ICM) |
| **A20?** | A09 | - | - | TCU Engine Speed Input *(Splice to Tach test wire)* |
| **A22** | A25 | - | - | TCU Ground |
| **A22** | - | B02 | **B02** | Logic Ground 2 (LG2) |
| **A23** | A26 | - | - | TCU Ground |
| **A23** | - | A24 | **A24** | Power Ground 2 (PG2) |
| **A24** | A24 | - | - | TCU Ignition Power Input |
| **A24** | - | B01 | **B01** | Ignition Power 2 (IGP2) |
| **A27** | - | A12 | **A12** | Radiator Fan Control (FANC) |
| **A28** | - | N/C | **N/C** | No Connection |
| **A29** | - | N/C | **N/C** | No Connection |
| **B03** | A05 | - | - | Shift Control Solenoid A |
| **B04** | A04 | - | - | Lockup Control Solenoid B |
| **B05** | A06 | - | - | Lockup Control Solenoid A |
| **B08** | A15 | - | - | Automatic Transmission Position D3 |
| **B11** | A03 | - | - | Shift Control Solenoid B |
| **B12** | A18 | - | - | Shift Interlock |
| **B13** | A08 | - | - | Dash D4 Indicator Light |
| **B14** | D12 | - | - | Mainshaft Speed Sensor Ground |
| **B15** | D19 | - | - | Mainshaft Speed Sensor Signal |
| **B16** | A21 | - | - | Automatic Transmission Position Reverse |
| **B17** | A13 | - | - | Automatic Transmission Position 2 |
| **B18** | A11 | - | - | Automatic Transmission Position 1 |
| **B22** | D15 | - | - | Countershaft Speed Sensor Ground |
| **B23** | D17 | - | - | Countershaft Speed Sensor Signal |
| **B24** | A17 | - | - | Automatic Transmission Position D4 |
| **B25** | A19 | B07 | **B07** | Automatic Transmission Position Park/Neutral |
| **C02** | - | B15 | **B15** | Crankshaft Position Sensor (CKP P) |
| **C03** | - | B13 | **B13** | Top Dead Center Sensor (TDC P) |
| **C04** | - | B11 | **B11** | Cylinder Position Sensor (CYP P) |
| **C05** | - | B05 | **B05** | A/C Thermostat Switch |
| **C06** | - | B09 | **B09** | Starter Switch Signal (STS) |
| **C07** | D06 | D04 | **D04** | Service Check Jumper Signal (SCS) |
| **C08** | - | D07 | **D07** | K-Line Diagnostics |
| **C10** | A20 | - | - | TCU Back-up Battery Input |
| **C10** | - | D01 | **D01** | Backup Power (VBU) |
| **C12** | - | B16 | **B16** | Crankshaft Position Sensor Ground (CKP M) |
| **C13** | - | B14 | **B14** | Top Dead Center Sensor Ground (TDC M) |
| **C14** | - | B12 | **B12** | Cylinder Position Sensor Ground (CYP M) |
| **C15** | - | D06 | **D06** | VTEC Pressure Switch (VTP) *(Optional)* |
| **C16** | - | B08 | **B08** | Power Steering Pressure Switch (PSP) |
| **C17** | - | D09 | **D09** | Alternator FR Signal (ALT FR) |
| **C18** | D09 | B10 | **B10** | Vehicle Speed Sensor (VSS) |
| **C20** | - | N/C | **N/C** | No Connection |
| **D01** | D07 | D11 | **D11** | Throttle Position Sensor (TPS) |
| **D02** | D05 | D13 | **D13** | Engine Coolant Temp Sensor (ECT) |
| **D03** | - | D17 | **D17** | Manifold Absolute Pressure (MAP) |
| **D04** | - | D19 | **D19** | Sensor 5V Reference Voltage (VCC1) |
| **D05** | D02 | - | - | Brake Switch Input (TCU) |
| **D05** | - | D02 | **D02** | Brake Switch Input (ECU) |
| **D06** | - | - | **NOT CONN** | Knock Sensor *(Not used on P75)* |
| **D07** | - | D14 | **D14** | Primary Oxygen Sensor (O2) |
| **D08** | - | D15 | **D15** | Intake Air Temp Sensor (IAT) |
| **D09** | - | D12 | **NOT CONN** | EGR Lift Sensor |
| **D10** | - | D20 | **D20** | Sensor 5V Reference Voltage (VCC2) |
| **D11** | - | D22 | **D22** | Sensor Ground 2 (SG2) |
| **D12** | - | D21 | **D21** | Sensor Ground 1 (SG1) |
| **D13** | - | N/C | **N/C** | Secondary O2 Ground *(OBD2 only, delete)* |
| **D14** | - | N/C | **N/C** | Secondary O2 Signal *(OBD2 only, delete)* |
| **D15** | - | N/C | **N/C** | Fuel Tank Pressure Sensor *(OBD2 only, delete)* |
| **D16** | - | D10 | **D10** | Electric Load Detector (ELD) |
| - | A10 | - | **NOT REQ** | TCU Pin (Omit) |
| - | D03 | D05 | **D08** | Barometric Output (BARO OUT) |
| - | D11 | B04 | **B04** | Air Flow Sensor B |
| - | D13 | B03 | **B03** | Air Flow Sensor A |
| - | D16 | A18 | **A19** | Engine Speed Output to TCU |
| - | D18 | D18 | **D16** | Sensor Voltage Reference |

> **Note:** Question marks and uncertain mappings from the archived conversion table are
> preserved. In particular, it says not to connect TCU A09 to OBD2 A20 and instead uses
> the tachometer test wire. Verify every mapping against the applicable service manuals.

---

## 4. Pin-counting references

> **Warning:** Counting pins is different between OBD1 and OBD2 plugs. Miscounting pins
> is the most common cause of conversion-harness errors.

### OBD1 plugs, ECU side
Looking directly at the **wire side** of the plug (where wires enter the back of the plastic connector) with the locking clip facing **Up**:
* **Pin 1** is the top-left pin.
* **Pin 2** is directly below Pin 1 (bottom-left).
* Pins alternate columns as you count across to the right (Odd on top, Even on bottom).

```
[ Clip at Top ]
|  1  |  3  |  5  |  7  |  9  | ...
|  2  |  4  |  6  |  8  |  10 | ...
```

### OBD2 plugs, engine-harness side
Looking directly at the **face side** of the plug (mating face, opposite the wires) with the locking clip guide facing **Up**:
* Pins are counted sequentially across the top row from left to right, then across the bottom row.

```
[ Clip at Top ]
|  1  |  2  |  3  |  4  |  5  |  6  | ...
|  7  |  8  |  9  |  10 |  11 |  12 | ...
```

---

## 5. Wiring harness length guidelines

To mount the OBD1 ECU and the Accord TCU in their factory locations under the passenger kick panel, cut your jumper wires to the following lengths before crimping terminal pins:
* **ECU Interface Wires**: 47 pieces cut to **4.5 inches** (runs from the OBD2a connector to the OBD1 ECU plugs).
* **TCU Interface Wires**: 27 pieces cut to **21.0 inches** (runs from the OBD2a harness to the OBD1 TCU plugs).
* **ECU-to-TCU Jumpers**: 5 pieces cut to **19.0 inches** (connects signals directly between the ECU and TCU plugs, requiring terminals on both ends).

---

## 6. Harness assembly notes

The archived guide gives these construction details:

1. Bend or cut the right-angle OBD2a connector leads straight before soldering.
2. Cut the wires and crimp their terminals before assembling the plugs.
3. Crimp the outer terminal tabs around the insulation and the inner tabs around bare
   wire. Do not extend bare wire into the terminal socket.
4. Use the larger terminals for OBD1 A-plug pins 1-6 and 23-26, and D-plug pins 1-2 and
   19-22. The B-plug uses small terminals.
5. Keep soldering time on `each` OBD2 connector lead short to avoid softening its plastic.
6. Insulate the soldered OBD2 leads with heat-shrink tubing.
7. Insert OBD1 terminals with the crimp side facing the plug's locking clip.
8. Check every completed connection for continuity before connecting the harness.

> **Warning:** The archived guide says OBD1 terminals are difficult to remove after they
> lock into a plug. Confirm `each` destination before inserting it.

## Conversion files
* [Automatic Accord OBD2-to-OBD1 Wiring Spreadsheet & Baseline Bin (ZIP)](AutoOBDconvertinfoandIntegrabin.zip)
