---
summary: 'Hardware modification guide to adding 1-wire VTEC control to OBD0 Honda ECUs by populating unused automatic transmission solenoid circuits.'
tags: [ecu, hardware, chipping, vtec]
applies_to:
  make: Honda
  models: [civic, crx]
  chassis: [ef, eg]
complexity: advanced
---

# Adding 1-Wire VTEC Control to OBD0 ECUs (PM6)

The factory manual transmission OBD0 PM6 ECU (from the 1988–1991 Civic/CRX Si) does not have VTEC control circuitry. Because Honda utilized a shared PCB layout for both manual and automatic transmission ECUs, the manual boards contain unpopulated slots intended for automatic transmission lockup solenoid controls.

By populating these unused circuits with specific resistors, transistors, and diodes, you can create a high-current output channel. Custom ROM codebases can then use this channel to trigger a VTEC solenoid. This is referred to as a **1-Wire VTEC modification** because it drives the VTEC solenoid directly, while the VTEC pressure switch is bypassed in the software.

## 1. Required Components

Many of these parts can be salvaged from a common OBD0 PM5 ECU (found in Civic DX/LX models).

| Location | Component Type | Value / Specification | Notes |
| :--- | :--- | :--- | :--- |
| **Q42** | Power Transistor | 2SD1594 (NEC D1594) | SOT-89 or TO-220 package |
| **Q16** | NPN Transistor | 2SC945 (C945) | Can use NTE85 |
| **Q28** | Diode Array | NIL3Z | Salvage from PM5 |
| **IC17** | Driver IC | 8055P | Low-side driver |
| **C77** | Ceramic Capacitor | 0.01 uF | Disc filtering capacitor |
| **R62** | Resistor | 10k Ω, 1/8W | Pull-down resistor |
| **R64** | Resistor | 51k Ω, 1/8W | Gate resistor |
| **R66** | Resistor | 10k Ω, 1/8W | Gate resistor |
| **R69** | Resistor | 110 Ω, 1/4W | Current limiting |
| **R70** | Resistor | 1k Ω, 1/8W | Current limiting |
| **D17** | Rectifier Diode | 1N4004 | Flyback protection |
| **D26** | Zener Diode | ~68V | Transient voltage suppression |
| **BR10** | Jumper | 0 Ω | Solder bridge |
| **BR3** | Jumper | 0 Ω | Optional; board revision dependent |

## 2. Installation Procedure

1. **Prepare the Board:** Open the ECU casing and locate the unpopulated footprints on the right side of the PCB. Use solder wick to clear factory solder from the through-holes.
2. **Install Passives & Diodes:** Install resistors (`R62`, `R64`, `R66`, `R69`, `R70`), capacitor `C77`, and diodes `D17` and `D26`. 
   > [!IMPORTANT]
   > Verify the polarity bands on all diodes before soldering.
3. **Install Transistors & Driver IC:** Solder transistors `Q42`, `Q16`, `Q28`, and the `IC17` driver IC. Ensure orientations match the silk-screened outlines on the PCB.
4. **Install Jumpers:** Solder a solid copper jumper wire across the pads at **BR10**.

> [!NOTE]
> Depending on your specific board revision, you may also need to install a jumper at **BR3**. Compare your board layout to a factory PS9 or automatic PM6 board to verify if the trace path requires it.

## 3. Output Pin Routing

Once the hardware is installed, the new output channel is routed to the ECU connector.

* The output activates pin **A8** (the automatic transmission lockup solenoid output).
* To wire VTEC, run a single wire from the VTEC solenoid in the engine bay through the firewall and pin it directly into position **A8** on the ECU harness plug.

{{> resistor-color-codes }}
