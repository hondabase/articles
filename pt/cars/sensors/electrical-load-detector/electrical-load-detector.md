---
summary: 'The Electrical Load Detector (ELD) monitors vehicle electrical demand to allow the ECU to adjust idle and alternator output for stable engine operation.'
tags: [sensors, electrical, idle, alternator]
applies_to:
  obd: [0, 1, 2]
  models: [Honda]
complexity: beginner
---

# Electrical Load Detector (ELD) Operation

The Electrical Load Detector (ELD) measures total vehicle electrical load to determine whether the alternator should operate in low or high-output mode. 

Because Honda engines are calibrated for lean air-fuel ratios at idle, even minor electrical loads—such as turn signals or cooling fans—can cause idle instability. The ELD monitors these electrical demands and sends a signal to the ECU before the load impacts engine speed. Upon receiving this signal, the ECU makes proactive adjustments to the Idle Air Control (IAC) valve, fuel injection pulse width (PW), and ignition timing to maintain a stable idle.

## System Functionality

The ELD unit is typically integrated into the under-hood fuse/relay box. It functions as a current-sensing device that provides a voltage signal to the ECU proportional to the current flowing through the main fuse box.

*   **Low Load:** The ECU commands the alternator to a lower voltage output to reduce engine drag and improve fuel economy.
*   **High Load:** The ECU commands the alternator to a higher voltage output to ensure battery state-of-charge and prevent voltage drops during high electrical demand.

## ECU Compensation
When the ELD detects a significant increase in electrical load, the ECU performs the following compensations:

*   **IAC Valve:** Increases the duty cycle to allow more bypass air into the intake manifold.
*   **Fuel Injection:** Adjusts the pulse width to maintain the target air-fuel ratio during the transient load.
*   **Ignition Timing:** Modifies timing advance to compensate for the increased mechanical load on the engine from the alternator.

> [!NOTE]
> If the ELD circuit fails, the ECU will typically default to a high-output alternator state to ensure the battery remains charged, which may result in slightly reduced fuel economy and minor idle fluctuations.

> [!TIP]
> If you are experiencing erratic idle when electrical accessories are activated, verify the ELD signal voltage at the ECU pinout before diagnosing the IAC valve or vacuum leaks.