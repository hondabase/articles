---
summary: 'An overview of the Intel HEX file format, a standard ASCII-based encoding used for storing machine code and data for ECU ROM and EPROM programming.'
tags: [tuning, rom, eprom, ecu, diagnostics, reference]
complexity: beginner
---

# Intel HEX File Format Reference

An Intel HEX file is an ASCII text file used to store machine language code and constant data. Each line in an Intel HEX file represents a single hexadecimal record.

## File Structure
The format is widely used in automotive tuning and diagnostics for transferring binary data to be written into [ROM](/cars/rom/rom) or [EPROM](/cars/rom/eprom) chips.

> [!NOTE]
> Most EPROM programmers and ECU emulators natively support the Intel HEX format for flashing or real-time emulation.

### Record Composition
Each line in the file follows a specific structure consisting of hexadecimal numbers. These records contain:
* **Data:** The actual machine code or constant values.
* **Addressing:** Information regarding where the data should be placed in the memory map.
* **Checksum:** A validation byte used to ensure data integrity during the transfer process.

## Usage in ECU Tuning
When working with engine management systems, Intel HEX files serve as the bridge between compiled binary code and the physical hardware. 

* **Programming:** Used to load base maps or modified calibration data onto EPROM chips.
* **Emulation:** Used by hardware emulators to simulate the presence of a physical ROM chip, allowing for real-time tuning.
* **Diagnostics:** Used to verify the contents of an ECU's memory against known-good stock files.
