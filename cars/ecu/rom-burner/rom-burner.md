---
summary: 'A guide to choosing and using EPROM/Flash ROM burners for programming 27C256 and SST 27SF256 memory chips in Honda ECUs.'
tags: [hardware, reference]
applies_to:
  obd: [0, 1, 2]
  models: [integra]
  chassis: [ef]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Rom Burner'
    url: /pgmfi/wiki/library/rom-burner
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Guide to EPROM and Flash ROM Burners

A ROM burner (also known as a device programmer) is an electronic tool used to write compiled binary calibration files (`.bin`) from a computer onto memory chips. These chips are then inserted into the IC socket of a modified ECU to run custom maps. 

Because Honda OBD0 and OBD1 ECUs require 32 KB of program space, selecting a burner that supports 256-kilobit (256k) memory chips is essential.

---

## 1. Supported Chip Types

While many chips share a DIP-28 package, their writing and erasing procedures vary:

*   **27C256 (EPROM):** Erasable Programmable Read-Only Memory. These are typically one-time programmable (OTP) unless you use windowed chips, which require a dedicated ultraviolet (UV) eraser box to clear before rewriting.
*   **SST 27SF256 (Flash EPROM):** Many tuners prefer this chip. It can be electrically erased and rewritten in seconds by the burner software, eliminating the need for UV light.
*   **AT29C256 (EEPROM):** Electrically Erasable PROM. Similar to the SST flash chip, but with different write timing algorithms and voltages.

---

## 2. Programmer Hardware Options

Below is a comparison of burners commonly used for Honda ECU tuning:

| Programmer Model | Interface | Status | Notes |
| :--- | :---: | :--- | :--- |
| **XGecu TL866 / T48 (MiniPro)** | USB | **Modern Standard** | The current go-to programmer for DIY tuners. Cheap, actively supported, and programs SST `27SF256` and `27C256` chips quickly. |
| **Moates BURN1 / BURN2** | USB | **Legacy / Used** | Custom USB programmers designed by Moates specifically for automotive tuning. They work natively with SST `27SF256` chips and integrate directly with software like Crome. |
| **Willem Programmer** | Parallel (LPT) / USB | **Legacy / DIY** | Very inexpensive open-source style board. Older parallel versions require a true hardware parallel port (LPT1) and will fail on USB-to-parallel printer adapters. |
| **Pocket Programmer 2** | Parallel | **Legacy** | Historically bundled with older Hondata packages; requires a parallel port. |
| **Batronix USB Programmer** | USB | **Professional** | High-quality German-engineered professional burner with excellent software support. |
| **Xeltek SuperPro / EE Tools** | USB | **Professional** | High-end professional programmers; reliable but generally expensive for single-vehicle hobbyists. |

---

## 3. Programming Tips

*   **Select the Correct Chip Profile:** Always select the exact manufacturer and model prefix of your chip (e.g., `SST27SF256` instead of a generic `27C256`) in your burner software. Applying the wrong programming voltage (Vpp) can permanently damage the chip.
*   **Verify After Writing:** Enable the "Verify" function in your burner software. This compares the chip's written contents byte-by-byte with the raw BIN file on your computer to ensure there were no write errors.
