---
summary: 'Technical reference on Honda PGM-FI internal and external ignition coils, including testing procedures, specifications, and conversion instructions.'
tags: [ignition, hardware, diagnostics, distributor]
applies_to:
  models: [accord, civic, integra, prelude]
  chassis: {}
complexity: intermediate
---

# Honda PGM-FI Ignition Coil Technical Reference

The ignition coil is an electrical transformer that steps up the low battery voltage (12V) to the high voltage (20,000V to 40,000V+) required to jump the spark plug gap and initiate combustion in Honda PGM-FI engines.

## Overview

In most Honda vehicles from the OBD0, OBD1, and OBD2a/2b eras, the ignition coil is housed directly inside the distributor cap (**internal coil**). This arrangement integrates the coil, the Ignition Control Module (ICM), and the distributor rotor/cap into a single unit.

While convenient for packaging, internal coils are susceptible to heat soak within the sealed distributor housing. Under high engine load, high RPM, or forced induction, this heat can break down the coil insulation, leading to internal shorts and ignition failure.

Certain models, such as the OBD1 Accord, Prelude, and specific Civic trims, utilized an **external coil** mounted on the firewall or engine block, which offers improved thermal management and reliability.

## Specifications

When diagnosing misfires or "no start" conditions, measuring the electrical resistance of the primary and secondary windings is the primary diagnostic step. Values below are OEM specifications for common Honda/TEC ignition coils (measured at 68°F / 20°C).

### Internal Coil Specs (e.g., TEC TC-08A / TC-05A)

| Winding | Resistance Range | Measurement Points |
| :--- | :--- | :--- |
| **Primary** | 0.63 – 0.77 Ω | Positive (+) and Negative (-) terminal screws |
| **Secondary** | 12.8 – 19.2 kΩ | Positive (+) terminal and high-tension output tower |

### External Coil Specs (e.g., TEC TC-07A)

| Winding | Resistance Range | Measurement Points |
| :--- | :--- | :--- |
| **Primary** | 0.4 – 0.6 Ω | Positive (+) and Negative (-) terminal screws |
| **Secondary** | 12.0 – 18.0 kΩ | Positive (+) terminal and high-tension output tower |

## Testing Procedure

Use a digital multimeter (DVOM) to verify coil integrity.

> [!WARNING]
> Ensure the ignition switch is OFF and the negative battery terminal is disconnected before beginning.

1. **Access the Coil:** Remove the distributor cap and dust shield to expose the ignition coil.
2. **Identify Terminals:** Locate the positive (+) terminal (typically Black/Yellow wire) and the negative (-) terminal (typically Blue wire). Disconnect these wires to prevent back-feeding.
3. **Test Primary Winding:**
   - Set the multimeter to the lowest resistance range (e.g., 200 Ω).
   - Measure between the (+) and (-) terminals.
   - Subtract the resistance of the test leads from the final reading.
   - **Result:** Values outside the 0.6 – 0.8 Ω range, or an `OL` (open circuit) reading, indicate a defective coil.
4. **Test Secondary Winding:**
   - Set the multimeter to the kilohms range (e.g., 20k Ω).
   - Measure between the (+) terminal and the high-voltage output tower.
   - **Result:** Values outside the 12.8k – 19.2k Ω range, or an `OL` reading, indicate a broken internal winding.

## Internal to External Coil Conversion

Converting to an external coil (e.g., MSD Blaster SS or OEM external) increases spark energy and isolates the coil from distributor heat. This is recommended for high-RPM or turbocharged applications.

### Requirements
* External ignition coil.
* External coil-compatible distributor cap.
* High-tension spark plug wire (coil-to-cap).
* Wiring connectors, heat shrink, and soldering equipment.

### Wiring Connections

| Original Wire | Function | External Coil Connection |
| :--- | :--- | :--- |
| **Black/Yellow** | +12V Switched Power | Positive (+) Terminal |
| **Blue** | ICM Trigger Signal | Negative (-) Terminal |

### Procedure
1. **Remove Internal Components:** Remove the distributor cap, rotor, dust shield, and factory internal coil.
2. **Modify Housing:** Drill a small hole in the underside of the distributor housing and install a rubber grommet to prevent wire chafing.
3. **Route Wires:** Solder extensions to the Black/Yellow and Blue wires. Route them through the new grommet.
4. **Install External Cap:** Install the external-style distributor cap and rotor.
5. **Mount Coil:** Secure the external coil to the firewall or engine block, away from direct exhaust heat.
6. **Final Connections:** Connect the Black/Yellow wire to the (+) terminal and the Blue wire to the (-) terminal of the external coil. Connect the high-tension lead from the coil to the center tower of the distributor cap.
7. **Verification:** Start the engine and verify timing alignment with a timing light.

{{> ignition-troubleshooting-tips }}
