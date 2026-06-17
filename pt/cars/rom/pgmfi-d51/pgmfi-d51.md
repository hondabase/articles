yaml
---
summary: 'D51 is a modified disassembler supporting the A5 instruction specific to Oki 8XC154 MCUs used in Honda ECUs. Available for Windows and Linux with full source code.'
tags:
  - ecu
  - disassembler
  - rom
  - mcu
  - oki-8xc154
  - tuning
  - reference
applies_to:
  obd: [0, 1, 2]
complexity: advanced
---

# D51 Disassembler for Oki 8XC154 MCUs

D51 is a modified disassembler designed to support the A5 instruction, which is unique to Oki 8XC154 microcontrollers found in Honda engine control units. Binary releases are available for both Windows and Linux platforms, with complete source code provided for compilation and modification.

## Overview

The D51 disassembler extends the original `dasm` tool to properly handle instruction set peculiarities of the Oki 8XC154 MCU architecture. This makes it essential for ROM analysis and ECU tuning work on compatible Honda vehicles.

## Downloads and Resources

| File | Type | Size | Date | Author | Description |
|:---|:---|:---|:---|:---|:---|
| [D51_w32.zip](D51_w32.zip) | Binary | 33 KB | 2004-03-05 | blundar | Win32 executable compiled in Visual C++ |
| [D51_W32_Source.zip](D51_W32_Source.zip) | Source | 39 KB | 2004-03-05 | blundar | Visual C++ source code and project files |
| [d51v3.12-linux.zip](d51v3.12-linux.zip) | Source/Binary | 476 KB | 2004-03-05 | blundar | Linux source code and compiled binaries |
| [91.ctl](91.ctl) | Control File | 85 B | 2004-03-05 | blundar | Control file example for 1991 PM6 ECU |

## Usage

> [!TIP]
> Refer to the command-line parameters or source code documentation for detailed usage instructions. Each binary distribution includes help documentation.

```