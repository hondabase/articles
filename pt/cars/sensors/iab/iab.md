---
summary: 'Technical overview of the Intake Air Bypass (IAB) system, explaining its function in optimizing engine torque and power through variable intake runner lengths.'
tags: [sensors, intake, iab, performance]
applies_to:
  obd: [0, 1, 2]
  models: [B18C1, H22A]
complexity: beginner
---

# Intake Air Bypass (IAB) System

The Intake Air Bypass (IAB) system utilizes a vacuum-actuated valve to toggle between two distinct intake runner paths within the intake manifold. This dual-stage design optimizes engine performance across the RPM range:

*   **Low RPM:** The IAB valves remain closed, forcing air through the longer intake runners to increase intake air velocity and improve low-end torque.
*   **High RPM:** The IAB valves open, allowing air to bypass the long runners and utilize shorter, wider paths to maximize airflow and peak horsepower.

## Application
The IAB system is standard equipment on specific high-performance Honda intake manifolds, most notably:
*   **B18C1:** Acura Integra GS-R
*   **H22A:** Honda Prelude VTEC

> [!NOTE]
> The IAB system is controlled by the ECU via a solenoid valve. When the engine reaches the specified activation RPM, the ECU grounds the solenoid, allowing vacuum to actuate the butterfly valves.

## System Components
The IAB system consists of the following primary components:
*   **IAB Solenoid:** An electromagnetic valve that regulates vacuum supply to the actuator.
*   **Vacuum Actuator:** A diaphragm-based canister mounted to the intake manifold that physically opens and closes the butterfly plates.
*   **Butterfly Plates:** Internal valves located within the intake manifold runners.
*   **Vacuum Reservoir:** A small canister used to maintain consistent vacuum pressure for the actuator.

## Troubleshooting
If the IAB system fails to engage, verify the following:
1.  **Vacuum Lines:** Inspect all rubber lines for cracks, leaks, or improper routing.
2.  **Solenoid Function:** Test the solenoid for continuity and ensure it clicks when 12V is applied.
3.  **Actuator Diaphragm:** Check the actuator for vacuum leaks by applying manual vacuum with a hand pump.
4.  **ECU Output:** Ensure the ECU is providing the ground signal to the solenoid at the correct RPM threshold.