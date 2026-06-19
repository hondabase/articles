---
summary: 'Spark Advance defines the angular rotation in degrees between the ignition event and the piston reaching Top Dead Center (TDC).'
tags: [ignition, timing, sensors, reference]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Spark Advance Fundamentals

Spark Advance refers to the number of degrees of crankshaft rotation that occur between the moment the spark plug fires and the piston reaches Top Dead Center (TDC).

## Technical Overview

Proper spark timing is critical for engine efficiency, power output, and longevity. Because the air-fuel mixture requires a finite amount of time to burn, the spark must be initiated before the piston reaches the top of its compression stroke.

> [!NOTE]
> Spark advance is measured in degrees before top dead center (BTDC).

## Factors Influencing Spark Advance

The Engine Control Unit (ECU) calculates the optimal ignition timing based on several real-time variables:

*   **Engine Load:** Higher load typically requires less advance to prevent detonation.
*   **Engine Speed (RPM):** As RPM increases, the piston moves faster, requiring more advance to ensure peak cylinder pressure occurs at the optimal point after TDC.
*   **Intake Air Temperature (IAT):** Higher temperatures increase the risk of knock, often requiring the ECU to pull timing.
*   **Coolant Temperature (ECT):** Cold engines may require different timing maps to assist in warm-up and emissions control.

## Detonation and Timing

> [!WARNING]
> Excessive spark advance can lead to pre-ignition or detonation (knock), which can cause catastrophic engine failure, including damaged pistons, rod bearings, and head gaskets.

Always ensure that ignition maps are tuned conservatively for the specific fuel octane and engine compression ratio being utilized.
