---
summary: 'Technical specifications, software configuration, and chip settings for the EETools ChipMax USB device programmer.'
tags: [hardware, reference]
applies_to:
  obd: [0, 1, 2]
  chassis: [ef]
  models: {}
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Chip Max'
    url: /pgmfi/wiki/library/chip-max
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# EETools ChipMax Device Programmer

The **ChipMax** (manufactured by [EE Tools](http://www.eetools.com)) is an entry-level professional universal device programmer. Originally released with a parallel port interface, newer models utilize USB connectivity (such as the ChipMax2). 

It is a popular choice for burning EPROMs (like the `27C256`) and EEPROMs (like the [28C256](/cars/ecu/28c256)) used in OBD0 and OBD1 Honda ECUs.

## Key Features

*   **Universal Device Support:** Features a high-quality 40-pin Zero Insertion Force (ZIF) socket. It supports a wide range of devices including EPROMs, EEPROMs, Flash memory, and microcontrollers.
*   **Reliable Hardware Timings:** Unlike low-cost generic burners (such as the [Willem](/cars/rom/willem) or DIY "Ghetto Burner" designs), the ChipMax features dedicated internal controllers that handle precise programming voltages and timing cycles, preventing verification failures and damaged chips.
*   **Software & Support:** EE Tools maintains regular software updates for device support. Historically, their technical support has been known to write custom device profiles upon request.

## Comparison & Usage

Compared to hobbyist-grade burners, the ChipMax is highly stable, making it a preferred option for tuners who frequently read and write ROMs. The control software allows for quick checksum verification, blank checks, and buffer editing prior to writing.
