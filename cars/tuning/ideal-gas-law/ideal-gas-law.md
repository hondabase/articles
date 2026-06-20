---
summary: 'Application of the Ideal Gas Law in Honda speed-density engine management systems for calculating fuel requirements based on pressure and temperature.'
tags: [tuning, sensors, reference]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
---

# Ideal Gas Law in Speed-Density Tuning

The Ideal Gas Law is the fundamental physical principle used by Honda speed-density engine management systems to calculate air mass and determine fuel requirements. The equation is expressed as:

**PV = nRT**

## Variable Definitions

*   **P (Pressure):** Must be measured on an absolute pressure scale.
*   **V (Volume):** The displacement of the engine cylinder.
*   **n (Number of moles):** The quantity of gas molecules present.
*   **R (Ideal Gas Constant):** 8.3145 J/mol·K.
*   **T (Temperature):** Absolute temperature measured in Kelvin.

> [!IMPORTANT]
> All calculations involving the Ideal Gas Law require the use of absolute scales. Pressure must be referenced to a vacuum (Absolute Pressure), and temperature must be converted to Kelvin.

## Application in Engine Management

In a speed-density system, the ECU calculates the mass of air entering the engine by solving for **n** (the number of moles of air):

**n = PV / RT**

By solving for **n**, the ECU estimates the actual airflow into the engine based on the measured manifold absolute pressure (MAP) and intake air temperature (IAT). This value is then used to determine the appropriate fuel injector pulse width to achieve the target air-fuel ratio.

> [!TIP]
> Because the ECU relies on these sensors to calculate air mass, any deviation in sensor accuracy—such as a failing MAP sensor or heat-soaked IAT sensor—will result in incorrect fuel calculations and poor engine performance.
