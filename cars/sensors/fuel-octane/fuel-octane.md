---
summary: 'Understanding fuel octane ratings and their impact on Honda engine performance, knock resistance, and ignition timing optimization.'
tags: [fuel, tuning, ignition, performance]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Fuel Octane Ratings and Engine Performance

Fuel octane is a measure of gasoline's resistance to pre-ignition and detonation (knock). In high-performance Honda engines, selecting the correct octane rating is critical for maintaining engine longevity and optimizing ignition timing.

## Understanding Octane Ratings

Octane ratings represent the fuel's ability to withstand compression without spontaneously igniting. When an engine is under load, high cylinder pressures and temperatures can cause the air-fuel mixture to ignite prematurely, leading to engine knock.

*   **Higher Octane:** Provides greater resistance to detonation, allowing for more aggressive ignition timing and higher compression ratios.
*   **Lower Octane:** More susceptible to pre-ignition under high-load conditions, which may force the ECU to pull ignition timing to protect the engine.

> [!IMPORTANT]
> Always use the minimum octane rating specified in your vehicle's owner's manual. Using a higher octane fuel than required does not provide additional power unless the engine management system is tuned to take advantage of the increased knock resistance.

## Impact on Tuning

When calibrating an ECU, the octane rating of the fuel dictates the limits of the ignition map. 

*   **Knock Threshold:** Engines with higher compression ratios or forced induction require higher octane fuel to prevent knock.
*   **Ignition Timing:** If the fuel octane is too low for the current ignition map, the knock sensor will trigger, and the ECU will retard timing, resulting in a significant loss of power and efficiency.

> [!TIP]
> If you are experiencing persistent knock, verify that you are using the correct fuel grade before adjusting ignition maps or checking mechanical components.

## Measurement Standards

Octane is typically measured using two methods, which are often averaged to provide the "Pump Octane Number" (R+M)/2 found on gas station pumps:

1.  **Research Octane Number (RON):** Measures performance under low-severity conditions.
2.  **Motor Octane Number (MON):** Measures performance under high-severity conditions, such as high-load or high-RPM operation.