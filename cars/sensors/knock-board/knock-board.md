---
summary: 'Technical overview of the Honda OBD1 ECU knock sensor processing daughterboard, its limitations in high-performance engines, and software bypass options.'
tags: [ecu, sensor, hardware, knock-sensor]
applies_to:
  obd: [1]
  models: [civic, del-sol, integra]
  chassis: [dc2, eg, eh]
complexity: advanced
---

# Honda OBD1 ECU Knock Sensor Daughterboard

The knock board is a vertical daughterboard mounted in the top-right corner of DOHC VTEC OBD1 Honda ECUs (such as the P30 and P72). It functions as a dedicated analog signal processing module, filtering and interpreting acoustic telemetry from the engine block's knock sensor.

## 1. Operational Theory

The factory knock sensor is a single-wire, non-resonant piezoelectric sensor that acts as a microphone to capture structural vibrations from the engine block.

* **Acoustic Filtering:** The knock board utilizes bandpass filtering circuits calibrated to the specific resonant frequency of detonation for the engine bore (e.g., ~7 kHz for B-series engines).
* **MCU Signaling:** When the filtered signal amplitude exceeds a predetermined threshold at a specific crank angle, the knock board signals the main MCU. The ECU then retards ignition timing to mitigate pre-ignition and detonation.

## 2. Limitations in High-Performance Applications

The OEM knock board is designed for stock, naturally aspirated engines. It often fails to perform reliably in modified environments:

* **Mechanical Noise:** Engines with forged pistons require larger piston-to-wall clearances, which increase mechanical noise (piston slap). The knock board often misinterprets this noise as detonation, causing the ECU to pull ignition timing unnecessarily.
* **Forced Induction:** Turbocharged or supercharged engines generate higher combustion noise and harmonic vibrations. The factory knock board is not calibrated for these frequencies, rendering it unreliable for detecting actual knock under boost.

## 3. Disabling the Knock Sensor

In aftermarket tuning, it is standard practice to disable the knock sensor feedback loop to prevent false timing retardation.

* **Software Bypass:** Tuning suites allow for the disabling of the knock sensor check routine within the ROM code.
* **Physical Removal:** Once disabled in the software, the ECU ignores the knock board. The daughterboard can be desoldered and removed from the ECU without triggering a **Code 23 (Knock Sensor)**.

::: widget error-codes :::

## 4. Hardware Patents

The OBD1 P72 and P30 knock boards reference several semiconductor and data-processing patents. These patents reflect the shared silicon fabrication technologies of the early 1990s:

| Patent Number | Description |
| :--- | :--- |
| US 4,825,364 | Monolithic data processor with memory refresh |
| US 4,942,561 | Delay time measuring device |
| US 4,896,260 | Data processor having integrated circuit memory refresh |
| US 4,829,419 | Microcomputer control of machines |
| US 4,954,951 | System and method for increasing memory performance |
| US 4,686,622 | Computer system architecture using serial communication |

> [!WARNING]
> Disabling the knock sensor removes the ECU's ability to automatically protect the engine from detonation. Ensure your ignition maps are professionally tuned and verified on a dyno before disabling this safety feature.