---
summary: 'Technical overview of the P1J and P1K ECU units found in 1996–2000 UK Honda Civic D14 engines, including PCB identification and modification potential.'
tags: [ecu, p1j, p1k, d14, obd1, tuning]
applies_to:
  models: [civic]
  chassis: [ek]
complexity: intermediate
---

# P1J and P1K ECU Technical Reference

The P1J and P1K ECUs are factory-equipped in 1996–2000 UK Honda Civic models featuring the D14 engine series. Despite the production years, these units utilize an OBD1 architecture.

> [!NOTE]
> While these units are physically installed in OBD2-era vehicles, the internal architecture is OBD1.

## PCB Identification
These ECUs utilize a specific board layout identified by the marking: **2PU6098-4460P1 5 A8E-A3**. 

The hardware is compatible with standard OBD1 chipping procedures. For detailed visual references of the PCB layout and component placement, refer to the [P1K ECU documentation](/cars/honda/civic/ek/tuning/p1k).

## Component Gallery

```carousel
![P1J PCB Top View](DSC00055_small.jpg)
*Top view of the P1J PCB assembly*
<!-- slide -->
![P1J PCB Bottom View](DSC00056_small.jpg)
*Bottom view of the P1J PCB assembly*
<!-- slide -->
![P1J Connector Side](DSC00057_small.jpg)
*Connector interface side of the P1J*
<!-- slide -->
![P1J Component Detail](DSC00058_small.jpg)
*Detailed view of onboard components*
<!-- slide -->
![P1J Housing](DSC00054_small.jpg)
*External view of the P1J ECU housing*
```

## VTEC Conversion
The P1J and P1K boards are candidates for VTEC conversion. While the board layout supports the necessary modifications common to OBD1 platforms, VTEC functionality on these specific variants remains unverified. 

> [!CAUTION]
> VTEC conversion on P1J/P1K units is experimental. Ensure all traces are verified against standard OBD1 VTEC schematics before attempting operation.
