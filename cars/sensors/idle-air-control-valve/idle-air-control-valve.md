---
summary: 'A technical overview of the Honda Idle Air Control Valve (IACV) function, its relationship with coolant temperature, and troubleshooting steps for ECU-related idle issues.'
tags: [ecu, sensors, idle, diagnostics, iacv]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Idle Air Control Valve (IACV) Operation and Diagnostics

The Idle Air Control Valve (IACV), also referred to as the Electronic Air Control Valve (EACV), regulates engine idle speed by bypassing a controlled amount of air around the throttle plate. The ECU modulates this valve based primarily on Engine Coolant Temperature (ECT) and target idle parameters.

## Operational Parameters

The ECU determines the required idle speed by referencing the ECT sensor. As the engine reaches operating temperature, the ECU reduces the duty cycle to the IACV to lower the idle speed to the factory specification.

| Parameter | Description |
| :--- | :--- |
| **Control Method** | Pulse Width Modulation (PWM) |
| **Primary Input** | Engine Coolant Temperature (ECT) |
| **Secondary Inputs** | Load (A/C, Electrical, Power Steering) |

> [!NOTE]
> Target idle settings are stored within the ECU calibration and can be modified via tuning software.

## Troubleshooting

If the engine exhibits an erratic idle, stalls, or triggers a Check Engine Light (CEL) Code 14, verify the mechanical integrity of the valve before inspecting the electrical circuit.

### ECU Driver Failure
A persistent Code 14 or a complete loss of idle control often indicates a failure of the internal ECU driver circuit. This is frequently caused by a shorted IACV solenoid drawing excessive current, which damages the internal components.

> [!WARNING]
> If you suspect an ECU driver failure, do not replace the ECU without first testing the IACV solenoid resistance. A faulty solenoid will immediately damage a replacement ECU.

For detailed diagnostic procedures and component-level repair, refer to the following guide:

*   [IACV Circuit Fix - R58 & R59](/cars/diagnostics/iacv-circuit-fix-r58-r59)

### Diagnostic Resources
::: widget error-codes :::
