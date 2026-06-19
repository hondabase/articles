---
summary: 'Troubleshooting guide for Honda OBD1 ECU datalogging, covering hardware continuity, ROM configuration, and serial communication settings.'
tags: [datalogging, diagnostics, serial, ecu, obd1]
applies_to:
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eh]
complexity: advanced
---

# Troubleshooting Honda ECU Datalogging (CN2 Debugging)

Datalogging enables real-time monitoring of engine variables. If your tuning software fails to establish a live connection with the ECU, follow this troubleshooting checklist to isolate hardware, software, or configuration issues.

## 1. Hardware and Board Continuity Checks

Before adjusting software settings, use a digital multimeter in continuity mode to verify the electrical traces surrounding the [CN2 datalogging header](/cars/tuning/serial-communication) on the ECU circuit board.

*   **Solder Bridges:** Inspect the CN2 header solder pads. Ensure there are no microscopic solder bridges or flux residues connecting adjacent pins.
*   **Ground Connectivity:** Verify that CN2 **Pin 4** (GND) has solid, zero-resistance continuity to the main ECU metal chassis and power ground pins (A26/B2).
*   **RX Line Trace:** Verify continuity from CN2 **Pin 2** (RX) to the main processor:
    *   **Surface-mount (JDM):** Trace to **Pin 42**.
    *   **DIP (USDM):** Trace to **Pin 39**.
*   **TX Line Trace:** Verify continuity from CN2 **Pin 1** (TX) to **Pin 6** of **IC19** (the surface-mount TX line buffer chip).

> [!IMPORTANT]
> The most common wiring error is connecting TX-to-TX and RX-to-RX. Ensure your USB-to-TTL adapter's RXD wire is connected to CN2 Pin 1 (TX), and the TXD wire is connected to CN2 Pin 2 (RX).

## 2. ROM Calibration and Firmware Settings

If hardware traces pass continuity tests, verify the configuration of the ROM binary file.

### Disable the Checksum Routine
A stock ECU ROM calculates a checksum to verify code integrity. Custom datalogging code will cause this checksum to fail, triggering a solid Check Engine Light (CEL) and locking the serial interface.
*   **Action:** Open your ROM in your editor and select **Remove Checksum Routine** before burning the chip.

### Install a Datalogging Protocol Plugin
Stock ROM code does not output serial diagnostic data on the CN2 header.
*   **Action:** Install a protocol plugin (e.g., Crome's *Quick Datalogger*). This inserts serial transmit loops into the ECU's main runtime program.
*   **Baud Rate Matching:** Verify that your software's connection settings match the plugin protocol's baud rate (typically 38,400 bps).

## 3. Driver and Virtual COM Port Optimization

Configure your operating system to ensure stable serial communication:

*   **Adjust Latency Timer:** In Windows **Device Manager**, locate your USB-to-Serial port under *Ports (COM & LPT)*. Navigate to **Properties > Port Settings > Advanced** and change the **Latency Timer** from 16 ms to **1 ms**.
*   **Verify COM Port Assignment:** Confirm the tuning software is pointed to the correct COM port. If the OS assigns a high port number (e.g., COM18), manually reassign it to a lower port (COM1–COM4) in the Device Manager.

## 4. Bench Testing the ECU

Use a bench test harness to isolate the ECU from vehicle wiring.

### OBD1 Bench Test Pinout

| Connection Type | ECU Pin Number | Description |
| :--- | :---: | :--- |
| **+12V Constant** | D1 | Back-up power supply |
| **+12V Switched** | A25 & B1 | Main ignition power inputs |
| **Chassis Ground** | A26 & B2 | Main power grounds |
| **Diagnostic (SCS)** | D4 | Ground to enable diagnostic flash codes |
| **CEL Output** | A11 | Connect LED + 1k Ohm resistor to +12V |

> [!TIP]
> Once powered on the bench, connect your USB-to-TTL converter to the CN2 header. Even without sensors, the software should show active, updating data, confirming the serial interface is functional.

## Related Articles

*   [CN2 Serial Port Pinouts](/cars/tuning/serial-communication)
*   [Configuring USB-to-TTL Adapters](/cars/tuning/second-gen-usb-to-serial-converter)
*   [How to Interpret Sensor Diagnostics](/cars/diagnostics/diagnostic-trouble-codes)
