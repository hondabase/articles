---
summary: 'Technical overview and troubleshooting guide for the legacy EPROMer5 parallel-port device programmer used for 27C256 and AT29C256 chips.'
tags: [hardware, reference, eprom, tuning]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
---

# EPROMer5 Device Programmer Technical Guide

The EPROMer5 is a legacy parallel-port (LPT) based device programmer. While modern USB programmers have largely superseded it, the EPROMer5 remains a functional tool for programming `27C256` and `AT29C256` chips.

## 1. Chip Support
The EPROMer5 supports the following memory ICs:

* **27C256:** Natively supports standard 32 KB EPROMs (e.g., AMD, TI, or Intel 27C256).
* **AT29C256:** Supports Atmel electrically erasable EEPROMs via software revisions.

## 2. Troubleshooting and Configuration

Due to the reliance on legacy parallel port communication and DIY assembly, users may encounter initialization or verification errors.

### Solder Joint Verification
If the device fails to identify chips or reports verification errors, inspect the PCB:

* **Visual Inspection:** Use magnification to inspect all surface-mount device (SMD) IC solder joints.
* **Reflow:** Reheat suspicious joints using a fine chisel tip and fresh flux to ensure electrical continuity.

### Parallel Port Timing
Parallel port communication is sensitive to host CPU clock speeds and bus latency.

> [!TIP]
> When using older hardware (e.g., 600 MHz laptops), manually adjust the write timing in the programmer software. Setting the burn speed delay to **13** or higher is recommended to prevent data buffer overflow errors when writing to UV EPROMs.

> [!NOTE]
> Flash memory, such as the Atmel `29C256`, utilizes internal page buffers and is generally less sensitive to parallel port timing variations than standard `27C256` EPROMs.