---
summary: 'How to configure and troubleshoot USB-to-TTL serial converters (such as FTDI or CP2102 chips) for reliable ECU datalogging.'
tags: [datalogging, serial, hardware]
applies_to:
  obd: [1]
  models: [integra]
  chassis: {}
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Second Gen Usb To Serial Converter'
    url: /pgmfi/wiki/library/second-gen-usb-to-serial-converter
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# USB-to-TTL Serial Converter Guide (`FTDI` & CP2102)

Modern laptops do not have physical DB9 serial ports. To interface with the [serial datalogging header (CN2)](/cars/tuning/serial-communication) on a Honda OBD1 ECU, you must use a USB-to-TTL converter board. These converters utilize integrated circuit chips to translate the USB bus signals into asynchronous serial TTL data (0V–5V logic) that the ECU's microcontroller can process.

The most popular and reliable chips used in these converters are the **`FTDI` FT232RL** and the **Silicon Labs CP2102**.

---

## 1. Wiring standard USB-to-TTL Modules

Unlike older, complex modular boards that required manual configuration of jumpers and handshaking lines, standard modern breakout boards expose a simple 4-pin or 6-pin interface. To connect a standard module to your ECU:

1. Locate the interface pins on the breakout board: **GND**, **TXD** (Transmit), and **RXD** (Receive).
2. Wire the ground pin of the module to **Pin 4** (GND) of the ECU's CN2 header.
3. Wire the module's **RXD** pin to **Pin 1** (TX) of the ECU's CN2 header.
4. Wire the module's **TXD** pin to **Pin 2** (RX) of the ECU's CN2 header.
5. Do **not** connect the VCC (+5V or +3.3V) pin of the module to the ECU. The module should draw its power from the laptop's USB port, while the ECU runs on its own internal power supply. This prevents ground loops and electrical interference.

---

## 2. Diagnosing Hardware: The Loopback Test

If your datalogging software fails to connect, you can perform a **loopback test** to isolate whether the issue lies in your USB converter/driver or within the ECU itself.

### Loopback Test Steps

1. Disconnect the USB-to-TTL module from the ECU's `CN2` header.
2. Using a small jumper wire, connect the module's **TXD** pin directly to its own **RXD** pin.
3. Plug the module into your laptop's USB port.
4. Open a serial terminal terminal program (such as PuTTY, Tera Term, or Arduino Serial Monitor).
5. Select the COM port corresponding to your module (found in Windows Device Manager under *Ports (COM & LPT)*) and configure the connection for **38,400 baud**.
6. Open the connection and type text in the terminal window:
 - **If the characters you type appear on the screen:** The USB interface, chip, driver, and laptop configuration are working perfectly. The issue lies in your ECU's `CN2` connections, soldering, ROM firmware, or wiring.
 - **If nothing appears on screen:** The converter module, USB cable, or drivers are faulty.

---

## 3. Optimizing COM Port Latency (Critical Step)

By default, FTDI and CP2102 USB drivers are configured with a latency timer optimized for high-bandwidth data transfers rather than real-time diagnostics. This default setting (typically **16 ms**) causes laggy datalogging updates, slow refresh rates, or frequent disconnections in programs like Crome or Hondata.

### How to Adjust Latency in Windows:

1. Open the Windows **Control Panel** and navigate to the **Device Manager**.
2. Expand the **Ports (COM & LPT)** section.
3. Right-click your USB-to-Serial COM port and select **Properties**.
4. Go to the **Port Settings** tab and click **Advanced**.
5. Locate the **Latency Timer** dropdown (default is 16).
6. Change this value to **1 ms**.
7. Click **OK** to save and close. Re-open your tuning software to verify the increased datalogging speed.

---

## 4. Troubleshooting Connection Issues

If your loopback test passes but you still cannot establish communication with the ECU:

- **Verify Signal Cross-Connection:** Double-check that TX connects to RX and RX connects to TX. It is a common mistake to wire TX-to-TX and RX-to-RX. If you suspect this, swap the two data lines on your `CN2` plug.
- **Inspect Solder Joints:** Cold solder joints on the ECU's `CN2` pin header can cause intermittent connection drops under engine vibration. Reflow the solder pads with fresh flux.
- **Isolate Ignition Noise:** Spark plug wires and distributor coils emit electromagnetic interference (EMI). Route your datalogging USB cable away from the engine bay wiring harness and distributor. Using a USB cable with a ferrite bead clamp can help block this noise.
- **Datalogging Plugin Check:** Verify that your ROM chip is burned with the correct datalogging plugin active (such as the Quick 2-byte datalogger for Crome) and that the ROM checksum is disabled. For more software debugging tips, consult the [debugging datalogging guide](/cars/diagnostics/debugging-data-logging).
