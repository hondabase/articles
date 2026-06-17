---
summary: 'A comprehensive guide to the hardware and software fundamentals of socketing and chipping OBD0 and OBD1 Honda ECUs.'
tags: [ecu, chipping, tuning, obd0, obd1, soldering]
applies_to:
  engines: [B-Series, D-Series]
  ecus: [P28, P30, PM6, PM7, PR4, PR3, PW0]
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra]
  chassis: [da, dc2, ef, eg, eh, ek]
complexity: advanced
---

# Introduction to ECU Chipping

Modern engine management systems provide precise control over fuel and ignition timing, allowing for significant performance gains beyond factory conservative baselines. This guide covers the fundamentals of modifying Honda ECU hardware to accept custom tuning programs.

> [!WARNING]
> Tuning is a high-risk activity. Improper fuel or timing adjustments can cause catastrophic engine failure in seconds. Always use professional tools such as a load-bearing dyno, wideband O2 sensors, and EGT probes.

## Tuning Methodology
Factory ECUs operate in two primary modes:
* **Closed Loop:** Monitors engine sensors to maintain optimal fuel economy and emissions.
* **Open Loop:** Utilizes pre-defined fuel and timing tables, typically engaged at wide-open throttle (WOT).

Performance tuning involves modifying these open-loop tables. While "performance chips" often provide generic, unsafe maps, true tuning involves iterative adjustments based on objective data logging.

## Software and ROM Editors
While raw hex editing is possible, ROM editors provide a graphical interface for modifying fuel and ignition maps.

| Editor | OBD Support | Notes |
| :--- | :--- | :--- |
| **Ghettodyne** | OBD0 | Legacy; limited support. |
| **Turboedit** | OBD0 | Active development for PM6/PM7 codebases. |
| **BRE** | OBD0 | Specialized for VTEC ECUs (PR3/PW0). |
| **Uberdata** | OBD1 | Early support for P72/P75; includes boost support. |
| **Crome** | OBD1 | Scriptable editor; supports PGMFI Real Time Programming. |

## Hardware Requirements
To modify an ECU, you must be able to program EPROMs and perform high-quality soldering on circuit boards.

### Essential Tools
* **ROM Burner:** A device capable of programming 27C256 EPROMs.
* **Soldering Station:** A temperature-controlled iron is required.
* **Desoldering Station:** A vacuum-assisted desoldering tool is highly recommended to prevent damage to PCB traces and pads.
* **Socketing:** Always use high-quality machined-pin sockets for the EPROM.

## ECU Chipping Procedures

### OBD0 ECU Chipping
Many 90-91 OBD0 ECUs (PM6, PM7, PR4) feature external EPROMs and are straightforward to socket. 
1. Carefully remove the original ROM.
2. Clean the through-holes of all solder.
3. Install a 28-pin socket.
4. Insert the newly programmed EPROM.

> [!CAUTION]
> Some 88-89 OBD0 ECUs do not have external EPROMs. These require complex modifications beyond standard socketing.

### OBD1 ECU Chipping
All 92-95 Honda ECUs can be chipped to accept external EPROMs.

1. **Preparation:** Open the ECU case and locate the area designated for the ROM (often outlined in white on the PCB).
2. **Component Installation:**
   * **74HC373:** Install the logic chip.
   * **R54:** Install a 1k to 1.2k resistor.
   * **C51/C52:** Install 0.1µf ceramic disc capacitors.
   * **Socket:** Install a 28-pin machined socket at the 27256 location.
3. **Enable:** Connect the `J1` jumper to enable the external ROM.

```carousel
![P28 PCB Layout](p28_board.jpg)
*The red outlined area indicates the components required for chipping.*
<!-- slide -->
![Chipped P28](p28_done.jpg)
*A fully socketed P28 ECU with the 74HC373 and ROM socket installed.*
```

## Troubleshooting
If the vehicle fails to start or exhibits a continuous Check Engine Light (CEL):
* **Bad Connections:** Verify all solder joints for cold joints or bridges.
* **Checksum Errors:** Ensure the ROM image has been correctly processed by the editor's checksum routine.
* **Hardware Failure:** If the ECU runs poorly, revert to a known-stock program to isolate whether the issue is hardware-related or a result of the custom tune.