---
summary: 'Learn how to disable the VTEC Vehicle Speed Sensor (VSS) check in Honda OBD1 ECUs, enabling VTEC engagement without a working speed signal.'
tags: [ecu, vtec, sensors, tuning]
applies_to:
  models: [civic, integra, del-sol]
  chassis: [ef, eg, dc2]
complexity: beginner
---

# Disabling the VTEC Vehicle Speed Sensor (VSS) Check

In stock Honda OBD1 ECU configurations, the VTEC engagement logic requires a valid signal from the Vehicle Speed Sensor (VSS). If the ECU does not detect vehicle movement, it will prevent VTEC from engaging to protect the engine. This check can be bypassed via software modification to allow VTEC engagement regardless of vehicle speed.

## Prerequisites

To modify the VSS check, you must have:
*   A socketed OBD1 ECU.
*   An EPROM burner/programmer.
*   Tuning software capable of editing the ECU bin file (e.g., Crome, Neptune, or TunerPro).

## Modification Procedure

The VSS check is controlled by a specific bit in the ECU's calibration data. By toggling this bit, the ECU will ignore the VSS input when calculating VTEC engagement parameters.

> [!WARNING]
> Disabling the VSS check allows VTEC to engage while the vehicle is stationary. Use caution, as this can lead to engine damage if the engine is revved to high RPMs without load.

### Steps to Disable
1.  Open your current ECU calibration file (.bin) in your tuning software.
2.  Navigate to the **VTEC Settings** or **Advanced Parameters** menu.
3.  Locate the option labeled **Disable VSS Check** or **VTEC Speed Check**.
4.  Check the box or set the value to **Enabled** (to disable the check).
5.  Save the modified bin file.
6.  Burn the new file to your EPROM chip and install it into the ECU.

## Technical Considerations

*   **Diagnostic Trouble Codes (DTCs):** Disabling the VSS check in the software does not fix a faulty VSS sensor. If your sensor is broken, the ECU may still trigger a Code 17 (VSS).
*   **Fuel Economy:** The ECU uses the VSS signal for various fuel trim calculations. While VTEC will engage, ensure your fuel maps are properly tuned for all load conditions.
*   **Safety:** This modification is intended for specific racing applications (e.g., dyno tuning or drag racing) where the vehicle may not be moving but high-RPM operation is required.

> [!TIP]
> Always verify your changes by performing a data log to ensure the VTEC solenoid activates at the desired RPM threshold after the modification.
