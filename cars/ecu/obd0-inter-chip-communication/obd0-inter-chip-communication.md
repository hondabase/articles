---
summary: 'Technical documentation regarding the OBD0 ECU memory bus, peripheral address ranges, and chip-select logic for the OKI M83C154/M80C154 MCU.'
tags: [ecu, hardware, memory, reverse-engineering, obd0]
applies_to:
  models: [civic, crx]
  chassis: [ef]
complexity: advanced
---

# OBD0 ECU Inter-Chip Communication and Memory Mapping

This article details the communication architecture between the OBD0 OKI M83C154 or M80C154 MCU and its external peripherals, including external RAM, the I/O controller, the ADC, and EPROM.

> [!NOTE]
> The following data is derived from historical reverse-engineering efforts. It is not a confirmed schematic and contains unresolved address ranges and contradictory pin descriptions.

## Peripheral Devices
The MCU interfaces with the following external components via the memory bus:

*   **NEC uPD7004C:** Analog-to-Digital Converter (ADC).
*   **5128:** External SRAM.
*   **OKI 6260A:** I/O Controller.
*   **38256:** 32K EPROM (present in specific ECU variants).

The MCU utilizes `MOVX A,@DPTR` and `MOVX @DPTR, A` instructions to access these devices. Logic gates are employed on address lines to facilitate chip selection.

## Proposed Memory Map
The following table outlines the proposed memory address ranges for peripheral devices.

| Start | End | Device | Confidence Note |
| :--- | :--- | :--- | :--- |
| `1000` | `1FFF` / `11FF` (?) | 5128 XRAM | End address unresolved |
| `2000` | `2FFF` / `3FFF` (?) | OKI 6260A | End address unresolved |
| `4000` | `4FFF` (?) | NEC uPD7004C | End address unresolved |
| `8XXX` | N/A | Unused | Earmarked for RTP |

## Observed DPTR Values
The following DPTR values were observed during operation, suggesting that the address bus directly influences chip-enable logic:

| Address (Hex) | Binary Representation |
| :--- | :--- |
| `0110Bh` | `0001000100001011` |
| `0110Eh` | `0001000100001110` |
| `01120h` | `0001000100100000` |
| `0112Bh` | `0001000100101011` |
| `0112Eh` | `0001000100101110` |
| `01150h` | `0001000101010000` |
| `01151h` | `0001000101010001` |
| `01152h` | `0001000101010010` |
| `01154h` | `0001000101010100` |
| `01160h` | `0001000101100000` |
| `011F5h` | `0001000111110101` |
| `02000h` | `0010000000000000` |
| `02001h` | `0010000000000001` |
| `02002h` | `0010000000000010` |
| `02003h` | `0010000000000011` |
| `02004h` | `0010000000000100` |
| `02006h` | `0010000000000110` |
| `0200Ah` | `0010000000001010` |
| `0200Bh` | `0010000000001011` |
| `0200Eh` | `0010000000001110` |
| `0200Fh` | `0010000000001111` |
| `04000h` | `0100000000000000` |
| `04001h` | `0100000000000001` |

## Decode Logic Traces
The following traces were recorded to map the chip-select logic involving 74HC04 (hex inverter) and 74HC132 (quad NAND) gates:

*   **M5128 Pin 18 (CE):** Connected to 74HC132 Pin 8 (Out 3Y).
*   **74HC132 Pin 9 (In 3A):** Connected to 80C154 Pin 25 (A8) and 6260 Pin 11.
*   **74HC132 Pin 11 (4 out):** Connected via R143 to 74HC132 Pin 1 (In 1A).
*   **74HC132 Pin 6 (2 out):** Connected to 74HC132 Pin 2 (In 1B).
*   **74HC132 Pin 3 (1 out):** Connected to 74HC132 Pin 12 (In 4A).
*   **74HC04 Pin 2 (Out 1Y):** Connected to 74HC132 Pin 4 (In 2A).
*   **74HC04 Pin 4 (Out 2Y):** Connected via R55/C55 to 74HC04 Pin 6 (Out 3Y) and D7004C Pin 22.
*   **74HC04 Pin 8 (Out 4Y):** Connected to ADC board Pin 5.
*   **74HC04 Pin 10 (Out 5Y):** Connected to 83C154 Pin 14 (P3.4).
*   **6260 Pin 12:** Connected to 80C154 Pin 30 (ALE).
*   **6260 Pin 13:** Connected to 80C154 Pin 16 (WR).
*   **6260 Pin 14:** Connected to D7004C Pin 19.

> [!IMPORTANT]
> Observations indicate that when the high-nibble high bit is `0` for addresses `2000h-4001h`, uPD7004C Pin 22 is pulled low. The inverse occurs when the bit is high.

## Related Documentation
*   [NEC uPD7004C ADC](/cars/sensors/upd7004c)
*   [OKI 6260A I/O Controller](/cars/ecu/oki6260a)
*   [OBD0 PM6/PM7 RAM Locations](/cars/rom/obd0pm6pm7ram-locations)
