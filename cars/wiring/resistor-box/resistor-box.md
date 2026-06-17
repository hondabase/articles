---
summary: 'Guide for wiring and installing a resistor box, required when running low-impedance Peak and Hold injectors on Honda ECUs.'
tags: [fuel-injection, wiring, hardware-modification]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, prelude]
  chassis: [ef, eg, eg-eh, ek]
complexity: intermediate
---

# Resistor Box Installation Guide

A **Resistor Box** is required when utilizing **Peak and Hold (Low-Impedance)** fuel injectors on Honda ECUs that were originally designed for high-impedance injectors. The box limits the current flow to the injectors to prevent damage to the ECU driver circuits.

---

## Technical Overview
*   **Purpose:** Limits current draw for low-impedance (2–5 $\Omega$) injectors to match the requirements of ECU driver circuits designed for high-impedance (12–16 $\Omega$) injectors.
*   **Application:**
    *   **OBD0:** Factory-equipped with a resistor box.
    *   **OBD1/OBD2:** Not factory-equipped. An external box must be added if swapping to low-impedance injectors.

## Wiring Procedure
The resistor box is wired in series between the 12V ignition power source and the fuel injectors.

1.  **Locate Ignition Power:** Identify the +12V switched power wire feeding the injector rail harness.
2.  **Mounting:** Secure the resistor box in a location with adequate airflow (the engine bay firewall is the standard factory location).
3.  **Wiring:**
    *   Cut the +12V power supply wire leading to the fuel injectors.
    *   Connect the +12V power source to the input of the resistor box.
    *   Connect the output side of the resistor box to the injector harness side (power side).
    *   Ensure all solder joints are sealed with heat-shrink tubing to prevent corrosion or shorts.

---

## Verification
After installation, use a multimeter to verify that the resistance between the injector plug and ground (on the power side) now reflects the added resistance of the resistor box.

*Warning: Failure to use a resistor box with low-impedance injectors will result in excessive current draw, likely causing the fuel injector driver transistors in the ECU to overheat and fail.*
