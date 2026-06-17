---
summary: 'Technical guide to wiring, configuring, and loopback testing FTDI-based USB-to-TTL serial adapters for Honda ECU datalogging.'
tags: [datalogging, hardware, wiring]
applies_to:
  obd: [0, 1]
  models: [accord, civic, crx, del-sol, integra, prelude]
  chassis: [bb, cb-cd, da, dc2, ef, eg, eg-eh]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Usb To Serial Converter Second Gen'
    url: /pgmfi/wiki/library/usb-to-serial-converter-second-gen
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# USB-to-Serial TTL Adapters (`FTDI` / USBMOD3)

Modern laptops lack the legacy RS-232 serial COM ports historically used to connect to automotive tuning hardware. To establish a real-time datalogging connection with a Honda ECU, you must use a USB-to-TTL serial converter. 

One highly reliable solution is the **Elexol USBMOD3**, a breakout module powered by a high-speed `FTDI` transceiver chip that translates the ECU's 5V TTL serial signals into USB-compliant data packets.

---

## 1. Module Configuration & Pin Map

To configure the USBMOD3 module for bus-powered (USB-powered) operation and bypass hardware handshake controls, make the following pin connections on the module's interface:

| Source Pin | Target Pin | Purpose |
| :---: | :---: | :--- |
| **Pin 4 (Vcc)** | **Pin 8 (Reset In)** | Pulls the reset line high (prevents accidental resets). |
| **Pin 9 (Enum Power)** | **Pin 10 (Reset Out)** | Configures the module for bus-powered operation. |
| **Pin 18 (Power Control)** | **Ground (GND)** | Pulls power control low to enable bus power mode. |
| **Pin 12 (VIO)** | **Pin 13 (V+)** | Powers the UART I/O pins at the correct internal voltage. |
| **Pin 23 (DSR)** | **Pin 24 (DTR)** | Bridges Data Set Ready to Data Terminal Ready to bypass hardware modem handshake controls. |
| **Pin 25 (CTS)** | **Pin 26 (RTS)** | Bridges Clear To Send to Request To Send to bypass hardware flow control. |

---

## 2. Loopback Diagnostic Test

Before soldering the module to your ECU harness, perform a loopback test to verify that the USB converter chip and PC drivers are functioning correctly:

1. **Bridge Serial Lines:** Temporarily connect a jumper wire between **Pin 27 (RXD)** and **Pin 28 (TXD)** on the USBMOD3 board.
2. **Connect to PC:** Plug the module's USB cable into your laptop. Download and install the standard FTDI Virtual COM Port (VCP) drivers from the official FTDI website.
3. **Identify COM Port:** Open Windows **Device Manager** and expand the **Ports (COM & LPT)** section. Note the COM port number assigned to the USB Serial Port (e.g., `COM3`).
4. **Open Terminal Console:** Launch a serial terminal application (such as PuTTY or Tera Term) and connect to the identified COM port at **38400 baud**.
5. **Type Test:** Type several characters into the terminal window.
 

* **Success:** If you see the characters echo back on the screen, the FTDI chip is successfully transmitting and receiving data.
 

* **Failure:** If nothing appears, check your drivers, pin jumpers, and USB cable.

---

## 3. Wiring to the ECU `CN2` Port

Once the loopback test passes, remove the temporary jumper between Pin 27 and 28, and connect the module to the ECU\'s `CN2` header:

1. Connect **Pin 27 (RXD on module)** to **Pin 2 (ECU TX)** on the `CN2` header.
2. Connect **Pin 28 (TXD on module)** to **Pin 4 (ECU RX)** on the `CN2` header.
3. Connect **Ground (GND on module)** to **Pin 1 (ECU GND)** on the `CN2` header.

> [!WARNING]
> Never connect the ECU's `CN2` Pin 5 (12V) to the USBMOD3 board. This will instantly destroy the transceiver module and damage your laptop's USB port.
