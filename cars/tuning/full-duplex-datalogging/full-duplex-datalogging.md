---
summary: 'Explains the difference between half-duplex and full-duplex serial communication on OBD1 Honda ECUs and why removing the J12 jumper enables PC datalogging.'
tags: [datalogging, hardware]
applies_to:
  obd: [1]
  models: [civic, integra]
  chassis: {}
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Full Duplex Datalogging'
    url: /pgmfi/wiki/library/full-duplex-datalogging
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Full-Duplex Datalogging & the `J12` Jumper

To datalog from an OBD1 Honda ECU using a PC-based tuning suite (such as Crome, Hondata, or Neptune), you must configure the ECU's serial interface to run in **full-duplex** mode. By default, the factory ECU is configured for **half-duplex** operation. 

This configuration is controlled by a physical solder jumper on the ECU board labeled **`J12`**.

---

## 1. Half-Duplex vs. Full-Duplex

The communication mode dictates how data travels between the ECU and your diagnostic tool:

*   **Half-Duplex (J12 Closed):** In this mode, the transmit (TX) and receive (RX) lines share a single, bi-directional signal path. Only one device can transmit data at a time. The factory Honda ECU uses this mode to communicate with dealer diagnostic tools (such as the legacy Honda HDS) using a master-slave protocol where the tool requests data and the ECU responds.
*   **Full-Duplex (J12 Open):** In this mode, the transmit (TX) and receive (RX) lines are completely separated. Both the ECU and the PC can send and receive data simultaneously over dedicated wires (using the CN2 header).

---

## 2. Why the `J12` Jumper Must Be Removed

If you attempt to datalog with a PC while the **`J12`** jumper is still closed:

1.  The ECU's physical RX and TX lines remain bridged together.
2.  When your logging software sends a command byte to the ECU, that exact same signal is instantly echoed back into the PC\'s receiver wire.
3.  The logging software receives its own command as if it were a data response from the ECU.
4.  This mismatch confuses the serial buffer, resulting in reading lag, garbled data, or complete communication dropouts.

---

## 3. How to Enable Full-Duplex Mode

To convert the ECU to full-duplex operation:

1.  Locate jumper **`J12`** on the main ECU circuit board. On standard OBD1 Civics and Integras, this is a small two-pad solder bridge located near the main MCU.
2.  Use desoldering braid or a soldering iron to remove the solder bridge between the two pads. Alternatively, if it is a wire jumper, carefully cut the wire with wire snips.
3.  Ensure the two pads are completely separated and no solder bridge remains.

Once `J12` is opened, the serial interface will operate in full-duplex mode. This allows the PC to communicate cleanly with the ECU over the **`CN2`** header pins (using separate TX and RX lines) without echoing data back onto the PC\'s receive buffer.
