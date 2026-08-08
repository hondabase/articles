---
summary: 'Diagnose and replace a faulty Ignition Control Module (ICM) in Honda and Acura vehicles experiencing no-start or intermittent ignition issues. Learn common symptoms and diagnostic steps.'
tags: [ignition-control-module, igniter, no-start, diagnostics]
applies_to:
  models: [accord, civic, crx, del-sol, integra, prelude]
complexity: intermediate
sources:
  - name: Nthefastlane
    title: 'Honda Ignition Switch Module Replacement'
    url: 'https://www.nthefastlane.com/honda-ignition-switch-module-repair'
    license: 'All rights reserved'
    license_url: 'https://www.nthefastlane.com/honda-ignition-switch-module-repair'
    adapted: true
---

# Honda Ignition Control Module Diagnosis and Replacement

## Introduction
The Ignition Control Module (ICM), often referred to as the igniter, is a critical component in the ignition system of many Honda and Acura vehicles. Its primary function is to receive a trigger signal from the Engine Control Unit (ECU) or crankshaft position sensor and then rapidly switch the primary coil circuit of the ignition coil on and off. This action induces the high voltage necessary for the spark plugs to ignite the air-fuel mixture. A failing ICM can lead to various ignition problems, most notably a complete loss of spark.

## Common Symptoms of a Failing ICM
A malfunctioning ICM can manifest in several ways, often making the vehicle unreliable or preventing it from starting altogether.

* **No-Start Condition (Cranks, No Spark):** This is the most common and definitive symptom. The engine will crank over normally, but there will be no spark at the spark plugs, preventing the engine from firing.
* **Intermittent Stalling:** The engine may suddenly die while driving, often restarting after a cool-down period, only to stall again later.
* **Rough Idling or Misfires:** While less common as a primary symptom, a failing ICM can sometimes cause inconsistent spark, leading to rough engine operation.
* **Engine Hesitation or Loss of Power:** Similar to misfires, inconsistent spark delivery can reduce engine performance.
* **Check Engine Light (CEL):** In some cases, the ECU may detect an ignition system fault and illuminate the CEL, potentially storing a diagnostic trouble code (DTC) related to ignition system malfunction.

## Diagnosing a Faulty Ignition Control Module
Proper diagnosis is crucial to avoid replacing components unnecessarily. The goal is to confirm a lack of spark and then systematically check the inputs and outputs of the ICM.

### Safety Precautions
> [!WARNING]
> Working with ignition systems involves high voltage. Always exercise extreme caution to avoid electrical shock. Disconnect the vehicle's battery negative terminal before performing any component replacement.

### Diagnostic Steps
1. **Confirm No Spark:**
* Remove a spark plug wire and attach it to a known good spark plug or a spark tester.
* Ground the spark plug/tester to a clean metal part of the engine.
* Have an assistant crank the engine while observing for spark.
* If no spark is present, proceed to check the ICM.
> [!CAUTION]
> Never allow spark plug wires to hang loose or arc to unintended components, as this can damage the ignition coil or ECU.

2. **Check Power Supply to the Distributor/ICM:**
* Locate the main power wire to the distributor or ICM. This is typically a 12V supply when the ignition is on.
* Using a multimeter, check for 12V with the ignition key in the ON (II) position.
* **Consult your factory service manual (FSM) for the specific wire color and pin location for your vehicle model.**

3. **Check Ground Connection:**
* Verify that the ICM has a solid ground connection.
* Use a multimeter to check for continuity between the ICM's ground terminal and a known good chassis ground.
* **Refer to the FSM for the correct ground wire location.**

4. **Check Trigger Signal from ECU/Sensor:**
* The ICM requires a trigger signal from the ECU or a crankshaft/camshaft position sensor to fire.
* This signal is typically a fluctuating voltage (e.g., 0-5V or 0-12V square wave) when the engine is cranking.
* Using an oscilloscope is ideal for this, but a multimeter set to AC voltage might show some activity, though it's not definitive.
* If no trigger signal is present, the issue might be with the ECU, crankshaft position sensor, or wiring, not the ICM itself.
* **The FSM will provide detailed procedures for testing the trigger signal and expected voltage ranges.**

5. **Test Ignition Coil (if external to ICM):**
* In some systems, the ignition coil is separate from the ICM. If you have power, ground, and a trigger signal to the ICM, but still no spark, the ignition coil itself might be faulty.
* **Follow FSM procedures for testing primary and secondary coil resistance.**

6. **ICM Specific Test (if available):**
* Some FSMs provide specific resistance or voltage tests for the ICM itself.
* Often, the most reliable test for an ICM is substitution with a known good unit, or confirming all inputs are correct and outputs are absent.

> [!IMPORTANT]
> If all inputs (power, ground, trigger signal) to the ICM are confirmed to be correct according to the FSM, and there is still no spark output from the ICM to the ignition coil, the ICM is likely faulty.

## Ignition Control Module Replacement Procedure
The ICM is commonly located inside the distributor housing on many older Honda/Acura models. The exact procedure may vary slightly by model and year.

### Tools and Materials
* Basic metric socket set and wrenches
* Screwdrivers (Phillips and flat-head)
* Needle-nose pliers
* Dielectric grease or thermal paste (if specified for your ICM)
* New Ignition Control Module

### Step-by-Step Replacement
1. **Prepare the Vehicle:**
* Park the vehicle on a level surface and engage the parking brake.
* Disconnect the negative terminal of the vehicle's battery using a 10mm wrench.
> [!WARNING]
> Disconnecting the battery will reset the ECU and radio presets. Ensure you have your radio security code if applicable.

2. **Access the Distributor:**
* Locate the distributor on the engine. It's usually on the cylinder head, often at one end of the camshaft.
* Carefully disconnect the main electrical connector(s) from the distributor.
* Remove the spark plug wires from the distributor cap. It's often helpful to label them or remove them one at a time to ensure correct reinstallation.
* Unclip or unscrew the distributor cap and remove it. Set it aside.

3. **Remove the Old ICM:**
* Inside the distributor, you will see the rotor, and typically beneath it, the ICM and ignition coil.
* Remove the rotor by unscrewing its retaining screw.
* The ICM is usually secured by two or three small screws and has electrical connectors. Disconnect any remaining wires from the ICM and ignition coil.
* Carefully unscrew the mounting screws and remove the old ICM from the distributor housing.
> [!TIP]
> Take photos of the wiring and component orientation before disassembly to aid reassembly.

4. **Install the New ICM:**
* Clean the mounting surface inside the distributor, ensuring it's free of old thermal paste or debris.
* If your new ICM or the FSM specifies, apply a thin, even layer of dielectric grease or thermal paste to the back of the new ICM where it contacts the distributor housing. This aids in heat dissipation.
* Position the new ICM in the distributor housing and secure it with its mounting screws. Do not overtighten.
* Reconnect all electrical connectors to the new ICM and ignition coil. Ensure they are fully seated.

5. **Reassemble the Distributor:**
* Reinstall the rotor onto its shaft and secure it with its screw.
* Place the distributor cap back onto the distributor housing and secure it with its clips or screws.
* Reconnect the spark plug wires to the correct terminals on the distributor cap.
* Reconnect the main electrical connector(s) to the distributor.

6. **Final Steps:**
* Reconnect the negative terminal of the vehicle's battery.
* Start the engine and check for proper operation. Listen for any unusual noises and confirm the engine runs smoothly.

## Verification
After replacement, the engine should start reliably and run smoothly without misfires or stalling. If the issue persists, re-verify all connections and re-diagnose the ignition system, potentially looking at other components like the ignition coil, crankshaft position sensor, or ECU.

> [!NOTE]
> Always consult the specific factory service manual for your vehicle's make, model, and year for precise diagnostic procedures, torque specifications, and component locations. This article provides general guidance applicable to many Honda/Acura vehicles.
