---
summary: 'Selection guide for memory chips used in Honda OBD0 and OBD1 ECU chipping, addressing speed constraints, compatibility, and pinout variations.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - ecu
  - chipping
  - hardware
---

# Sourcing Memory Chips for Honda ECUs

Socketing or chipping a 1990–1995 Honda OBD0 or OBD1 ECU requires installing a 32 KB (256-kilobit) parallel memory chip. While several chip types fit the physical DIP-28 socket footprint, they have different access speeds, erase procedures, and pinouts.

---

## 1. Supported Chip Technologies

Tuners commonly choose between three distinct chip technologies:

*   **SST 27SF256 (Flash Memory - Recommended):** This is the industry standard for Honda tuning. It is electrically erasable and rewriteable, meaning it can be programmed repeatedly in seconds using a standard USB burner.
*   **27C256 (EPROM):** Erasable Programmable ROM. Windowless versions are one-time programmable (OTP). Windowed versions can be erased using ultraviolet (UV) light, which takes 15–20 minutes in a UV eraser box.
*   **AT29C256 (EEPROM):** Electrically Erasable PROM. Compatible with standard sockets and easily rewriteable, but less common than SST flash chips.

---

## 2. Speed Specifications (Access Time)

ECU microcontrollers require extremely fast data retrieval to coordinate fuel injector pulses and ignition events. 

*   **The Spec:** Honda specifications mandate memory chips rated at **170 nanoseconds (ns) or faster**. 
*   **Recommendation:** While some chips labeled 200ns will function because they exceed their rated speeds in practice, it is highly recommended to source chips rated at **150ns, 120ns, 90ns, or 70ns** to guarantee stability under high heat and high RPM.

### Access Speed Suffixes:
*   `-20` = 200ns (risky; use only if verified)
*   `-17` = 170ns (minimum factory specification)
*   `-15` = 150ns
*   `-12` = 120ns
*   `-9` or `-90` = 90ns
*   `-7` or `-70` = 70ns

### Historical Example
Early production runs of the OBD0 Acura Integra PR4 ECU (dated June 1989) shipped from the factory with a windowed `27C256-17` (170ns) chip in a factory socket. Because mass-production mask ROMs were not ready in time, Honda utilized these reprogrammable chips to meet initial vehicle delivery targets.

![Factory windowed 27C256-17 EPROM in an early OBD0 PR4 ECU](chipmarkings.jpg)
*Factory-socketed windowed EPROM from a 1989 Acura Integra PR4 ECU.*

---

## 3. Incompatibility Warnings

### The `28C256` EEPROM
Do not confuse the recommended `27SF256` or `29C256` with the standard **`28C256`** EEPROM. Although the `28C256` shares the same 32 KB capacity and 28-pin DIP package, it uses a different pin configuration (specifically on write control pins). If plugged into a standard `27C256` socket, a `28C256` will not communicate with the ECU and will trigger a solid CEL. It requires circuit trace modification to function.
