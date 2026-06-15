---
summary: 'Technical analysis of the diagnostic debug mode and ROM configuration byte switches in the OBD1 Honda P72 ECU.'
tags: [ecu, diagnostics, rom]
applies_to:
  obd: [1]
  models: [civic, del-sol, integra]
  chassis: [da, dc2, eg, eg-eh]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'P72 Debug Mode'
    url: /pgmfi/wiki/library/p72-debug-mode
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1 P72 ECU Debug Mode & ROM Configuration Switches

The OBD1 P72 ECU (which runs the B18C1 engine in the Acura Integra GS-R) contains a built-in diagnostic and debug segment in its ROM code. Much like the P30 (DOHC VTEC Civic/del Sol) codebase, the P72 software features a master debug switch that can override standard sensor check routines and alter diagnostic behavior.

By modifying the master debug byte in the ROM, developers can change how the ECU processes error codes, sensor bypasses, and communication telemetry.

---

## 1. The Debug Master Switch (`0x547E`)

The entry point for debug mode is controlled by a single-byte switch located at ROM address **`0x547E`**. 

*   **Value = `0x00` (Debug Disabled):** The ECU runs standard engine checks, sensor diagnostics, and code evaluations.
*   **Value > `0x00` (Debug Enabled):** The ECU activates alternate logic branches, overriding several standard sensor checking subroutines.

---

## 2. Assembly Analysis (OKI 66k Instruction Set)

The following assembly block from the P72 ROM shows how the ECU evaluates the debug flag to load alternate settings:

```assembly
; 1. Load the master debug byte into Register 0
53A7- LCB    A, 0547eh               ; Load Code Byte from 0x547E into Accumulator A
53AB- STB    A, r0                   ; Store Byte from Accumulator A to Register 0 (r0)

; 2. Fetch memory configuration pointer
53AC- MOV    DP, #003d3h             ; Move Data Pointer to 0x03D3
53AF- LB     A, [[[DP]]]             ; Load Byte from pointer address into A
53B0- STB    A, r2                   ; Store Byte to Register 2 (r2)

; 3. If master debug is disabled (r0 == 0), skip to label_53ba
53B1- CMPB   r0, #000h               ; Compare byte in r0 to 0x00
53B4- JEQ    label_53ba              ; Jump if Equal to label_53ba

; 4. If debug is enabled, load secondary debug switch
53B6- LCB    A, 0547fh               ; Load Code Byte from 0x547F into A

; 5. Process internal RAM flags
label_53ba:     
53BA- SLLB   A                       ; Shift Left Logical Byte (places MSB into Carry flag)
53BB- MB     off(00216h).3, C        ; Move Carry bit (C) to bit 3 of RAM offset 0x0216

53BE- LCB    A, 05475h               ; Load Code Byte from 0x5475 into A
53C2- SLLB   A                       ; Shift Left Logical Byte
53C3- MB     off(002eeh).3, C        ; Move Carry bit to bit 3 of RAM offset 0x02EE

; 6. Evaluate r0 again to load the tertiary debug switch
53C6- CMPB   r0, #000h               ; Compare r0 to 0x00
53C9- JEQ    label_53d2              ; Jump if Equal to label_53d2
53CB- LCB    A, 05480h               ; Load Code Byte from 0x5480 into A
53CF- SLLB   A                       ; Shift Left Logical Byte
53D0- SJ     label_53dc              ; Short Jump to label_53dc
```

### Execution Flow:
1.  The ECU checks the master debug switch at `0x547E`.
2.  If the debug switch is `0x00`, the execution jumps directly to `label_53ba`, bypassing the secondary lookup at `0x547F` and the tertiary lookup at `0x5480`.
3.  If the debug switch is non-zero, the ECU processes additional configuration flags at `0x547F` and `0x5480`, saving their status as bitwise flags in RAM address offsets `0x0216` and `0x02EE`.

---

## 3. Neighboring Configuration Byte Switches

The block of ROM memory from address **`0x5470`** to **`0x548F`** acts as a configuration table containing single-byte switch flags. These flags determine whether specific software subsystems are active:

*   **VTEC Solenoid Checks:** Enable or disable diagnostic loops that verify VTEC solenoid continuity.
*   **VSS VTEC Check:** Enable or disable the minimum speed requirement check for VTEC engagement.
*   **Knock Sensor Checks:** Toggle the evaluation of knock sensor daughterboard signals.
*   **Oxygen Sensor Diagnostics:** Toggle heated sensor heater circuit diagnostics.

When master debug mode (`0x547E`) is active, these individual switches are bypassed or overridden by the master debug routine, allowing for diagnostic testing of custom ROMs on engines missing these physical inputs.
