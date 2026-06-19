---
summary: 'Technical guide to converting a legacy Nokia FBUS serial phone cable into a low-cost USB-to-TTL serial adapter for OBD1 Honda ECU datalogging.'
tags: [datalogging, hardware, wiring]
applies_to:
  models: [accord, civic, crx, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, ef, eg, eg-eh]
complexity: advanced
---

# DIY Datalogging Cable (Nokia FBUS Modification)

Datalogging from an OBD1 Honda ECU requires converting the ECU's 5V TTL (Transistor-Transistor Logic) serial signal from the `CN2` header into a standard USB signal.

A legacy Nokia FBUS mobile phone data cable (originally used for Nokia 3200/5100/6100 series phones) can be repurposed as a high-quality USB-to-TTL serial adapter, as these cables contain a **Prolific PL-2303** transceiver chip.

---

## Safety & Pinout

> [!CAUTION]
> Pin 5 on the ECU's `CN2` header carries raw +12V battery voltage. **Never connect this pin** to your USB adapter or laptop, as it will cause permanent damage to your equipment.

### CN2 Header Pinout
| Pin | Function | Connection |
| :---: | :--- | :--- |
| **1** | Ground (GND) | Connect to Cable Ground |
| **2** | ECU Transmit (TX) | Connect to Cable Receive (RX) |
| **3** | +5V Logic | *Do not connect* |
| **4** | ECU Receive (RX) | Connect to Cable Transmit (TX) |
| **5** | +12V Power | **DO NOT CONNECT** |

---

## Wiring Options

You must identify your specific Nokia cable type by opening the USB plug housing and examining the internal PCB.

### Option A: RadioShack USB Cable (#170-0787)
*   **Brown:** Ground (Pin 1)
*   **Orange:** Cable RX -> Connect to Pin 2 (ECU TX)
*   **Red:** Cable TX -> Connect to Pin 4 (ECU RX)

### Option B: Generic / eBay Nokia Cable
*   **Black:** Ground (Pin 1)
*   **White:** Cable RX -> Connect to Pin 2 (ECU TX)
*   **Blue:** Cable TX -> Connect to Pin 4 (ECU RX)

---

## Software Configuration
1.  **Jumper Removal:** Desolder and remove the **`J12`** jumper on the main ECU board to enable full-duplex communication.
2.  **Drivers:** Install the generic **Prolific PL-2303** USB-to-Serial driver.
3.  **Baud Rate:** Set your tuning suite (Crome, Hondata, TurboEdit) to the assigned COM port at **38400 baud**.
