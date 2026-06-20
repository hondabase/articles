---
summary: 'An overview of One Time Programmable (OTP) EPROMs used in engine control units, detailing their permanent data storage characteristics.'
tags: [tuning, rom, eprom, hardware]
applies_to:
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: beginner
---

# One Time Programmable (OTP) EPROM

One Time Programmable (OTP) EPROMs are non-volatile memory chips that can be programmed exactly once. Once the data is written to the chip, the program is permanent and cannot be erased or modified.

## Technical Overview

OTP chips are functionally identical to standard EPROMs during the programming phase. However, they lack the quartz window found on traditional UV-erasable EPROMs. Because they cannot be exposed to ultraviolet light, the silicon die remains permanently shielded, preventing the erasure of the stored data.

> [!NOTE]
> OTP chips are often used in mass-production ECUs to reduce manufacturing costs, as they are cheaper to produce than windowed EPROMs.

## Key Characteristics

*   **Permanent Storage:** Once the programming process is complete, the data is locked.
*   **Cost-Effective:** Ideal for high-volume production environments where firmware updates are not required.
*   **Physical Design:** Lacks the transparent window found on erasable EPROMs (e.g., 27C256 or 27C512 series).
*   **Compatibility:** In many ECU applications, OTP chips can be replaced with compatible EEPROMs or Flash memory chips if a socket is installed, allowing for re-programmability.

## Handling and Usage

When working with ECUs equipped with OTP chips, consider the following:

*   **Verification:** Always verify the checksum of the binary file before attempting to program an OTP chip, as there is no opportunity to correct errors after the write process.
*   **Socketing:** If you intend to perform frequent tuning, it is recommended to desolder the OTP chip and install a high-quality DIP socket. This allows for the use of re-programmable chips (such as SST27SF512 or similar Flash memory).
*   **Programming:** Ensure your programmer supports the specific OTP chip model, as voltage requirements for the "burn" process may differ from standard EPROMs.
