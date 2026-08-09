---
title: 'Honda D, B, and H-Series Distributor Trigger Decoding (24+1, CYP/TDC/CKP)'
summary: 'Technical breakdown of Honda 3-VR sensor distributor triggers (24+1, 4+1, 1-tooth CYP), VR polarity mapping, timing drift fixes, and standalone ECU configuration.'
tags: [trigger, distributor, obd1, obd2, vr-sensor, timing, rusefi, standalone]
applies_to:
  models: [civic, integra, accord, prelude]
  chassis: [eg, ek, dc2, cb7, bb]
  engines: [d-series, b-series, h-series]
complexity: advanced
sources:
  - title: 'Honda D/B/H trigger patterns (Most Distributor Hondas)'
    url: 'https://rusefi.com/forum/viewtopic.php?t=2013'
    adapted: true
    author: blundar
  - title: 'Honda OBD1 CKP/CYP/TDC simulate signals'
    url: 'https://rusefi.com/forum/viewtopic.php?t=1903'
    adapted: true
    author: stefanst
  - title: 'Honda OBD1 Trigger Settings/Timing Drift Issue'
    url: 'https://rusefi.com/forum/viewtopic.php?t=2759'
    adapted: true
    author: ZayTuned
---

# Honda D, B, and H-Series Distributor Trigger Decoding (24+1, CYP/TDC/CKP)

## Overview

Factory Honda D-series, B-series, and H-series distributor engines (OBD0, OBD1, and OBD2) utilize a unique three-sensor Variable Reluctance (VR) trigger system housed inside the distributor housing. Converting these platforms to modern standalone engine management requires an understanding of signal decoding, sensor polarity, and rotor arm alignment.

> \[!NOTE\] Unlike modern engines with magnetic crank wheels on the harmonic balancer, Honda distributor triggers spin at half engine speed (camshaft speed). Sensor frequency is double per engine cycle.

---

## 1. Internal Distributor VR Sensor Architecture

Inside standard Honda distributor housings (TD-41U, TD-42U, TD-44U, TD-68U, etc.), three VR sensors monitor separate reluctor wheels:

| Sensor Name | Function | Tooth Count | Pulses per Engine Rev | Signal Purpose |
| --- | --- | --- | --- | --- |
| **CKP** (Crankshaft Position) | Engine Speed & Main Crank Angle | 24 teeth | 12 pulses / rev | Primary RPM calculation & high-resolution angle tracking |
| **TDC** (Top Dead Center) | Cylinder Pair Identification | 4 teeth | 2 pulses / rev | Identifies 1/4 and 2/3 cylinder pairs at TDC |
| **CYP** (Cylinder Position) | Sequential Phase Synchronization | 1 tooth | 0.5 pulses / rev | Identifies Cylinder 1 compression stroke for sequential injection/ignition |

---

## 2. Trigger Decoding Modes in Standalone Software

When configuring standalone ECUs (such as rusEFI, Megasquirt, Haltech, or Link) for Honda distributors, two primary decoding modes are used:

### 2.1 The 24+1 Trigger Mode (Recommended)

- **Crank Sensor:** 24-tooth CKP signal fed to primary trigger input (`Trigger #1`).
- **Cam Sync:** 1-tooth CYP signal fed to secondary cam sync input (`Trigger #2`).
- **TDC Sensor:** Disconnected or unassigned (not needed when 24-tooth CKP is decoded with CYP sync).
- **Result:** Provides precise 30-degree crankshaft angle resolution with full sequential fuel and ignition capability.

### 2.2 The 4+1 Fallback Mode

- Uses the 4-tooth TDC signal and 1-tooth CYP signal.
- Provides 180-degree crankshaft resolution. Suitable for batch fire fuel or distributor ignition, but inferior to 24+1 for high-RPM timing accuracy.

---

## 3. Resolving Timing Drift & VR Polarity Issues

### VR Sensor Wire Polarity

Variable Reluctance sensors generate an AC sine wave. Reversing positive (+) and negative (-) wires shifts the zero-crossing slope from positive to negative, introducing up to 10-15 degrees of dynamic ignition timing drift as RPM increases.

> \[!WARNING\] Always verify ignition timing with a physical timing light across the 1,000 RPM to 6,000 RPM range. If timing drifts significantly under revs, reverse the CKP sensor wire polarity in your engine harness.

### Grounding & Noise Suppression

- The distributor housing must maintain a low-resistance ground connection to the cylinder head.
- Shielded twisted-pair wiring is mandatory for CKP, TDC, and CYP signal lines to prevent high-voltage ignition interference.

---

## 4. Summary Verification Checklist

1. Confirm 24-tooth CKP wired to primary VR input.
2. Confirm 1-tooth CYP wired to secondary VR/Cam input.
3. Lock timing in software to 16 degrees BTDC (factory red mark on D/B/H crank pulleys).
4. Verify with timing light at idle and revs; adjust trigger offset angle until mechanical timing matches software target.

---

## 5. Downloads & Reference Files

- [Bomarc P28 ECU Internal Schematics (PDF)](topic_2013_bomarc-services-p28.pdf)
