---
summary: 'An overview of the Dual Point Fuel Injection (DPFI) system used in early Honda engines, detailing its operational principles and fuel delivery configuration.'
tags: [fuel-injection, dpfi, sensors, intake]
applies_to:
  obd: [0, 1]
  models: [Civic, CRX]
complexity: beginner
---

# Dual Point Fuel Injection (DPFI) Overview

Dual Point Fuel Injection (DPFI) is a throttle body injection system utilized by Honda on early D-series engines. Unlike Multi-Point Fuel Injection (MPFI) systems that feature an individual injector for each cylinder, the DPFI system utilizes two injectors located within the throttle body assembly to deliver fuel to the intake manifold.

## System Operation

The DPFI system functions as a semi-sequential injection setup where fuel is atomized at the throttle body and distributed through the intake manifold runners.

> [!NOTE]
> DPFI systems are often identified by the presence of two fuel injectors mounted vertically within the throttle body housing, distinct from the single-injector TBI systems found on other manufacturers' vehicles of the same era.

## Key Components

*   **Throttle Body:** Houses the two fuel injectors, the Throttle Position Sensor (TPS), and the Idle Air Control Valve (IACV).
*   **Fuel Injectors:** Two low-impedance injectors responsible for the entire fuel delivery requirements of the engine.
*   **Intake Manifold:** Designed specifically for DPFI to ensure proper air-fuel mixture distribution from the central throttle body to the individual intake ports.

## Diagnostic Considerations

When troubleshooting DPFI systems, focus on the following areas:

*   **Injector Pulse:** Verify that both injectors are receiving a signal from the ECU.
*   **Fuel Pressure:** Ensure the fuel pressure regulator (integrated into the throttle body assembly) is maintaining the correct operating pressure.
*   **Sensor Calibration:** The TPS and coolant temperature sensors are critical for the ECU to calculate the correct pulse width for the dual-injector setup.

::: widget error-codes :::

> [!TIP]
> If you are experiencing persistent fuel delivery issues, check the injector resistor box wiring, as these components are prone to corrosion on high-mileage OBD0 vehicles.