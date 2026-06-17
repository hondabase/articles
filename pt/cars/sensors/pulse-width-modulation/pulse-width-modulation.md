---
summary: 'An overview of Pulse Width Modulation (PWM) as a digital-to-analog conversion method for controlling solenoids, stepper motors, and output devices in ECU systems.'
tags: [sensors, reference, pwm, electronics]
applies_to:
  obd: [0, 1, 2]
complexity: beginner
---

# Pulse Width Modulation (PWM) Fundamentals

Pulse Width Modulation (PWM) is a digital-to-analog conversion (DAC) technique used to control the average power delivered to electrical devices. By rapidly switching a digital signal between high and low states, the ECU can simulate varying voltage levels required for precise component operation.

## Applications in ECU Systems

PWM is primarily utilized to manage devices that require variable control rather than simple binary (on/off) states. Common applications include:

*   **Solenoids:** Controlling duty cycle for boost control or purge valves.
*   **Stepper Motors:** Managing idle air control (IAC) valves.
*   **Output Drivers:** Regulating power to auxiliary actuators.

> [!NOTE]
> The effective voltage delivered to the load is determined by the duty cycle—the percentage of time the signal remains in the "high" state during a single period.

## Technical Principles

The efficiency of PWM control depends on the frequency of the signal and the inductive nature of the load. 

*   **Duty Cycle:** The ratio of "on" time to the total period. A 50% duty cycle results in an average output voltage equal to half of the supply voltage.
*   **Frequency:** The speed at which the signal cycles. Higher frequencies allow for smoother control but increase switching losses in the ECU driver transistors.

> [!TIP]
> For further reading on the implementation of PWM in embedded systems, refer to the [Embedded.com PWM technical resource](http://web.archive.org/web/20260527195544/https://www.embedded.com/story/OEG20010821S0096).