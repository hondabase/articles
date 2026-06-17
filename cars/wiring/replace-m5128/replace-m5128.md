---
summary: 'Technical guide for upgrading a 2K SRAM chip in an OBD0 Honda ECU to a DS1220 NVSRAM for non-volatile memory retention.'
tags: [ecu, hardware, memory, tuning]
applies_to:
  obd: [0]
  models: [civic, crx, integra]
  chassis: [ef, da]
complexity: intermediate
---

# Replacing M5128 SRAM with DS1220 NVSRAM

This guide details the procedure for replacing the stock M5128 2K SRAM chip found in some OBD0 Honda ECUs with a DS1220 NVSRAM (Non-Volatile SRAM) module. This upgrade ensures that RAM contents are retained after power loss, which is essential for certain real-time programming (RTP) applications.

---

## Preparation and Hardware
*   **Target Module:** DS1220AB NVSRAM.
*   **Support Components:** 24-pin IC socket, 22-gauge wire.

---

## Installation Procedure

1.  **De-solder M5128:** Carefully remove the factory M5128 SRAM chip from the ECU PCB.
2.  **Modify Traces:** The factory M5128 configuration grounds pins 19 and 22, preventing full 2k address space utilization. You must cut the PCB traces leading to pins 19 and 22 to isolate them from ground.
3.  **Install Socket:** Solder the 24-pin IC socket into the board.
4.  **Wiring Modifications:**
    *   Solder a wire from M5128 socket pin 19 to MCU pin 23.
    *   Solder a wire from M5128 socket pin 22 to MCU pin 22.
5.  **Finalize:** Insert the DS1220AB NVSRAM into the socket.

---

## Technical Note
On 90–91 ECUs, the traces to be cut are located on the component side of the PCB. On 88–89 ECUs, one trace is on the solder side and one on the component side. Always verify the board revision before making permanent trace modifications.
