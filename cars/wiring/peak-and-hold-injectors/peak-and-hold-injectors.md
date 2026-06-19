---
summary: 'Technical overview of Peak and Hold (low impedance) fuel injectors, their operation, and the requirement for resistor boxes in Honda systems.'
tags: [fuel-injection, sensors, reference, wiring]
applies_to:
  brand: Honda
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
---

# Peak and Hold (Low Impedance) Injectors

**Peak and Hold injectors** (commonly known as **Low Impedance injectors**) are a type of fuel injector used in high-performance applications.

---

## Technical Overview
*   **Impedance:** Typically 2–5 $\Omega$ (Ohms).
*   **Current Draw:** Draws significantly more current than high-impedance injectors (~6–2.4 Amps).
*   **Operation:** 
    *   **Peak:** High initial current is applied to open the injector solenoid quickly and crisply.
    *   **Hold:** A reduced current is maintained to keep the injector open.

## Compatibility
The high current draw of these injectors can damage ECUs that are not designed to handle the load.

*   **Resistor Boxes:** To run low-impedance injectors on ECUs expecting high-impedance injectors, you must utilize an inline **Resistor Box** to limit the current draw to safe levels.
*   **OBD0:** Factory-equipped with a resistor box.
*   **OBD1/OBD2:** Factory-equipped for high-impedance injectors and do **not** have a resistor box. If swapping to low-impedance injectors on these systems, an external resistor box must be added.

*Always verify your injector impedance and ECU compatibility before installation to prevent driver circuit failure in the ECU.*
