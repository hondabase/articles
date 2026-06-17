---
summary: 'Technical overview of Input/Output (I/O) port architecture in Honda ECU microcontrollers and their role in interfacing with engine sensors and actuators.'
tags: [ecu, mcu, sensors, actuators, hardware]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# Honda ECU Input/Output (I/O) Architecture

Input/Output (I/O) ports serve as the communication interface between the ECU microcontroller (MCU) and the vehicle's electrical system. These ports allow the MCU to monitor engine sensor data and control various actuators required for engine management.

## Functional Overview

The MCU utilizes I/O ports to translate physical electrical signals into digital data for processing, and conversely, to translate digital commands into physical signals to drive engine components.

### Input Signals
Inputs are categorized by the type of signal they provide to the MCU:

*   **Analog Inputs:** Signals that vary continuously, such as those from the Throttle Position Sensor (TPS) or Coolant Temperature Sensor (ECT). These are processed via an Analog-to-Digital Converter (ADC) internal to the MCU.
*   **Digital/Discrete Inputs:** Binary signals representing an "on" or "off" state, such as the A/C switch or neutral safety switch.
*   **Frequency/Pulse Inputs:** Signals that provide data based on pulse frequency or duration, such as the Crankshaft Position (CKP) sensor or Vehicle Speed Sensor (VSS).

### Output Signals
Outputs are used to drive actuators based on the MCU's calculated logic:

*   **Digital Outputs:** Used for simple switching operations, such as activating the Main Relay or the A/C compressor clutch.
*   **Pulse Width Modulation (PWM):** Used for precise control of components like fuel injectors, the Idle Air Control (IAC) valve, or VTEC solenoids.

> [!IMPORTANT]
> Most MCU I/O pins operate at 5V logic levels. Connecting these pins directly to 12V vehicle power will result in permanent damage to the microcontroller.

## Signal Conditioning
Because raw automotive electrical signals are often noisy or exceed the voltage tolerances of the MCU, they must pass through conditioning circuits before reaching the I/O ports:

1.  **Voltage Dividers:** Used to scale down sensor voltages (e.g., 12V to 5V).
2.  **Low-Pass Filters:** Used to remove high-frequency electrical noise from sensor signals.
3.  **Drivers/Transistors:** Used to amplify the low-current signal from the MCU to drive high-current components like fuel injectors or ignition coils.

{{> resistor-color-codes }}