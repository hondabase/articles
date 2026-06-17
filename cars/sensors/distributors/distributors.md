---
summary: 'A comprehensive overview of Honda distributor operation, function, and role in the ignition system across OBD0, OBD1, and OBD2 platforms.'
tags: [ignition, distributor, sensors, timing]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Honda Distributor Operation and Function

A distributor is a mechanical and electrical device responsible for routing high-voltage current from the [Ignition Coil](/cars/ignition/ignition-coil) to the individual spark plugs in the correct firing order. In Honda applications, the distributor housing also serves as the primary mounting point for critical engine management sensors.

## Core Components

The Honda distributor assembly typically integrates the following components into a single housing:

*   **Ignition Coil:** Generates the high-voltage spark required for combustion.
*   **Igniter (ICM):** The Ignition Control Module acts as a high-speed switch, grounding the coil primary circuit to trigger the spark.
*   **Distributor Cap and Rotor:** Mechanically routes the high-voltage spark to the specific spark plug wire corresponding to the cylinder in the firing sequence.
*   **Internal Sensors:** Most Honda distributors house the Crankshaft Position (CKP), Top Dead Center (TDC), and Cylinder Position (CYP) sensors.

## Sensor Functions

The sensors located within the distributor housing provide the ECU with essential timing and synchronization data:

| Sensor | Function |
| :--- | :--- |
| **CKP (Crankshaft Position)** | Detects engine RPM and crankshaft position for ignition timing. |
| **TDC (Top Dead Center)** | Identifies when the #1 piston is at the top of its compression stroke. |
| **CYP (Cylinder Position)** | Provides cylinder identification for sequential fuel injection. |

> [!IMPORTANT]
> The internal sensors are critical for engine operation. If the ECU loses signal from the CKP, TDC, or CYP sensors, the engine will typically fail to start or enter a "limp mode" due to the inability to calculate ignition and fuel injection timing.

## Maintenance and Diagnostics

Regular inspection of the distributor is necessary to ensure consistent ignition performance.

*   **Cap and Rotor:** Inspect for carbon tracking, pitting, or oxidation on the contact points. Replace these components if wear is evident to prevent misfires.
*   **O-Ring Seal:** The distributor O-ring is a common failure point that leads to oil leaks into the distributor housing. If oil is found inside the cap, the internal O-ring must be replaced to prevent sensor contamination and electrical shorts.
*   **Igniter Testing:** If the engine cranks but has no spark, the igniter is the most common point of failure. Use a multimeter to check for continuity and signal switching according to the specific service manual for your chassis.

> [!TIP]
> When replacing the distributor or adjusting ignition timing, always use a timing light to verify the base ignition timing at the crankshaft pulley while the service connector is jumped.