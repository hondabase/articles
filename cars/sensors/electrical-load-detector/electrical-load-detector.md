---
summary: 'The Electrical Load Detector (ELD) monitors vehicle electrical consumption to allow the ECU to proactively adjust idle parameters and alternator output.'
tags: [sensors, electrical, idle, alternator]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Electrical Load Detector (ELD) Operation

The Electrical Load Detector (ELD) is a sensor designed to monitor the vehicle's total electrical consumption. This data is used by the Engine Control Module (ECM) to determine the necessary alternator output mode (low or high) and to stabilize engine idle during electrical load transitions.

## Functional Overview

Honda engines are calibrated for lean operation at idle to maximize fuel efficiency. Because of this, even minor electrical loads—such as the activation of turn signals or cooling fans—can cause a noticeable drop in engine RPM. 

The ELD monitors current flow through the main fuse box and sends a signal to the ECM. Upon receiving this signal, the ECM proactively adjusts the following parameters to compensate for the load:

*   **Idle Air Control (IAC) Valve:** Increases bypass air to maintain target idle speed.
*   **Injector Pulse Width (PW):** Adjusts fuel delivery to maintain the stoichiometric air-fuel ratio.
*   **Ignition Timing:** Modifies spark advance to stabilize engine torque output.

> [!NOTE]
> The ELD allows the ECM to compensate for electrical loads before they result in a perceptible fluctuation in engine idle.

## System Integration

The ELD is integrated into the vehicle's power distribution system, typically located within the under-hood fuse/relay box. It acts as a current-sensing device that provides a variable voltage signal to the ECM, which is proportional to the total electrical load of the vehicle.

### Troubleshooting Considerations

If the ELD circuit fails or provides an out-of-range signal, the ECM may trigger a Diagnostic Trouble Code (DTC) related to the charging system or idle control. 

> [!WARNING]
> Always verify the integrity of the ELD ground and signal wiring before replacing the sensor unit, as high-resistance connections in the sensor circuit can mimic a faulty ELD.
