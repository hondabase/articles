---
summary: 'Technical reference on the Honda PGM-FI internal and external ignition coils, including testing procedures, specs, and converting from internal to external coil setups.'
tags: [ignition, hardware, diagnostics]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, integra, prelude]
  chassis: {}
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Ignition Coil'
    url: /pgmfi/wiki/library/ignition-coil
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Ignition Coil

The ignition coil is an electrical transformer that steps up the low battery voltage (12V) to the high voltage (20,000V to 40,000V+) required to jump the spark plug gap and initiate combustion in Honda PGM-FI engines.

## Overview

In most Honda vehicles from the OBD0, OBD1, and OBD2a/2b eras, the ignition coil is housed directly inside the distributor cap (referred to as an **internal coil**). This compact arrangement integrates the coil, the Ignition Control Module (ICM or igniter), and the distributor rotor/cap into a single unit. 

While convenient for packaging, internal coils run hot due to heat dissipation limits within the sealed distributor housing. Under high engine load, high RPM, or high boost, this heat can break down the coil windings' insulation, leading to internal shorts and ignition failure.

Certain models (like the OBD1 Accord, Prelude, and some Civic models) utilized an **external coil** mounted on the firewall or engine block, which runs cooler and is more reliable.

---

## Specifications

When diagnosing misfires or a "no start" condition, checking the electrical resistance of the primary and secondary windings is the primary diagnostic step. Below are the OEM specifications for the most common Honda/TEC ignition coils (measured at 68°F / 20°C).

### Internal Coil Specs (e.g., TEC TC-08A / TC-05A)
*   **Primary Winding Resistance:** `0.63 – 0.77 ohms` (measured between the positive (+) and negative (-) terminal screws).
*   **Secondary Winding Resistance:** `12.8 – 19.2 k-ohms` (measured between the positive (+) screw terminal and the high-tension output tower).

### External Coil Specs (e.g., TEC TC-07A)
*   **Primary Winding Resistance:** `0.4 – 0.6 ohms`.
*   **Secondary Winding Resistance:** `12.0 – 18.0 k-ohms`.

---

## Testing Procedure

To verify if your ignition coil has failed, use a digital multimeter (DVOM) to measure the resistance of the internal windings.

### Steps to Test:
1.  **Safety First:** Ensure the ignition switch is turned OFF. Disconnect the negative battery terminal.
2.  **Access the Coil:** Remove the distributor cap and leak cover (dust shield) to expose the ignition coil.
3.  **Identify Terminals:** Note the location of the positive (+) terminal screw (usually has a black/yellow wire) and the negative (-) terminal screw (usually has a blue wire). Disconnect the wires from the terminals to prevent back-feeding.
4.  **Test Primary Winding:**
    *   Set your multimeter to the lowest resistance range (e.g., 200 ohms).
    *   Touch one probe to the positive (+) terminal and the other to the negative (-) terminal.
    *   Subtract the resistance of your meter leads (touching the leads together) from the reading.
    *   The result should be within **0.6 – 0.8 ohms** for an internal coil. If it reads `0` (short circuit) or `OL` (open circuit), the coil is defective.
5.  **Test Secondary Winding:**
    *   Set your multimeter to the kilohms range (e.g., 20k or 200k ohms).
    *   Touch one probe to the positive (+) terminal and the other probe to the high-voltage output tower (where the spring contact meets the distributor cap).
    *   The result should be between **12.8k – 19.2k ohms**. An open loop (`OL`) indicates a broken winding inside the coil casing.

---

## Internal to External Coil Conversion

Converting your distributor from an internal coil to an external coil (such as an MSD Blaster SS or an OEM external coil) increases spark energy and isolates the coil from distributor heat. This modification is highly recommended for turbocharged or high-RPM builds.

### Requirements:
*   An external ignition coil (e.g., MSD-8207 or Honda TC-07A).
*   An external coil distributor cap (features an external wire socket instead of a solid cap contact).
*   Heavy-gauge spark plug wire (to link the cap to the external coil).
*   Wiring connectors, heat shrink, and solder.

### Wiring Diagram and Connections:

Inside the distributor, you must route the wires that originally went to the internal coil out to the new external coil.

| Original Wire inside Distributor | Function | Connection to External Coil |
| :--- | :--- | :--- |
| **Black/Yellow** | +12V Switched Power | Positive (+) Terminal of External Coil |
| **Blue** | Ignition Control Signal (from ICM/Igniter) | Negative (-) Terminal of External Coil |

### Procedure:
1.  **Remove Internal Coil:** Remove the distributor cap, rotor, and internal dust shield. Unscrew and remove the factory internal coil.
2.  **Modify Housing:** Drill a small hole in the underside of the distributor housing. Insert a rubber grommet to protect the wires from chaffing.
3.  **Run Output Wires:** Solder extensions to the internal Black/Yellow wire (+12V power supply) and the Blue wire (ICM trigger signal). Run these wires out through the grommet.
4.  **Install External Cap:** Install the modified external-style distributor cap and rotor.
5.  **Mount the External Coil:** Secure the new coil to the firewall or engine block away from direct header heat.
6.  **Connect Wires:** Plug the Black/Yellow wire into the positive (+) terminal of the external coil, and the Blue wire into the negative (-) terminal.
7.  **Connect Secondary Output:** Connect a custom-length spark plug wire from the high-voltage tower of the external coil to the center tower of the new distributor cap.
8.  **Test Run:** Start the engine and verify smooth idle. Check timing alignment with a timing light if the distributor housing was rotated.

---

## Related

- [Crankshaft position sensor](/cars/ignition/crankshaft-position-sensor)
- [Cylinder position sensor](/cars/sensors/cylinder-position-sensor)
- [Introduction to ECU chipping](/cars/rom/introduction-to-ecu-chipping)
