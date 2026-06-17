---
summary: 'An overview of Honda Dual-Point Fuel Injection (DPFI) systems, their operational limitations, and the recommended transition to Multi-Point Fuel Injection (MPFI).'
tags: [ecu, dpfi, fuel-injection, tuning, diagnostics]
applies_to:
  obd: [0, 1]
  models: [Civic, CRX]
complexity: intermediate
---

# Honda Dual-Point Fuel Injection (DPFI) Overview

Dual-Point Fuel Injection (DPFI) represents an early electronic fuel management system used by Honda, serving as the evolutionary successor to carbureted induction. Unlike modern systems, DPFI utilizes two injectors located in a common throttle body assembly to supply fuel to all cylinders.

## Operational Characteristics

In a DPFI system, fuel is injected into the intake manifold, and the cylinder currently in the intake stroke draws the air-fuel mixture. This configuration introduces several inherent mechanical limitations:

*   **Fuel Separation:** Due to the distance from the injectors to the intake valves, fuel tends to separate from the air stream.
*   **Poor Atomization:** The lack of individual port injectors results in suboptimal fuel droplet size.
*   **Uneven Distribution:** Cylinder-to-cylinder air-fuel ratio variance is common, as the intake path length differs for each cylinder.

These factors contribute to the lower power output and efficiency compared to Multi-Point Fuel Injection (MPFI) systems.

## ECU and Tuning Limitations

DPFI systems are managed by specific ECU models, including the PM5, PM9, and P04. 

> [!IMPORTANT]
> DPFI ECUs are generally considered unsuitable for performance tuning or modification. The software architecture for these units is extremely limited, and the hardware lacks the necessary drivers and processing capability to support high-performance fuel maps.

## Conversion to MPFI

For users seeking increased power, improved fuel economy, or the ability to perform engine tuning, a conversion to an MPFI system is the industry-standard recommendation. 

> [!TIP]
> Converting to MPFI involves upgrading the intake manifold, wiring harness, and ECU to a compatible OBD-series unit. This transition provides individual port injection, allowing for precise fuel control and significantly higher performance potential.