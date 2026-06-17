---
summary: 'An overview of the Intake Air Bypass (IAB) system, which optimizes engine performance by switching between long and short intake runners based on RPM.'
tags: [sensors, intake, h22a, gsr, iab]
applies_to:
  obd: [0, 1, 2]
  models: [prelude]
  chassis: [bb]
complexity: beginner
---

# Intake Air Bypass (IAB) System

The Intake Air Bypass (IAB) system utilizes a vacuum-actuated valve to switch between two distinct intake manifold runner lengths. This dual-stage design optimizes engine volumetric efficiency across the entire power band:

*   **Low RPM:** The system utilizes longer intake runners to increase air velocity, enhancing low-end torque.
*   **High RPM:** The system switches to shorter intake runners to reduce restriction and maximize peak horsepower.

## Application
The IAB system is standard equipment on specific high-performance Honda intake manifolds, most notably:
*   B18C1 (GSR)
*   H22A (Prelude)

> [!NOTE]
> The IAB valve is controlled by the ECU via a solenoid. When the engine reaches the activation threshold (typically around 5,700 RPM on H22A engines), the ECU energizes the solenoid to open the butterfly valves.

## System Components
The IAB system consists of the following primary components:

*   **IAB Solenoid:** An electrical valve that manages vacuum delivery to the actuator.
*   **Vacuum Actuator:** A diaphragm-based canister that physically moves the butterfly valve linkage.
*   **Butterfly Valves:** Internal plates within the intake manifold plenum that open or close the secondary air passages.
*   **Vacuum Reservoir:** A small canister used to maintain consistent vacuum pressure for the actuator during wide-open throttle (WOT) conditions.

## Troubleshooting
If the IAB system fails to actuate, verify the following:

1.  **Vacuum Lines:** Ensure all lines are free of cracks, leaks, or blockages.
2.  **Solenoid Function:** Test the solenoid for continuity and ensure it clicks when 12V is applied.
3.  **Actuator Diaphragm:** Check the actuator for vacuum leaks by applying manual vacuum with a hand pump.
4.  **Mechanical Binding:** Inspect the butterfly valve linkage for carbon buildup or physical obstructions that may prevent full range of motion.