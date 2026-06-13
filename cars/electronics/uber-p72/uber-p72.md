---
summary: 'Detailed walkthrough on configuring and tuning the UberData custom ROM codebase for P72 OBD1 ECUs.'
applies_to:
  brand: Acura
  ecus: [P72]
  obd: [1]
complexity: advanced
tags:
  - tuning
  - rom
  - software
---

# Uber P72 ROM Map

The **Uber P72** ROM is a modified Acura Integra GS-R [P72 OBD1 ECU](/cars/electronics/p72) factory codebase designed to work with the UberData tuning suite. 

This page documents the RAM and ROM address offsets that are specific to the UberData modifications. For factory Honda/Acura P72 addresses, refer to the standard [P72 ROM Map](/cars/electronics/p72).

## RAM Address Mapping

The table below outlines specific RAM locations used by the UberData custom code in a P72 ROM:

| Hex Offset | Length (Bytes) | Description | Notes |
| :---: | :---: | :--- | :--- |
| `645D` | 2 | UberData ERM Alternate VTEC RPM | Alternate threshold configuration |
| `645F` | 2 | UberData ERM Alternate VTEC RPM | Alternate threshold configuration |
| `6464` | 2 | UberData ERM Alternate VTEC RPM | Alternate threshold configuration |
| `6466` | 2 | UberData ERM Alternate VTEC RPM | Alternate threshold configuration |
