---
summary: 'Technical guide to high-impedance (saturated) fuel injectors on Honda PGM-FI engines, explaining their electrical properties, driver types, and compatibility.'
tags: [injectors, fueling, hardware]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, ef, eg, eg-eh, ek]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'High Impedance Injectors'
    url: /pgmfi/wiki/library/high-impedance-injectors
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# High Impedance Injectors

High-impedance injectors, also known as **saturated injectors**, have a relatively high internal coil resistance, typically ranging from **12 to 16 ohms**.

## Overview

In fuel injection systems, the ECU controls fuel delivery by grounding the injector circuit to open the injector's internal solenoid valve. High-impedance injectors are named after the way the ECU's driver circuit operates: the driver applies a constant 12V signal to the injector coil, and the current "saturates" the coil, holding the valve open for the duration of the pulse width.

Because of their high resistance, the electrical current flowing through the injector is low (around 1 amp). This low current generates minimal heat in the ECU's internal injector drivers, allowing the ECU to control the injectors directly without any inline resistors or specialized driver circuits.

---

## Evolution on Honda Engines

Honda's use of injectors evolved across different OBD generations:

* **OBD0 MPFI (1988–1991 D/B-series):** Utilized **low-impedance** injectors (2–3 ohms) from the factory, which required an inline resistor box to limit current and prevent burning out the ECU drivers.

* **OBD1 (1992–1995 D/B/H-series):** Civic and Integra models transitioned to **high-impedance** (saturated) injectors, plugging directly into the wiring harness without a resistor box. (The Prelude H22/H23 remained low-impedance with a factory resistor box).

* **OBD2 (1996–2001 D/B/H/F-series):** All Honda models transitioned to high-impedance saturated injectors.

* **K-Series (2001+):** Employs modern high-impedance injectors with updated plug connectors.

---

## Specifications

High-impedance injectors are highly reliable and widely used in factory and aftermarket setups. Below are the specifications of common Honda factory high-impedance injectors:

| Engine / Vehicle | OBD Generation | Flow Rate (cc/min) | Nominal Resistance |
| :--- | :---: | :---: | :---: |
| **D16Z6 (Civic EX/Si)** | OBD1 | `240cc` | ~12.5 ohms |
| **B18C1 (Integra GS-R)** | OBD1 / OBD2 | `240cc` | ~12.5 ohms |
| **H22A4 (Prelude VTEC)** | OBD2 | `290cc` | ~13.0 ohms |
| **K20A2 (RSX Type-S)** | K-Series | `310cc` | ~12.0 ohms |
| **S2000 (F20C/F22C)** | OBD2 | `360cc` | ~12.5 ohms |

---

## Wiring Reference

High-impedance injectors are wired in a simple, direct layout. Each injector receives a switched +12V power source, and its ground return line connects directly to a dedicated pin on the ECU.

```
 +12V Switched Power (from Main Relay)
 |
 +--------+--------+
 | |
 [Injector 1] [Injector 2]...
 | |
 | |
 ECU Pin INJ1 ECU Pin INJ2... (ECU grounds to trigger)
```

There are no inline resistor packs or external driver boxes in a saturated injector circuit.

---

## Advantages and Modern Build Guidelines

### Advantages:

* **Simpler Wiring:** No resistor box is needed, reducing failure points and cleaning up the engine bay.

* **Less Heat:** Generates less heat in both the injector casing and the ECU drivers.

* **Modern Technology:** The highest quality aftermarket injectors available today (such as Injector Dynamics ID1050x or Fuel Clinic injectors) are high-impedance. Modern manufacturing allows these high-impedance injectors to flow massive amounts of fuel (1000cc/min+) while retaining excellent idle control and response times.

### Conversion Tip:

If you are converting an OBD0 chassis (which has a factory resistor box) to run an OBD1 ECU with high-impedance injectors, you must **remove the resistor box** and splice the power supply wires together (referred to as a "resistor box delete"). Failing to bypass the resistor box will result in weak injector activation and severe lean conditions because the resistance will be too high.

---

## Related

- [Low impedance injectors](/cars/fueling/low-impedance-injectors)
- [Injector sizing](/cars/fueling/injector-sizing)
- [Introduction to ECU chipping](/cars/rom/introduction-to-ecu-chipping)
