---
summary: 'Technical overview of the Honda OBD1 ECU knock sensor processing daughterboard, its limitations in high-performance engines, and software bypass options.'
tags: [ecu, sensor, hardware]
applies_to:
  obd: [1]
  models: [civic, del-sol, integra]
  chassis: [dc2, eg, eg-eh]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Knock Board'
    url: /pgmfi/wiki/library/knock-board
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# The Honda OBD1 ECU Knock Board

The knock board is a small vertical daughterboard mounted in the top-right corner of DOHC VTEC OBD1 Honda ECUs (such as the P30 and P72). It acts as a dedicated analog signal processing module, filtering and interpreting the acoustic telemetry from the engine block's knock sensor.

---

## 1. How It Works

The factory knock sensor is a single-wire, non-resonant piezoelectric sensor. It functions essentially as a microphone, capturing the structural vibrations of the engine block. 

* **Acoustic Filtering:** The knock board contains bandpass filtering circuits calibrated to the resonant frequency of detonation for specific engine bores (e.g., ~7 kHz for the B-series engine).

* **MCU Signaling:** When the filtered signal amplitude exceeds a predetermined threshold at a specific crank angle, the knock board signals the main MCU. The ECU then pulls ignition timing to protect the engine from pre-ignition and detonation.

---

## 2. Limitations in Tuned Engines

While the OEM knock board works well for stock, naturally aspirated engines running low-octane fuel, it has significant drawbacks in high-performance applications:

* **Mechanical Noise (Forged Internals):** High-performance engines rebuilt with forged pistons require larger piston-to-wall clearances than cast factory pistons. This creates mechanical noise (piston slap) that the knock board often misinterprets as detonation. This causes the ECU to pull ignition timing unnecessarily, reducing power.

* **Forced Induction (Boost):** Turbocharged or supercharged engines generate higher combustion noise and harmonic vibrations. The factory knock board is not calibrated for these frequencies and noise levels, making it unreliable for detecting actual knock under boost.

---

## 3. Disabling the Knock Sensor

Due to these limitations, it is common practice in aftermarket tuning to disable the knock sensor feedback loop.

* **Software Bypass:** Tuning suites (such as Hondata, Crome, or Neptune) allow you to disable the knock sensor check routine in the ROM code.

* **Physical Removal:** Once disabled in the software, the ECU ignores the knock board entirely. The physical daughterboard can be desoldered and removed from the ECU casing without triggering a **Code 23 (Knock Sensor)** Check Engine Light.

---

## 4. Hardware Patents

The OBD1 P72 and P30 knock boards are marked with several semiconductor and data-processing patents. Interestingly, several of these patents are shared with other digital devices of the early 1990s (such as Hewlett-Packard LaserJet printers), reflecting the shared silicon fabrication patents of the era:

* **US Patent 4,825,364:** Monolithic data processor with memory refresh

* **US Patent 4,942,561:** Delay time measuring device

* **US Patent 4,896,260:** Data processor having integrated circuit memory refresh

* **US Patent 4,829,419:** Microcomputer control of machines

* **US Patent 4,954,951:** System and method for increasing memory performance

* **US Patent 4,686,622:** Computer system architecture using serial communication
