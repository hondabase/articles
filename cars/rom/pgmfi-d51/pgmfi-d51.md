---
summary: 'Technical reference for the D51 disassembler, modified to support the A5 instruction set specific to Oki 8XC154 microcontrollers.'
tags: [ecu, disassembly, mcu, oki, tuning]
applies_to:
  models: [civic, crx]
  chassis: [ef]
complexity: advanced
---

# D51 Disassembler for Oki 8XC154 MCUs

The D51 disassembler is a specialized tool modified to support the unique A5 instruction set found on Oki 8XC154 microcontrollers. 

> [!IMPORTANT]
> This tool is intended for advanced users performing reverse engineering or custom ROM development on supported Honda ECU hardware.

## Usage and Compatibility

The tool is available in both Linux and Windows binary formats. To operate the disassembler, execute the binary via the command line interface.

*   **Linux Binaries:** Compiled for standard Linux distributions.
*   **Windows Binaries:** Compiled for Windows environments.

### Command Line Interface
To view available flags, input parameters, and configuration options, execute the binary with the help argument:

```bash
./d51 --help
```

## Technical Specifications

The primary modification to the standard D51 codebase is the implementation of the A5 instruction opcode, which is non-standard for generic 8051-based disassemblers but required for proper decoding of Oki 8XC154 firmware.

> [!TIP]
> Always verify the checksum of your ROM file before and after disassembly to ensure data integrity during the conversion process.
