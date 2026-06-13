---
summary: 'Hardware modification guide to adding 1-wire VTEC control to OBD0 Honda ECUs by populating unused automatic transmission solenoid circuits.'
applies_to:
  brand: Honda
  obd: [0]
complexity: advanced
tags:
  - ecu
  - hardware
  - chipping
---

# Adding 1-Wire VTEC Control to OBD0 ECUs (PM6)

The factory manual transmission OBD0 PM6 ECU (from the 1988–1991 Civic/CRX Si) does not have VTEC control circuitry. However, because Honda used the same PCB layout for both manual and automatic transmission ECUs, the manual boards contain unpopulated slots intended for automatic transmission lockup solenoid controls.

By populating these unused circuits with specific resistors, transistors, and diodes, you can create a high-current output channel. Custom ROM codebases (such as TurboEdit) can then use this channel to trigger a VTEC solenoid. This is commonly referred to as a **1-Wire VTEC modification** because it drives the VTEC solenoid directly, while the VTEC pressure switch is bypassed in the software.

---

## 1. Required Components

Many of these parts are difficult to find in standard electronic component catalogs. However, they can be easily salvaged from a cheap, common OBD0 PM5 ECU (found in Civic DX/LX models):

| Location | Component Type | Value / Specification | Notes & Part Numbers |
| :---: | :--- | :--- | :--- |
| **Q42** | Power Transistor | 2SD1594 (NEC D1594) | SOT-89 or TO-220 package; salvage from automatic PM5/PM6. |
| **Q16** | NPN Transistor | 2SC945 (C945) | Standard NPN; can use NTE85. |
| **Q28** | Diode Array | NIL3Z | Salvage from PM5 ECUs. |
| **IC17** | Driver IC | 8055P | Low-side driver chip; salvage from automatic PM5/PM6. |
| **C77** | Ceramic Capacitor | `0.01 uF` | Standard disc filtering capacitor. |
| **R62** | Resistor | 10k $\Omega$, 1/8W | Pull-down resistor. |
| **R64** | Resistor | 51k $\Omega$, 1/8W | Gate resistor. |
| **R66** | Resistor | 10k $\Omega$, 1/8W | Gate resistor. |
| **R69** | Resistor | 110 $\Omega$, 1/4W | Current limiting resistor. |
| **R70** | Resistor | 1k $\Omega$, 1/8W | Current limiting resistor. |
| **D17** | Rectifier Diode | 1N4004 (or 1N1004) | Flyback protection diode. |
| **D26** | Zener Diode | ~68V | Transient voltage suppression diode. |
| **BR10** | Jumper | Jumper wire (0 $\Omega$) | Solder bridge connection. |
| **BR3** | Jumper | Jumper wire (0 $\Omega$) | Optional; depend on board revision. |

---

## 2. Step-by-Step Installation

1.  **Prep the Board:** 
    Open the ECU casing and locate the unpopulated footprints on the right side of the PCB matching the component IDs listed above. Use solder wick to clear the factory solder from the through-holes.
2.  **Solder Passives & Diodes:** 
    Install the resistors (`R62`, `R64`, `R66`, `R69`, `R70`), capacitor `C77`, and diodes `D17` and `D26`. Pay attention to the polarity bands on the diodes.
3.  **Install Transistors & Driver IC:** 
    Solder transistors `Q42`, `Q16`, `Q28`, and the `IC17` driver IC. Ensure their orientations match the silk-screened outlines on the PCB.
4.  **Install Jumper BR10:** 
    Solder a solid copper jumper wire across the pads at **`BR10`**.
    
    > **Note:** Depending on your specific board revision, you may also need to install a jumper at **`BR3`**. Compare your board layout to a factory PS9 or automatic PM6 board to verify if the trace path requires it.

---

## 3. Output Pin Routing

Once the hardware is installed, the new output channel is routed directly to the ECU connector pinout. Under standard PM6 wiring layouts:

*   The output activates pin **`A8`** (which is normally the automatic transmission lockup solenoid output on automatic harnesses). 
*   To wire VTEC, run a single wire from your VTEC solenoid in the engine bay through the firewall and pin it directly into position **`A8`** on the ECU harness plug.
