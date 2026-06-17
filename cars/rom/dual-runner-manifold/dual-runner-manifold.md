---
summary: 'Understand the operation and tuning principles of Honda dual-runner intake manifolds, including IAB (Intake Air Bypass) activation for optimized torque and power.'
tags: [tuning, iab, intake, manifold, performance]
applies_to:
  obd: [0, 1, 2]
  models: [accord, integra, prelude]
  chassis: [bb, cb-cd, da, dc2]
complexity: beginner
---

# Dual Runner Intake Manifold Operation

Dual-runner intake manifolds, found on engines such as the F22, B18C1, and H22A, utilize a variable geometry design to optimize volumetric efficiency across the entire RPM range. The system employs two distinct air passages to balance low-end torque with high-RPM horsepower.

## Operational Principles

The manifold features a secondary set of intake runners controlled by butterfly valves, often referred to as Intake Air Bypass (IAB) valves.

*   **Low RPM Range:** The butterfly valves remain closed, forcing air through the longer primary runners. This increases air velocity and intake charge inertia, which promotes higher torque production at lower engine speeds.
*   **High RPM Range:** Once the engine reaches a specific RPM threshold, the ECU triggers the IAB solenoid to open the butterfly valves. This allows air to flow through the shorter secondary runners, reducing intake restriction and optimizing the engine for high-RPM power output.

> [!NOTE]
> The transition point between runner stages is determined by the ECU calibration. Tuning the IAB activation point is critical when modifying engine components like camshafts or exhaust headers to ensure a smooth torque curve.

## System Components

The IAB system relies on the following components for proper operation:

*   **IAB Solenoid:** An ECU-controlled vacuum solenoid that regulates the vacuum supply to the intake manifold actuator.
*   **Vacuum Actuator:** A diaphragm-based canister that physically opens and closes the butterfly valves.
*   **Butterfly Valves:** Internal plates located within the intake manifold plenum that restrict or open the secondary runners.

> [!WARNING]
> Ensure the vacuum lines connected to the IAB actuator are free of leaks. A vacuum leak in this system will prevent the secondary runners from opening, resulting in a significant loss of power at high RPM.

## Tuning Considerations

When modifying the engine, the IAB activation point may require adjustment within the ECU ROM. 

*   **Activation RPM:** This value should be set based on dyno testing to ensure the transition occurs where the torque curves of the long and short runners intersect.
*   **Hysteresis:** Most ECU strategies include a hysteresis buffer to prevent the IAB valves from rapidly cycling (fluttering) if the engine speed fluctuates near the activation threshold.