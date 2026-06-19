---
summary: 'Hardware modification guide for socketing, chipping, and converting JDM square-case OBD1 P30 ECUs to manual transmission.'
tags: [ecu, chipping, hardware, p30, obd1]
applies_to:
  brand: Honda
  ecus: [P30]
  models: [civic, del-sol]
  chassis: [eg, eh]
complexity: advanced
---

# Chipping the JDM OBD1 P30 ECU

The Japanese Domestic Market (JDM) OBD1 P30 DOHC VTEC ECU is housed in a compact, square-shaped metal casing, which differs from the larger rectangular casing used for USDM ECUs. Because of the compact board layout, chipping a JDM P30 requires working with surface-mount devices (SMD) rather than through-hole components. The memory latch (`74HC373`) must be soldered directly to SMT pads on the board.

## 1. Required Components

To chip a JDM P30 ECU, source the following components:

| Component Location | Description / Value | Manufacturer / Part Number |
| :--- | :--- | :--- |
| **Latch (IC)** | `74HC373` SMD Latch (SOP-20 package) | SN74HC373NSR (Digi-Key: `296-8310-1-ND`) |
| **ROM Socket** | 28-pin low-profile DIP Socket | Standard 0.6" width DIP-28 |
| **EPROM** | Reprogrammable EPROM | SST `27SF256` or `29C256` |
| **`C49` & `C50`** | `0.004 uF` SMD ceramic capacitor | Digi-Key: `399-1230-1-ND` |
| **`C91` & `C92`** | `0.0001 uF` (100 pF) SMD ceramic capacitor | Digi-Key: `399-1192-1-ND` |

> [!WARNING]
> The original reference images showing the precise locations of the capacitors and jumpers on the board underside were not recovered from the legacy archives. Ensure you verify the pad labels silk-screened on your PCB before soldering.

## 2. Step-by-Step Chipping Procedure

1. **Install the SMD Latch:** Locate the footprint for the 74HC373 latch on the board. Apply flux to the SMT pads, align the chip pins (ensuring the pin 1 notch matches the board layout), and solder the SOP-20 chip in place. Check for solder bridges between pins.
2. **Solder the ROM Socket:** Clean the factory solder out of the DIP-28 through-holes on the board. Insert the 28-pin socket from the top side and solder all 28 pins from the underside.
3. **Add Filtering Capacitors:** 
   - Solder **`C49`** and **`C50`** to their pads on the underside of the board.
   - Solder **`C92`** to its pads on the underside.
   - Solder **`C91`** to its pads on the top side of the board near the latch.
4. **Bridge Jumper J1:** Bridge the pads at jumper **`J1`** on the underside of the board with a blob of solder or a small wire. This tells the internal microcontroller to bypass its internal ROM and read from the newly installed EPROM.
5. **Insert the EPROM:** Insert a programmed SST 27SF256 EPROM into the DIP-28 socket. Ensure the notch on the chip matches the notch on the socket.

## 3. Datalogging & Real-Time Programming (RTP)

If you plan to use a real-time emulator (like Moates Ostrich) or datalog via the serial port:

- **Remove `J4`:** Locate and desolder the 0-ohm jumper resistor at position **`J4`** on the top side of the board. Removing `J4` disconnects the factory debug routines and enables full-duplex serial data transmission.
- **Install `CN2` Pins:** Solder a 4-pin male pin header (0.1" spacing) into the **`CN2`** port location to connect your USB-to-TTL datalogging cable.

## 4. Automatic to Manual Transmission Conversion

To convert an automatic JDM P30 ECU to a manual configuration and prevent automatic lockup solenoid CELs:

1. Locate the resistor array in the bottom right section on the underside of the board.
2. Desolder and remove resistor **`RP18`** (marked "472" / 4.7k ohms) and replace it with a solid jumper wire (0 ohms).
3. Desolder and remove resistor **`RP17`** entirely, leaving the pads open.
