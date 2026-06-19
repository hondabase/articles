---
summary: 'A piggyback controller is an aftermarket device that intercepts and modifies engine sensor signals before they reach the ECU to alter engine management parameters.'
tags: [ecu, tuning, sensors, piggyback, fuel-management]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Piggyback Engine Management Controllers

A piggyback controller is an aftermarket device installed in series with the factory ECU. These devices function by intercepting signals from engine sensors and modifying the data before it reaches the ECU, effectively "tricking" the ECU into adjusting fuel delivery or ignition timing.

## Common Piggyback Systems

Several devices are frequently utilized for signal manipulation in Honda engine management:

*   **Apexi SAFC / VAFC Series:** These units are commonly used to adjust air-fuel ratios by modifying the Mass Air Flow (MAF) or Manifold Absolute Pressure (MAP) sensor signals.
*   **Greddy E-Manage:** A more advanced system capable of controlling fuel injectors and ignition timing beyond simple sensor signal offset.
*   **Forced Induction Controllers:** Many supercharger kits (such as early Jackson Racing Supercharger systems) include basic piggyback-style components, such as relay-based signal modifiers, to compensate for increased airflow.

> [!WARNING]
> Piggyback controllers operate by providing false data to the ECU. This can lead to unintended side effects, such as incorrect ignition timing maps or the triggering of diagnostic trouble codes (DTCs) due to implausible sensor readings.

## Operational Principles

Piggyback controllers typically interface with the following sensor circuits:

*   **MAP/MAF Sensors:** Modifying these signals alters the ECU's calculation of engine load.
*   **Throttle Position Sensor (TPS):** Used to determine enrichment or transition points.
*   **RPM/Crank Signal:** Used to synchronize the piggyback's modifications with engine speed.

> [!IMPORTANT]
> Because piggybacks do not alter the underlying code or lookup tables within the ECU, they are limited in their ability to manage complex engine states compared to a standalone ECU or a remapped factory ECU. Always verify sensor scaling and wiring integrity when troubleshooting issues with piggyback-equipped vehicles.
