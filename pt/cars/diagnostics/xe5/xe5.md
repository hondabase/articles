---
summary: 'Technical overview of the Mugen XE5 ECU, a race-spec variant derived from the PM7 platform designed for the ZC engine.'
tags: [ecu, mugen, zc, rom, tuning]
applies_to:
  models: ['88-91 Civic/CRX']
  chassis: [EF]
complexity: intermediate
---

# Mugen XE5 ECU Technical Reference

The XE5 ECU is a specialized race-spec unit developed for the Mugen ZC engine platform (circa 1988–1991). It is derived from the PM7-0330 hardware architecture.

> [!IMPORTANT]
> The XE5 is a dedicated "race-only" calibration. It lacks support for an O2 sensor and disables the majority of standard factory sensor diagnostic checks.

## Hardware Overview

The XE5 utilizes the PM7-0330 PCB layout. Because it is designed for closed-course competition, it omits the circuitry and logic required for closed-loop fuel control.

### Component Documentation

The following images detail the physical configuration of the XE5 unit:

```carousel
![Exterior view of the XE5 ECU](XE5ECU.jpg)
*Exterior housing of the Mugen XE5 ECU*
<!-- slide -->
![Internal PCB view of the XE5 ECU](XE5Inside.jpg)
*Internal view of the PM7-based XE5 circuit board*
```

## Firmware and ROM

The XE5 firmware is optimized for high-output ZC engine configurations. 

* **ROM File:** [PM7-MUG.bin](PM7-MUG.bin)

## Technical Specifications

| Feature | Specification |
| :--- | :--- |
| **Base Hardware** | PM7-0330 |
| **O2 Sensor** | Disabled / Not Supported |
| **Diagnostic Checks** | Minimal / Race-spec bypass |
| **Application** | Mugen ZC Race Platform |
