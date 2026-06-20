---
summary: 'Detailed configuration and reprogramming guide for the UberData custom ROM code on Acura OBD1 P72 ECUs, including RAM address mappings and modification offsets.'
tags: [tuning, software, p72, uberdata, reprogramming]
applies_to:
  make: Acura
  models: ['Integra GS-R']
  ecus: [P72]
complexity: advanced
---

# Uber P72 ROM Map

The **Uber P72** is a modified factory code base derived from the [Acura OBD1 P72 ECU](/cars/sensors/p72), optimized for use with the UberData tuning suite. This guide documents the specific RAM and ROM address offsets used by UberData modifications on P72 firmware.

> [!NOTE]
> For standard Honda/Acura factory P72 address mappings, refer to the [P72 ROM Map](/cars/sensors/p72) documentation.

## RAM Address Mapping

The following table lists RAM locations used by UberData custom code in P72 ROM:

| Hex Offset | Length (Bytes) | Description | Notes |
|:---:|:---:|:---|:---|
| `645D` | 2 | UberData Alternate VTEC ERM RPM | Alternative limit configuration |
| `645F` | 2 | UberData Alternate VTEC ERM RPM | Alternative limit configuration |
| `6464` | 2 | UberData Alternate VTEC ERM RPM | Alternative limit configuration |
| `6466` | 2 | UberData Alternate VTEC ERM RPM | Alternative limit configuration |

> [!IMPORTANT]
> All offset addresses are relative to the RAM base address. Verify compatibility with your specific ROM version before applying modifications.
