---
summary: 'Frequently asked questions about Crome, a popular ROM editing and tuning software for OBD1 Honda ECUs.'
tags: [tuning, software, obd1]
applies_to:
  models: [civic, del-sol]
  chassis: [ef, eg, eg-eh]
complexity: intermediate
---

# Crome ROM Tuning FAQ

Crome is a ROM tuning and editing software suite designed for OBD1 Honda Engine Control Units (ECUs). It allows for the modification of fueling tables, ignition timing maps, and the configuration of advanced features on socketed ECUs.

## General Questions

### Why is Crome password protected?
Crome is free software developed by community contributors. To ensure users are aware of the software's origin and the contributors involved, the installer is password-protected.

### How do I find the Crome installer password?
The password is found through community research. This serves as a basic exercise for users to learn about the Crome ecosystem and the development history of the software.

## Hardware Requirements

To begin tuning and datalogging with Crome, the following hardware is required:

*   **Tuning Laptop:** A Windows-based computer. High-performance hardware is recommended to prevent latency during datalogging.
*   **Wideband O2 Sensor:** A sensor with a linear analog output (e.g., Innovate, PLX, or TechEdge) is required for accurate air-fuel ratio datalogging.
*   **EEPROM Chip Burner:** A programmer (e.g., Moates BURN2) to write files to ROM chips.
*   **Hardware Emulator (Optional):** An emulator (e.g., Moates Ostrich) allows for Real-Time Tuning (RTT) by uploading maps directly to the ECU.
*   **Datalogging Cable:** A USB-to-TTL serial adapter cable to connect the ECU's 4-pin datalogging header (`CN2`) to the laptop.
*   **ECU Chipping Kit:** To prepare an OBD1 ECU for socketing, the following components are required:
    *   28-pin machined DIP socket
    *   28-pin ZIF socket
    *   4-pin `CN2` datalogging header
    *   Two 0.1µF ceramic disc capacitors
    *   1k Ohm resistor
    *   `74HC373` latch chip

> [!TIP]
> For a step-by-step guide to installing hardware, see the [guide on how to add extra features in Crome](/cars/tuning/howto-add-extra-features-in-crome).

## ROM Compatibility & Plugin Setup

### Which stock ROM should I start with for ITB or Boost plugins?
You must start with a stock JDM P30 "203" ROM or any ROM derived from it, such as a JDM P08 "237" ROM.

### Where can I download stock Honda ROM files?
Stock ROMs and definitions are available in the [ECU Definition Codes library](/cars/ecu/ecu-definition-codes).

### Why does my ECU show a solid CEL after editing a stock ROM?
If a solid Check Engine Light (CEL) appears after burning a new ROM, verify the following:
1. The checksum routine has been removed from the ROM in Crome.
2. Any hardware features not physically present in your ECU (e.g., knock sensor, purge cut-off, barometric sensor, or injector test circuit) have been disabled.

### Datalogging fails after installing the datalogging plugin. What should I check?
Ensure the checksum routine is disabled in your ROM and that the correct COM port is selected in the Crome settings.

### Why is my datalogging sample rate very slow?
Datalogging speed is dependent on PC hardware and the quality of the RS232-to-TTL serial cable. Refer to the [serial communication troubleshooting guide](/cars/tuning/serial-communication) for optimization steps.

### The Crome plugins do not work with my P28 ROM. What should I do?
Most Crome plugins are built for the JDM P30 codebase. If using a P28 ECU, follow these steps:
1. Open your P28 ROM in Crome.
2. Go to **File > Export Tables** and save the table file.
3. Open a stock JDM P30 (203) ROM.
4. Go to **File > Import Tables** and import the saved table file.
5. Disable the knock sensor and speed limiter in the options menu.
6. Save and write the new P30 ROM to your chip.

Alternatively, use the "237" code from the JDM P08 (SOHC VTEC D15B), which is a single-cam version of the P30 code.

### Why can't I edit certain map headings in Crome?
You cannot edit the column headings for the first and last columns, or the row headings for the first and last rows. Attempting to do so will cause map scaling errors.

## EEPROM Chip Programming

### How do I program or read an EEPROM using the Moates BURN1 in Crome?
1. Go to **Settings** and select **Ostrich/BURN1** as your Real-Time Tuning (RTP) hardware.
2. Crome will automatically detect the connected hardware.
3. To burn a ROM, connect the BURN1 and click **Put**.
4. To read a chip, click **Get**.

### How do I specify the chip type (e.g., 27SF512) for the Moates BURN1?
Select **Ostrich/BURN1** as your RTP hardware under **Settings**. A checkbox will appear on the right side of the interface allowing you to select 27SF512 chips.
