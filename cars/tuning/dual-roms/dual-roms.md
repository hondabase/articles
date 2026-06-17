---
summary: 'Hardware modification guide to creating a dual-ROM setup using a 27C512 EPROM and a toggle switch to select between two engine tunes.'
tags: [ecu, hardware, tuning]
applies_to:
  obd: [0, 1]
  models: [accord, civic, crx, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, ef, eg, eg-eh]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Dual Roms'
    url: /pgmfi/wiki/library/dual-roms
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# DIY Dual-ROM Setup (27C512 Jumper Switch)

A standard Honda OBD0 or OBD1 ECU ROM calibration is 32 KB (256 kilobits) and fits on a standard `27C256` chip. By using a double-capacity **`27C512`** EPROM (64 KB / 512 kilobits), you can store two complete, independent ROM calibrations on a single physical chip and toggle between them using a simple dashboard switch.

---

## 1. ROM File Preparation

To create a dual-ROM binary:
1. Open your ROM editing software (such as Crome or TurboEdit) and save your two separate 32 KB tuned BIN files (e.g., `Tune_A.bin` and `Tune_B.bin`).
2. Use a file merger tool or a hex editor to combine the two files into a single 64 KB binary:
 

* **Lower Bank (Offset `0x0000` to `0x7FFF`):** Place `Tune_A.bin` here.
 

* **Upper Bank (Offset `0x8000` to `0xFFFF`):** Place `Tune_B.bin` here.
3. Program the merged 64 KB file onto a `27C512` EPROM or SST `27SF512` Flash chip.

---

## 2. Hardware Modification & Wiring

To toggle between the two memory banks, you must control the state of the highest address line on the 27C512 chip: **Pin 1 (A15)**.

* When **Pin 1 is grounded (0V)**, the address lines access the lower 32 KB bank (`A15 = 0`).
* When **Pin 1 receives +5V (VCC)**, the address lines access the upper 32 KB bank (`A15 = 1`).

```text
 27C512 EPROM Chip
 +------()------+
 [Switch] <---|1 (A15) 28| VCC (+5V Power)
 |2 27| 
 |3 26|......
 |14 (GND) 15| 
 +--------------+
```

### Step-by-Step Wiring:

1. **Isolate Pin 1:** Bend **Pin 1 (A15)** on your `27C512` EPROM chip outward at a 90-degree angle so it does not insert into the ECU socket.
 
 > [!CAUTION]
 > Pin 1 of a standard ECU `27C256` socket carries a constant +5V line (which serves as the programming voltage `VPP` pin on older chips). If you do not bend Pin 1 outward and you ground the switch, you will create a direct short circuit on the ECU\'s +5V power rail, instantly shutting off the engine and potentially damaging the ECU's voltage regulator.

2. **Solder Jumper Resistor:** Solder a 10k $\Omega$ pull-up resistor between the bent Pin 1 and Pin 28 (VCC, +5V power) of the chip. This keeps the pin high (+5V) by default when the switch is open.
3. **Wire the Switch:** Connect a wire from the bent Pin 1 to a single-pole single-throw (SPST) toggle switch in your dashboard. Connect the other side of the switch to a chassis ground point (or Pin 14 of the ECU board).
 

* **Switch Open:** Pin 1 is pulled up to +5V (running `Tune_B`).
 

* **Switch Closed:** Pin 1 is grounded (running `Tune_A`).

---

## 3. Best Practices for Dual Tunes

* **Disable Checksums:** Ensure checksum validation is disabled on both ROM files before writing them to prevent the ECU from triggering a solid Check Engine Light (limp mode) during switching.

* **Keep Codebases Identical:** If you plan to switch on the fly (for example, engaging a nitrous tune when a solenoid activates), ensure both ROM files utilize the exact same codebase version. The only differences should be the fuel and ignition values in the lookup tables. Switching between different codebase structures while the engine is running will crash the MCU.
