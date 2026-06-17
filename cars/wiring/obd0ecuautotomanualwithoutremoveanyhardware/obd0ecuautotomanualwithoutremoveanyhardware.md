---
summary: 'Hardware modification guide for bypassing the automatic transmission lockup solenoid check (DTC 19) when running an automatic ECU on a manual transmission vehicle.'
tags: [ecu, transmission, tuning, conversion, wiring]
applies_to:
  obd: [0]
  models: [civic, crx, del-sol, integra]
  chassis: [da, dc2, ef, eg, eg-eh, ek]
complexity: advanced
---

# OBD0 Automatic ECU to Manual Conversion

When running an automatic OBD0 ECU in a vehicle with a manual transmission, the ECU will detect the absence of the automatic transmission lock-up solenoid and trigger **Diagnostic Trouble Code (DTC) 19**.

---

## Bypass Method: External Load Resistor

Rather than physically modifying the ECU circuit board (desoldering internal jumpers), this method uses an external resistor on the wiring harness to mimic the electrical load of the solenoid coil.

### Wiring Specification
*   **Target Pin 1 (Solenoid Output):** ECU Pin **A8**.
*   **Target Pin 2 (Ground):** ECU Pin **A2**.
*   **Resistor:** 220 Ohm (1/4W or 1/2W).

### Installation
1.  Locate wires A2 (Ground) and A8 (Lock-up Solenoid output) on the ECU harness.
2.  Splice and solder the 220 Ohm resistor between these two wires.
3.  Ensure all connections are insulated with heat-shrink tubing to prevent short-circuits.

---

## Technical Note: VTEC Repurposing
In some OBD0 applications, this pin (A8) is repurposed for VTEC solenoid control. If you are also performing a VTEC conversion, ensure that your wiring harness correctly routes the VTEC solenoid signal to the ECU and does not have this bypass resistor installed, as it will interfere with the VTEC solenoid signal.
