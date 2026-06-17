---
summary: 'An overview of the Dual-Point Fuel Injection (DPFI) system, its operational limitations, and its role in early Honda engine management.'
tags: [ecu, dpfi, fuel-injection, diagnostics]
applies_to:
  obd: [0, 1]
  models: [civic, crx]
  chassis: [ef]
complexity: intermediate
---

# Dual-Point Fuel Injection (DPFI) Overview

Dual-Point Fuel Injection (DPFI) represents an early electronic fuel injection architecture used by Honda, serving as a transitional technology between carbureted systems and Multi-Point Fuel Injection (MPFI).

## System Operation
The DPFI system utilizes two fuel injectors located within a common intake manifold. Fuel delivery is determined by the intake stroke of the individual cylinder; the vacuum created by the cylinder on the intake stroke draws the atomized fuel from the manifold.

## Technical Limitations
DPFI systems are inherently limited compared to MPFI systems due to several design constraints:

*   **Fuel Separation:** Inconsistent fuel distribution across cylinders.
*   **Atomization:** Poor fuel atomization characteristics compared to port-injected systems.
*   **Delivery Efficiency:** Inefficient fuel delivery timing, which restricts overall engine volumetric efficiency and power output.

> [!IMPORTANT]
> Due to these design limitations, DPFI systems are generally considered unsuitable for performance tuning. Software development for DPFI-specific ECUs (such as the PM5, PM9, and P04) is virtually non-existent.

## Performance Upgrades
For users seeking increased power or tuning capabilities, an MPFI conversion is the standard industry recommendation. Converting to an MPFI system allows for individual cylinder fuel control and significantly improved air-fuel ratio management.

### Common DPFI ECU Variants
| ECU Model | System Type | Notes |
| :--- | :--- | :--- |
| PM5 | DPFI | Standard 1.5L application |
| PM9 | DPFI | Standard 1.5L application |
| P04 | DPFI | Late-model DPFI variant |

> [!TIP]
> If you are planning a performance build, prioritize an MPFI intake manifold and wiring harness conversion before attempting any ECU-based tuning.