---
summary: 'Technical explanation of Mass Air Flow (MAF) sensors, detailing their function and highlighting differences compared to MAP-based speed-density systems.'
tags: [sensors, engine-management, fundamentals]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Mass Air Flow (MAF) Sensor

The **Mass Air Flow (MAF) sensor** is a device used in electronic fuel injection systems to directly measure the mass of air entering the engine. 

---

## Operating Principles
There are two primary methods by which MAF sensors measure airflow:

*   **Flapper-Valve (Vane Air Flow):** Uses a mechanical flap that is physically deflected by the incoming airflow. The degree of deflection corresponds to the air mass.
*   **Hot-Wire/Film Element:** Uses a heated wire element in the airflow stream. As air flows over the element, it cools it down; the ECU measures the change in resistance required to keep the wire at a constant temperature, correlating this to the mass of the air.

## Comparison to MAP Sensors
Honda's PGM-FI systems primarily utilize **MAP (Manifold Absolute Pressure)** based speed-density systems.
*   **MAF System:** Directly measures the air mass.
*   **MAP/Speed-Density System:** Calculates air mass based on manifold pressure, air temperature, and engine RPM.

*While MAF systems are excellent for direct measurement, Honda's MAP-based systems offer significant flexibility for performance tuning, as they are not restricted by the physical size or flow capacity of a MAF sensor housing.*
