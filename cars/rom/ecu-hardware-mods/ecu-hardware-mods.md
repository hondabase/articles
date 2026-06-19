---
summary: 'A comprehensive index of hardware modifications for Honda OBD0 and OBD1 ECUs, including VTEC conversions, IAB additions, wideband inputs, and transmission swaps.'
tags: [ecu, hardware, chipping, vtec, obd0, obd1]
applies_to:
  models: [civic, crx, del-sol, integra, prelude]
  chassis: [bb, da, dc2, ef, eg, eg-eh, ek]
complexity: advanced
---

# Guide to Honda ECU Hardware Modifications

Stock Honda engine control units (ECUs) are highly modular. Honda often used the same printed circuit board (PCB) layouts for multiple ECU models, leaving certain component paths unpopulated on lower-tier models. This modularity allows for the physical installation of components to add features like VTEC control, secondary intake runners (IAB), and custom datalogging inputs.

## 1. Transmission & Chassis Modifications

### Automatic to Manual Conversion (OBD0 & OBD1)
Convert an automatic transmission ECU to run on a manual vehicle without triggering a Code 19 (lockup control solenoid) CEL. 

> [!IMPORTANT]
> This modification typically involves desoldering configuration jumpers and replacing them with 0-ohm resistors or jumper wires to signal the ECU software that a manual transmission is present.

## 2. OBD1 ECU Modifications (P28, P30, P72, P75, P05, P06)

### VTEC Conversion (Non-VTEC to VTEC)
Convert non-VTEC ECUs (such as the P06 Civic DX or P75 Integra LS) into VTEC-capable units. This requires soldering a high-side driver transistor, a latching transistor, resistors, diodes, and filtering capacitors to the board's unpopulated VTEC control section.

### Secondary Runner Control (IAB Addition)
Add Intake Air Bypass (IAB) controls to a P28 ECU to support the dual-stage intake runner solenoid found on B18C1 (Integra GS-R) and H22A (Prelude VTEC) intake manifolds.
* **The Mod:** Solder the IAB driver IC (typically at `IC15`) and supporting resistors.

### Knock Board Installation
Modify a P75 or P28 ECU to accept a knock sensor by installing the OEM knock processing sub-board and soldering the input trace pins.

### Knock Board Removal
Remove or bypass the knock processing sub-board on ECUs like the P13 (Prelude) or JDM P30/P72 to prevent VTEC disablement or active Code 23 errors when running engines that lack a knock sensor or feature noisy valvetrains.

### 4-Wire Oxygen Sensor Conversion
Convert single-wire O2 sensor circuits (found on JDM P08 and base-model USDM P05 ECUs) to standard heated 4-wire O2 sensor circuits to improve closed-loop stability.

### Wideband 0–5V Input Modification
Modify the factory oxygen sensor input resistor network to accept a linear 0–5V analog signal directly from an external wideband controller.

### External Sensor Logging (EGT / Fuel Pressure)
Repurpose unused analog input pins on the ECU plug (such as the EGR Valve Lift Sensor pin or the EVAP Control pin) to datalog external 5V sensors like Exhaust Gas Temperature (EGT) probes or fuel pressure sending units.

## 3. OBD0 ECU Modifications (PM6, PM7, PR4, PG7)

### VTEC Conversion (1-Wire VTEC)
Add 1-wire VTEC engagement control hardware to OBD0 ECUs (such as the PM6) to run VTEC engines like the D16Z6 or B16A on OBD0 wiring harnesses.

### Electrical Load Detector (ELD) Bypass
Disable the ELD feedback loop on USDM PM6 ECUs. This bypass prevents the ECU from throwing a Code 20 CEL when installed in chassis that lack an ELD unit in the engine bay fuse box.

### Barometric Pressure (PA) Sensor Conversion
Reconfigure 1990–1991 Integra PR4 ECUs to use either an internal or external Barometric/PA sensor by adjusting the jumper trace resistors.

## 4. Hardware Sourcing
To find specific part numbers, package sizes, and electronic specifications for the resistors, transistors, and diodes required to execute these modifications, refer to the [ECU Parts Sourcing List](/cars/ecu/parts-for-ec-us).
