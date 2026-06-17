---
summary: 'A technical definition of Top Dead Center (TDC) and its significance in the Honda combustion cycle and engine timing.'
tags: [sensors, reference, timing, engine-management]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Top Dead Center (TDC)

Top Dead Center (TDC) refers to the position of a piston when it reaches the highest point in its travel within the cylinder during the combustion cycle. 

## Technical Significance
In Honda engine management, the TDC position is a critical reference point for the Engine Control Unit (ECU) to calculate ignition timing and fuel injection events. The ECU determines this position using signals from the TDC sensor, typically located within the distributor assembly or near the crankshaft, depending on the engine generation.

> [!IMPORTANT]
> Accurate TDC calibration is essential for engine synchronization. Incorrect timing relative to TDC can lead to engine knock, power loss, or catastrophic mechanical failure.

## Application in Engine Timing
The TDC sensor provides a reference pulse once per crankshaft revolution. This signal is used by the ECU to:
* **Synchronize Ignition:** Determine the precise moment to trigger the ignition coil for spark plug firing.
* **Fuel Injection:** Coordinate the injection pulse width with the intake stroke.
* **Diagnostic Monitoring:** Detect misfires or timing deviations by comparing the TDC signal against the Crankshaft Position (CKP) and Cylinder Position (CYP) sensors.

## Verification
To verify mechanical TDC, align the timing marks on the crankshaft pulley with the pointer on the timing belt cover. 

> [!TIP]
> Always verify mechanical TDC using the crankshaft pulley marks before performing any ignition timing adjustments or distributor replacements.