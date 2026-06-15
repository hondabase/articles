---
summary: 'An educational guide explaining the hardware architecture, memory mapping, OKI 82C55 I/O expander, and 66k assembly code of OBD1 Honda ECUs.'
tags: [ecu, hardware, education]
applies_to:
  obd: [1]
  chassis: [dc2, ef, eg, eg-eh]
  models: [civic, del-sol, integra]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Doc ECU School'
    url: /pgmfi/wiki/library/doc-ecu-school
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1 Honda ECU Architecture and Memory Mapping

The OBD1 Honda ECU platform (such as the P28, P30, and P72) is built around the OKI `66207` microcontroller (66k instruction set). To manage the diverse inputs and outputs required to run an engine, the MCU utilizes a mix of direct pins, analog multiplexers, and a custom 82C55 I/O expander. 

Understanding how the ECU software interacts with these hardware elements is essential for custom ROM development and reverse engineering.

---

## 1. Hardware I/O Architecture

The ECU classifies signals based on their timing priority and signal type (analog vs. digital):

*   **Direct MCU I/O:** High-priority or highly time-sensitive signals are connected directly to the MCU. These include the engine speed (RPM) sensors (CYP, CKP, TDC), vehicle speed sensor (VSS), and injector driver control circuits.
*   **Analog Inputs:** Sensor voltages (MAP, TPS, IAT, ECT, Oxygen sensor) are routed directly to the MCU's internal analog-to-digital converter (ADC) via multiplexer ICs.
*   **82C55 I/O Expander:** Most digital switches (clutch switch, A/C request) and low-priority solenoid outputs (VTEC solenoid, A/C clutch relay, EVAP purge) are managed by a custom 44-pin Intel 82C55-compatible I/O expander chip.
*   **Input Latch:** A 20-pin logic latch IC located near the EPROM acts as an additional 8-bit digital input buffer for chassis and transmission switches.

---

## 2. Memory-Mapped Registers and RAM Buffers

Because the 82C55 is mapped as a peripheral device in the ECU's memory space, it does not have direct RAM addresses. Instead, the software uses specific RAM locations as intermediate input/output buffers. During execution, the ECU continuously synchronizes these RAM buffers with the physical hardware registers (which are mirrored at memory spaces like `0x0F00`, `0x1F00`, and `0x2F00`).

### Common I/O Buffer Locations (P30 / P28 Codebases)

*   **RAM Address `0x10` & `0x11` (Digital Input Bytes):** Bits in these bytes represent switch inputs.
    *   `11.2`: A/C Request Switch
    *   `10.5`: VTEC Pressure Switch (VTS) feedback
*   **RAM Address `0x20`, `0x22`, & `0x24` (Digital Output Bytes):** Modifying bits in these RAM bytes changes output states.
    *   `20.0`: A/C Clutch Relay Solenoid
    *   `22.0`: VTEC Solenoid Output
*   **RAM Address `0x14` (Error Flag Byte):** Used to store diagnostic fault flags.
    *   `14.4`: VTEC Solenoid open/short circuit error

---

## 3. Assembly Code Analysis (OKI 66k)

Examining the JDM OBD1 P30 assembly code (stock ROM version `P30_203`) demonstrates how the ECU processes these RAM buffers.

### Example A: A/C Clutch Control Logic

This routine checks the state of the A/C cabin button and controls the compressor clutch relay output:

```assembly
4306- DA 11 17 : JBR off 11.2, 4320   ; Jump to 4320 if A/C cabin switch (11.2) is OFF (Reset)
4309- C4 26 1C : SB off 26.4          ; Set bit 26.4
430C- F4 E2    : LB A, off E2
430E- CE 1B    : JNE 432B
4310- C4 E3 98 32 : MOVB off E3, #32
4314- C4 1B 18 : SB off 1B.0
4317- 95       : RC
4318- CB 15    : SJ 432F
431A- C4 B8 15 : CLRB off B8
431D- C4 E3 15 : CLRB off E3

4320- C4 26 0C : RB off 26.4          ; Reset bit 26.4
4323- F4 E3    : LB A, off E3
4325- CE ED    : JNE 4314
4327- C4 E2 98 32 : MOVB off E2, #32
432B- C4 1B 08 : RB off 1B.0
432E- 85       : SC
432F- C5 20 38 : MB 20.0, C           ; Output state to A/C Clutch Solenoid (20.0) based on Carry
```

### Example B: VTEC Pressure Switch (VTS) Feedback Verification

To prevent VTEC activation if oil pressure is insufficient, the ECU compares the VTEC solenoid output state against the VTS sensor input. If they do not match, the ECU triggers a Check Engine Light (Code 21):

```assembly
3D06- DC 16 1B : JBR off 16.4, 3D24   ; Jump if VTEC is software-disabled
3D09- EC 14 18 : JBS off 14.4, 3D24   ; Jump to 3D24 if VTS error flag (14.4) is already active
3D0C- DA 1F 0C : JBR off 1F.2, 3D1B   ; Jump to 3D1B if VTEC solenoid output is not active
3D0F- C4 C0 98 14 : MOVB off C0, #14
3D13- F4 BF    : LB A, off BF
3D15- ED 10 0C : JBS off 10.5, 3D24   ; Jump if VTEC Pressure Switch (10.5) is active (Ground/Closed)
3D18- 85       : SC
3D19- CB 09    : SJ 3D24
3D1B- C4 BF 98 14 : MOVB off BF, #14
3D1F- F4 C0    : LB A, off C0
3D21- ED 10 F4 : JBS off 10.5, 3D18
3D24- C5 9A 38 : MB 9A.0, C           ; If mismatch, set bit 9A.0 to trigger Code 21 (VTEC Switch)
```

By altering this routine (such as patching out the check on bit `10.5`), tuners can run VTEC on engines that lack the physical VTEC oil pressure switch, which is typical for JDM cylinder head swaps.

---

## 4. Hardware Jumpers (RP17, RP18)
The ECU's configuration jumpers (RP17 and RP18) are connected directly to multiplexed analog inputs. Because these jumpers act as pull-up or pull-down resistance dividers, the analog-to-digital converter reads their voltage to determine which chassis configuration, regional market, or transmission type (automatic vs. manual) the ECU software should assume.
