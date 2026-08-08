---
summary: 'Diagnose intermittent hot and cold air conditioning in Honda Civic EG and EK models by checking refrigerant levels, compressor clutch, condenser fan, and electrical components.'
tags: [air-conditioning, diagnostics, civic]
applies_to:
  models: [civic]
  chassis: [eg, ek]
complexity: intermediate
sources:
  - name: Nthefastlane
    title: 'A/C Hot & Cold Possible FREE "FIX"'
    url: 'https://www.nthefastlane.com/ac-hot-cold-civic-fix'
    license: 'All rights reserved'
    license_url: 'https://www.nthefastlane.com/ac-hot-cold-civic-fix'
    adapted: true
---

# Diagnosing Intermittent Hot and Cold Air Conditioning in Honda Civic (EG/EK)

Intermittent hot and cold air conditioning (A/C) is a common complaint in Honda Civic models, particularly the EG and EK generations. This issue can manifest as the A/C blowing cold air for a period, then switching to warm or ambient air, or cycling between the two. Effective diagnosis requires a systematic approach to identify the root cause.

## Common Causes of Intermittent A/C Operation

Several components within the A/C system can contribute to inconsistent cooling performance. Understanding these potential failure points is key to accurate diagnosis.

### 1. Refrigerant Level Issues

> [!IMPORTANT]
> Both undercharged and overcharged refrigerant levels can cause intermittent A/C performance. An undercharge leads to insufficient cooling, while an overcharge can cause excessive pressure, triggering safety cut-offs.

* **Low Refrigerant:** Often due to a slow leak in the system. When the pressure drops below a certain threshold, the low-pressure switch will disengage the compressor to prevent damage.
* **Overcharged System:** Too much refrigerant can lead to excessively high pressures, causing the high-pressure switch to disengage the compressor.

### 2. A/C Compressor Clutch Problems

The compressor clutch engages and disengages the compressor. Issues here can prevent the compressor from consistently running.

* **Excessive Clutch Gap:** Over time, the clutch plate and pulley can wear, increasing the gap. If the gap becomes too large, the electromagnet may not be strong enough to pull the clutch plate in, especially when hot.
* **Weak Clutch Coil:** The electromagnetic coil within the clutch can weaken, failing to engage the clutch reliably.
* **Faulty A/C Clutch Relay:** A failing relay can intermittently prevent power from reaching the clutch coil.

### 3. Condenser Fan Malfunction

The condenser fan pulls air through the A/C condenser, dissipating heat from the refrigerant. Without proper airflow, the system pressure can rise excessively.

* **Inoperative Fan Motor:** A seized or faulty fan motor will prevent heat dissipation, leading to high-side pressure spikes and compressor disengagement.
* **Faulty Fan Relay or Fuse:** Electrical issues can prevent the fan from operating.

### 4. Blend Door Actuator Issues

The blend door controls the mix of hot and cold air entering the cabin. If it's stuck or malfunctioning, it can direct warm air even when the A/C is on.

* **Stuck or Broken Actuator:** The mechanical linkage or the electric motor controlling the blend door can fail, preventing it from moving to the 'cold' position.
* **Electrical Fault:** Wiring or control unit issues can prevent the actuator from receiving the correct commands.

### 5. Pressure Switches

Honda A/C systems use pressure switches (low and high) to protect the compressor. These switches can become faulty and provide incorrect readings.

* **Low-Pressure Switch:** Disengages the compressor if refrigerant pressure is too low.
* **High-Pressure Switch:** Disengages the compressor if refrigerant pressure is too high.
* **Faulty Switch:** A malfunctioning switch can prematurely or intermittently cut power to the compressor.

### 6. Electrical System Faults

General electrical issues can disrupt the A/C system's operation.

* **Blown Fuses:** Check fuses related to the A/C compressor, condenser fan, and HVAC control unit.
* **Corroded Wiring or Connectors:** Poor electrical connections can lead to intermittent power delivery.
* **Faulty Ground Points:** Poor grounds can cause various electrical components to malfunction.

## Diagnostic Procedure

Follow these steps to systematically diagnose intermittent A/C issues.

### 1. Initial Inspection and Verification

* **Verify Complaint:** Operate the A/C system and confirm the intermittent hot/cold symptom. Note any specific conditions (e.g., only at idle, only when hot).
* **Visual Inspection:** Check for obvious signs of refrigerant leaks (oily residue), damaged wiring, or debris blocking the condenser.
* **Listen for Compressor:** With the engine running and A/C on, listen for the compressor clutch engaging and disengaging. Note if it cycles rapidly or not at all.

### 2. Refrigerant System Check

> [!CAUTION]
> Always wear appropriate eye protection and gloves when working with refrigerant. Improper handling can cause severe injury.

* **Connect Manifold Gauges:** Attach a set of A/C manifold gauges to the high and low-pressure service ports. Observe the pressure readings with the engine running and A/C on.
* **Low-Side Pressure:** Typically, this should be in a specific range (confirm against the factory service manual for your specific Civic model).
* **High-Side Pressure:** This pressure will be significantly higher and also has a specified range (confirm against FSM).
* **Interpret Readings:**
* **Low readings on both sides:** Indicates an undercharged system or a restriction.
* **High readings on both sides:** Suggests an overcharged system or a lack of condenser airflow.
* **Rapidly cycling compressor with low low-side pressure:** Strong indicator of low refrigerant.
* **Leak Detection:** If low on refrigerant, use a leak detector (electronic sniffer or UV dye) to locate the source of the leak.

### 3. Electrical System Diagnostics

* **Check Fuses and Relays:** Inspect all A/C-related fuses in the under-hood and cabin fuse boxes. Swap A/C relays with known good relays (e.g., horn relay if identical) to test their function.
* **A/C Compressor Clutch Circuit:**
* **Voltage Test:** With the A/C on, check for 12V at the compressor clutch connector. If no voltage, trace the circuit back through the pressure switches and A/C relay.
* **Resistance Test:** Disconnect the clutch connector and measure the resistance of the clutch coil. Compare to FSM specifications. An open circuit or very high resistance indicates a faulty coil.
* **Clutch Gap:** Measure the gap between the clutch plate and the pulley. If it exceeds the FSM specification, shims may need to be removed or added, or the clutch assembly may require replacement.
* **Condenser Fan Circuit:**
* **Operation Check:** Ensure the condenser fan runs when the A/C is on. If not, check for voltage at the fan motor connector and test the fan motor's resistance.
* **Fan Relay:** Test or swap the condenser fan relay.
* **Pressure Switches:**
* **Continuity Test:** Disconnect the electrical connector from the low and high-pressure switches. With the system properly charged, the low-pressure switch should show continuity. The high-pressure switch should also show continuity under normal operating pressures. Refer to the FSM for specific test conditions and expected values.

### 4. HVAC Control Unit and Blend Door

* **Blend Door Actuator Test:**
* Locate the blend door actuator (typically behind the dashboard).
* Listen for its operation when changing temperature settings.
* Visually inspect its movement if accessible.
* Check for voltage at the actuator connector while changing settings. If the actuator is not moving but receiving power, it's likely faulty.
* **HVAC Control Unit:** If all other components test good, the HVAC control unit itself might be faulty. Consult the FSM for specific diagnostic procedures for the control unit, which may involve checking input signals from sensors.

## Tools Required

* A/C Manifold Gauge Set
* Multimeter (for voltage, resistance, and continuity checks)
* Refrigerant Leak Detector (electronic or UV dye kit)
* Basic Hand Tools (wrenches, sockets, screwdrivers)
* Feeler Gauges (for clutch gap measurement)

## Safety Precautions

> [!WARNING]
> Refrigerant can cause frostbite and severe eye injury. Always wear safety glasses and gloves when working with the A/C system.

* **Electrical Safety:** Disconnect the battery's negative terminal before performing any electrical component replacement or extensive wiring checks.
* **Refrigerant Handling:** Do not vent refrigerant into the atmosphere. If the system needs to be opened, ensure proper recovery and recharging procedures are followed by a certified technician or using appropriate equipment.
* **Hot Components:** Engine and A/C components can be hot. Allow the engine to cool before working on the system.

## Confirm Against Factory Service Manual (FSM)

> [!IMPORTANT]
> Always refer to the specific Honda Factory Service Manual for your Civic's year and model. The FSM provides precise specifications for refrigerant pressures, electrical values (voltage, resistance), clutch gap, and detailed diagnostic flowcharts that are crucial for accurate repair.
