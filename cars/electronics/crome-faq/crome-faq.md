---
summary: 'Frequently asked questions about Crome, a popular ROM editing and tuning software for OBD1 Honda ECUs.'
applies_to:
  obd: [1]
complexity: intermediate
tags:
  - tuning
  - rom
  - software
---

# Crome ROM Tuning FAQ

Crome is a popular, cost-effective ROM tuning and editing software suite designed for OBD1 Honda Engine Control Units (ECUs). It allows enthusiasts to modify fueling tables, ignition timing maps, and configure advanced features on socketed ECUs. This FAQ covers common setup questions, hardware requirements, and troubleshooting tips for tuning with Crome.

## General Questions

### Why is Crome password protected?
Crome is free software made possible by the hard work of many contributors. To ensure users are aware of the software's origin and contributors, the creator (John Cui) password-protected the installer. 

### How do I find the Crome installer password?
The password is simple to find with a small amount of research. Finding it serves as a basic exercise for beginners to learn more about the Crome ecosystem and show appreciation for the years of development behind it.

## Hardware Requirements

### What hardware is required to start tuning with Crome?
To get started tuning and datalogging with Crome, you will need the following hardware:

- **Tuning Laptop:** A computer running Windows (ideally with a decent processor and RAM). A slow laptop will bottleneck datalogging response times.
- **Wideband O2 Sensor:** A wideband oxygen sensor with a linear analog output voltage (e.g., Innovate, PLX, or TechEdge) is critical if you want to datalog air-fuel ratios through the ECU.
- **EEPROM Chip Burner:** A hardware programmer (such as the Moates BURN1/BURN2 or a Willem programmer) to write files to your ROM chips. Note that Willem programmers usually require a parallel (LPT) port, which most modern laptops lack.
- **Hardware Emulator (Optional):** An emulator like the Moates Ostrich allows real-time tuning (RTT) by uploading maps directly to the ECU without constantly burning chips.
- **Datalogging Cable:** A USB-to-TTL serial adapter cable to connect the ECU's 4-pin datalogging header (`CN2`) to the laptop. Moates and other tuning vendors offer plug-and-play USB cables.
- **ECU Chipping Kit:** To prepare an OBD1 ECU for socketing, you need:
  - 28-pin machined DIP socket
  - 28-pin ZIF socket
  - 4-pin `CN2` datalogging header
  - Two 0.1µF ceramic disc capacitors
  - 1k Ohm resistor
  - `74HC373` latch chip

For a step-by-step guide to installing hardware options, see the [guide on how to add extra features in Crome](/cars/electronics/howto-add-extra-features-in-crome).

## ROM Compatibility & Plugin Setup

### Which stock ROM should I start with for ITB or Boost plugins?
You must start with a stock JDM P30 "203" ROM or any ROM derived from it (such as a JDM P08 "237" ROM). 

### Where can I download stock Honda ROM files?
You can find stock ROMs and definitions in the [ECU Definition Codes library](/cars/electronics/ecu-definition-codes).

### Why does my ECU show a solid CEL after editing a stock ROM?
If you get a solid Check Engine Light (CEL) after burning a new ROM, verify that you have:
1. Removed the checksum routine from the ROM in Crome.
2. Disabled any hardware features not physically present in your ECU (such as the knock sensor, purge cut-off, barometric sensor, or injector test circuit).

### Datalogging fails after installing the datalogging plugin. What should I check?
Ensure you have disabled the checksum routine in your ROM, and that you have selected the correct COM port in the Crome settings.

### Why is my datalogging sample rate very slow?
Datalogging speed is highly dependent on your PC's hardware capabilities and the quality of the RS232-to-TTL serial cable. See the [serial communication troubleshooting guide](/cars/electronics/serial-communication) for more information.

### The Crome plugins do not work with my P28 ROM. What should I do?
Most Crome plugins are built to support the JDM P30 codebase. If you are tuning a P28 ECU, export your tables from your P28 ROM and import them into a stock JDM P30 (203) ROM:
1. Open your P28 ROM in Crome.
2. Go to **File > Export Tables** and save the table file.
3. Open a stock JDM P30 (203) ROM as a new file.
4. Go to **File > Import Tables** and import the P28 table file you saved.
5. Disable the knock sensor and speed limiter in the options menu (since USDM P28 ECUs do not have knock sensor circuitry).
6. Save and write this new P30 ROM to your chip.

Alternatively, you can use the "237" code from the JDM P08 (SOHC VTEC D15B), which is a single-cam version of the P30 code. You can download this ROM from the [ECU Definition Codes library](/cars/electronics/ecu-definition-codes).

### Why can't I edit certain map headings in Crome?
In Crome, you cannot edit the column headings for the first and last columns, or the row headings for the first and last rows in a ROM. Attempting to do so will cause unpredictable map scaling errors.

## EEPROM Chip Programming

### How do I program or read an EEPROM using the Moates BURN1 in Crome?
1. Go to **Settings** and select **Ostrich/BURN1** as your Real-Time Tuning (RTP) hardware.
2. Crome automatically detects whether an Ostrich or a BURN1 is connected.
3. To burn a ROM, connect the BURN1 and click **Put**.
4. To read a chip, click **Get**.

### How do I specify the chip type (e.g., 27SF512) for the Moates BURN1?
Select **Ostrich/BURN1** as your RTP hardware under **Settings**. A checkbox will appear on the right side of the screen allowing you to select 27SF512 chips.
