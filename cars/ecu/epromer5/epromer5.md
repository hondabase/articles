---
summary: 'Technical overview and troubleshooting guide for the legacy EPROMer5 parallel-port device programmer used for 27C256 and AT29C256 chips.'
tags: [hardware, reference]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: Epromer5
    url: /pgmfi/wiki/library/epromer5
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# EPROMer5 Device Programmer Guide

The **EPROMer5** is a legacy parallel-port (LPT) based DIY ROM burner that was widely popular in the early 2000s among GM ECM and Honda ECU tuning communities. While modern USB programmers (such as the XGecu TL866/T48) have largely superseded it, the EPROMer5 remains a robust, low-cost tool for burning `27C256` and `AT29C256` chips.

---

## 1. Chip Support & Capabilities

*   **27C256 Support:** Natively supports standard 32 KB EPROMs (e.g., AMD, TI, or Intel 27C256).
*   **AT29C256 Support:** Later revisions and software updates added support for the popular electrically erasable Atmel AT29C256 EEPROM.

---

## 2. Troubleshooting & Configuration Tips

Due to its DIY nature and reliance on legacy parallel port communication, builders often encountered specific setup issues:

### Solder Joint Verification
If the device fails to identify chips, throws random verification errors, or fails to initialize, inspect the circuit board. Many kits were shipped partially assembled or built by hand:
*   Use a magnifying glass to check for cold solder joints on the surface-mount device (SMD) ICs.
*   Reheat any suspicious joints with a fine chisel soldering tip and apply fresh flux to ensure a solid electrical connection.

### Parallel Port Timing (Burn Speed)
Parallel ports are sensitive to CPU timing and bus speeds. 
*   **Timing Adjustments:** When running the programmer software on older PC systems (such as a 600 MHz LPT-equipped laptop), you may need to manually restrict the write timing speed in the burner settings. Setting the burn speed delay to **"13"** (or higher) is often required to prevent data buffer overflow errors when writing to `27C256` UV EPROMs.
*   **Flash Memory Advantage:** The Atmel `29C256` flash EEPROMs handle write operations via internal page buffers, which makes them less sensitive to parallel port timing. They can typically be programmed at any speed setting without timing-induced errors.
