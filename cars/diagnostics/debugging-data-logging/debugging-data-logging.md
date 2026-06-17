---
summary: 'Troubleshooting common Honda ECU datalogging issues, including connection drops, noise interference, and incorrect driver configurations.'
tags: [datalogging, diagnostics, serial]
applies_to:
  obd: [1]
  models: [accord, civic, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, eg, eg-eh]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Debugging Data Logging'
    url: /pgmfi/wiki/library/debugging-data-logging
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Troubleshooting Honda ECU Datalogging (`CN2` Debugging)

Datalogging enables real-time monitoring of engine variables, but connection failures are common during initial setups. If your tuning software (such as Crome, Hondata, or Neptune) fails to establish a live connection with the ECU, work through this troubleshooting checklist to isolate hardware, software, or operating system configuration issues.

---

## 1. Hardware and Board Continuity Checks

Before checking software settings, use a digital multimeter in **continuity (beep) mode** to verify the electrical traces surrounding the [CN2 datalogging header](/cars/tuning/serial-communication) on the ECU circuit board:

- **Check for Solder Bridges:** Inspect the CN2 header solder pads. Ensure there are no microscopic solder bridges or flux residues connecting adjacent pins.
- **Check Ground Connectivity:** Verify that CN2 **Pin 4** (GND) has solid, zero-resistance continuity to the main ECU metal chassis and power ground pins (pins A26/B2).
- **Trace the Receive (RX) Line:** Verify continuity from CN2 **Pin 2** (RX) to the main OKI 66207 processor:
 - On surface-mount processor boards (most JDM boards), trace to **Pin 42**.
 - On dual-inline-package (DIP) processor boards (common USDM boards), trace to **Pin 39**.
- **Trace the Transmit (TX) Line:** Verify continuity from CN2 **Pin 1** (TX) to **Pin 6** of **IC19** (the surface-mount TX line buffer chip).
- **TX/RX Signal Swap Check:** The most common wiring mistake is connecting TX-to-TX and RX-to-RX. Verify that your USB-to-TTL adapter's RXD wire is connected to Pin 1 (TX) of CN2, and the TXD wire is connected to Pin 2 (RX) of CN2.

---

## 2. ROM Calibration and Firmware Settings

If the hardware traces pass continuity tests, check the configuration of the ROM binary file burned onto your EEPROM chip:

### Disable the Checksum Routine

A stock ECU ROM constantly calculates a checksum to verify code integrity. If you load custom datalogging code on a ROM, this checksum will fail, triggering a solid Check Engine Light (CEL) and locking up the serial interface.
- **Action:** Open your ROM in your editor, go to the enhancements menu, and select **Remove Checksum Routine** before burning the chip.

### Install a Datalogging Protocol Plugin

Stock ROM code does not output serial diagnostic data on the `CN2` header by default. You must overlay a datalogging protocol plugin onto the binary file:
- **Action:** Install a protocol plugin (such as Crome's *Quick Datalogger

* plugin). This inserts serial transmit loops into the ECU's main runtime program execution.
- **Baud Rate Matching:** Verify that your software's connection settings match the plugin protocol's baud rate. For example, Crome's Quick Datalogger defaults to **38,400 bps**, while legacy protocols may run at **9,600 bps** or **115,200 bps**.

---

## 3. Driver and Virtual COM Port Optimization

If your hardware is correct and the ROM is properly configured, configure your laptop's operating system:

- **Adjust Latency Timer (Critical):** Open the Windows **Device Manager**, locate your USB-to-Serial port under *Ports (COM & LPT)*, go to **Properties > Port Settings > Advanced**, and change the **Latency Timer** from 16 ms to **1 ms**. Default latency settings cause communication timeouts and laggy datalogging updates.
- **Verify COM Port Assignment:** Confirm that your tuning software is pointed to the exact COM port number assigned by Windows (e.g. COM2). If the OS assigns a high COM port number (e.g. COM18), manually reassign it in the Device Manager properties to a lower port (COM1 to COM4) as older tuning programs cannot scan high COM ports.

---

## 4. Bench Testing the ECU

To troubleshoot the datalogging interface without dealing with car wiring, you can wire a basic bench test harness to power the ECU on your desk.

### OBD1 Bench Test Pinout

To boot up an OBD1 Honda ECU on a 12V DC power supply, make the following connections on the ECU plugs:

| Connection Type | ECU Pin Number | Description |
| :--- | :---: | :--- |
| **+12V Constant Power** | **D1** | Back-up power supply |
| **+12V Switched Power** | **A25 & B1** | Main ignition power supply inputs |
| **Chassis Ground** | **A26 & B2** | Main power grounds |
| **Diagnostic Jumper (SCS)** | **D4** | Connect this pin to ground to enable diagnostic flash codes |
| **Check Engine Light (CEL)** | **A11** | Connect an LED in series with a 1k Ohm resistor between pin A11 and +12V. The LED will illuminate to replicate the dashboard CEL. |

Once powered on the bench, connect your USB-to-TTL converter to the `CN2` header and launch your datalogger. Although the datalogger will report garbage values for missing sensors, you should see active, updating numbers on your screen, indicating that the serial interface is fully functional.

## Related Articles

- [CN2 Serial Port Pinouts](/cars/tuning/serial-communication)
- [Configuring USB-to-TTL Adapters](/cars/tuning/second-gen-usb-to-serial-converter)
- [How to Interpret Sensor Diagnostics](/cars/diagnostics/diagnostic-trouble-codes)
