---
summary: 'A complete reference list of Honda OBD0, OBD1, and OBD2 diagnostic trouble codes (DTCs), including CEL flash counts and descriptions.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - diagnostics
  - obd
  - reference
---

# Honda Diagnostic Trouble Codes (DTC) Reference Guide

When a sensor or system on a Honda engine malfunctions, the Engine Control Unit (ECU) illuminates the dashboard Check Engine Light (CEL / MIL) and stores a diagnostic trouble code (DTC) in its memory. 

This reference guide details how to retrieve these codes and lists the meanings and common causes for Honda trouble codes 1 through 92.

---

## How to Retrieve Diagnostic Codes

Before reading the codes, you must identify your vehicle's OBD generation:

### OBD0 Systems (1988–1991)
OBD0 ECUs display codes via a red LED mounted directly on the ECU circuit board:
1. Turn the ignition key to the ON position.
2. Locate the ECU under the passenger footwell carpet or seat.
3. Look through the circular viewing window in the ECU's metal case.
4. Count the flashes of the red LED. A code 9 is represented by 9 quick flashes.

### OBD1 Systems (1992–1995)
OBD1 systems flash the dashboard Check Engine Light (CEL):
1. Locate the 2-pin Service Connector Switch (SCS) connector (usually wrapped in blue tape behind the passenger-side kick panel).
2. Jump the two pins together using a paperclip or jumper wire.
3. Turn the ignition key to the ON position.
4. Watch the Check Engine Light and count the flashes:
   - **Long flashes (1.0 second):** represent the tens digit (e.g., three long flashes = 30).
   - **Short flashes (0.5 second):** represent the units digit (e.g., four short flashes = 4).
   - A code 34 is flashed as three long blinks followed by four short blinks.

---

## Honda OBD0 & OBD1 Diagnostic Trouble Codes

Below is the master list of factory diagnostic trouble codes:

| Code (Blinks) | Malfunctioning Sensor / System | Common Causes and Symptoms |
| :---: | :--- | :--- |
| **1** | Primary Oxygen Sensor (Primary $O_2$) | Damaged wiring, defective sensor, or incorrect heater circuit operation. |
| **2** | Secondary Oxygen Sensor (Secondary $O_2$) | Sourced in dual-carbureted or specific JDM/European dual-sensor models. |
| **3** | Manifold Absolute Pressure (MAP Sensor) | Open or shorted electrical circuit on the MAP sensor wiring plugs. |
| **4** | Crankshaft Position Sensor (CKP Sensor) | Internal distributor sensor failure or wiring fault. Prevents engine starting. |
| **5** | Manifold Absolute Pressure (MAP Sensor) | Mechanical vacuum range fault. Check for a split or disconnected MAP vacuum hose. |
| **6** | Engine Coolant Temperature (ECT Sensor) | Open or short in the ECT circuit. Causes poor cold starting and rough idle. |
| **7** | Throttle Position Sensor (TPS) | Defective TPS sensor, incorrect base calibration (must read 0.5V at closed throttle). |
| **8** | Top Dead Center Sensor (TDC Sensor) | Internal distributor sensor fault. Causes erratic spark timing or starting issues. |
| **9** | Cylinder Position Sensor (CYP Sensor) | Internal distributor sensor fault. Causes sequential injection failure or misfires. |
| **10** | Intake Air Temperature (IAT Sensor) | Sensor circuit open or shorted. Restricts temperature-based fueling trim corrections. |
| **12** | Exhaust Gas Recirculation (EGR Lift) | Clogged EGR passages or a defective EGR valve position sensor. |
| **13** | Barometric Pressure (BARO Sensor) | Malfunctioning barometric pressure sensor inside the ECU casing. Requires ECU repair. |
| **14** | Idle Air Control Valve (IACV / EACV) | Defective IACV solenoid circuit, vacuum leaks, or carbon build-up in the valve. |
| **15** | Ignition Output Signal | Missing spark trigger from the Igniter/Ignition Control Module (ICM) in the distributor. |
| **16** | Fuel Injector System | Faulty injector wiring, loose connectors, or failed resistor box (OBD0 models). |
| **17** | Vehicle Speed Sensor (VSS) | Failed speed sensor or broken speedo cable. **Note:** Prevents VTEC engagement. |
| **19** | A/T Lock-Up Control Solenoid | Automatic transmission lock-up solenoid electrical circuit fault. |
| **20** | Electrical Load Detector (ELD) | Defective ELD unit in the under-hood fuse box or high electrical resistance. |
| **21** | VTEC Solenoid Valve | Open or shorted VTEC solenoid wiring. Prevent VTEC engagement. |
| **22** | VTEC Oil Pressure Switch | Low engine oil level, low oil pressure, or a defective pressure switch on the VTEC assembly. |
| **23** | Knock Sensor (KS) | Defective knock sensor, cracked sensor body, or severed shield wire. |
| **30** | A/T FI Signal A | Automatic transmission to ECU communication circuit fault. |
| **31** | A/T FI Signal B | Automatic transmission to ECU communication circuit fault. |
| **41** | Primary $O_2$ Sensor Heater | Damaged heater element inside the 4-wire $O_2$ sensor. Requires sensor replacement. |
| **43** | Fuel Supply System | Closed-loop fueling limit exceeded. Engine is running extremely rich or lean. |
| **45** | System Too Rich / Too Lean | Fuel adaptation range limit reached (early transitional OBD2 code). |
| **48** | Lean Air-Fuel Sensor (LAF Sensor) | Failed 5-wire lean-burn oxygen sensor (typical on Civic VX D15Z1 models). |
| **54** | Crankshaft Speed Fluctuation (CKF) | Failed misfire detection sensor on the engine block/oil pump housing (OBD2 models). |
| **58** | TDC Sensor 2 | Top Dead Center sensor circuit malfunction (equipped on V-6 models). |
| **80** | EGR Flow Insufficient | Carbon-plugged EGR runner ports in the intake manifold. Requires port cleaning. |
| **90** | EVAP System Leak | EVAP system leak, faulty purge valve, or loose fuel cap (OBD2 models). |
| **91** | Fuel Tank Pressure Sensor | Low electrical input signal from the fuel tank pressure sensor. |
| **92** | EVAP Purge Flow Insufficient | Insufficient vacuum flow through the EVAP canister purge system. |

---

## Troubleshooting Guide for Common Codes

### VTEC Solenoid & Pressure Switch (Codes 21 & 22)
VTEC engagement requires meeting multiple parameters. If the ECU throws a Code 21 or 22:
1. **Check your engine oil level:** Low oil level or low oil pressure will trigger Code 22 when the ECU commands VTEC crossover.
2. **Check the VSS (Code 17):** If your speedometer is broken or the VSS is disconnected, the ECU will not engage VTEC and may throw a code.
3. **Verify the wiring:** The VTEC solenoid requires a 12V trigger from the ECU (pin A4 on OBD1). The VTEC pressure switch should connect to the ECU (pin D6) and ground.

### Oxygen Sensor Heater (Code 41)
If Code 41 is thrown:
- The internal heating element in the 4-wire $O_2$ sensor has failed (usually reads infinite resistance between the two black wires on the sensor side).
- Replace the sensor. Do not attempt to bypass this heater check, as it ensures the sensor reaches operating temperature quickly.

### Distributor Sensors (Codes 4, 8, & 9)
The distributor housing contains the CKP, TDC, and CYP sensors. 
- If any of these codes occur, check the plug connection on the distributor for corrosion.
- If the wiring is intact, the internal sensor coils inside the distributor housing are likely failing due to age or heat. The distributor housing assembly must be replaced. Refer to the [cylinder position sensor guide](/cars/electronics/cylinder-position-sensor) for diagnostics.
