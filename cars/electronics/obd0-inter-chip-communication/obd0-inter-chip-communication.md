---
summary: Reverse-engineered notes on the OBD0 ECU memory bus, peripheral address ranges, and chip-select logic.
applies_to:
  obd: [0]
complexity: advanced
tags: [ecu, hardware, memory, reverse-engineering]
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD0 Inter Chip Communication'
    url: /pgmfi/wiki/library/obd0-inter-chip-communication
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD0 inter-chip communication notes

These archived reverse-engineering notes describe how an OBD0 OKI M83C154 or M80C154 MCU appears to communicate with external RAM, the I/O controller, the ADC, and, in some ECUs, an EPROM.

> [!NOTE]
> This is an incomplete investigation, not a confirmed schematic. The source marks several ranges and connections with question marks and includes contradictory pin descriptions. Those uncertainties are preserved here.

## Devices on the bus

The source identifies these devices as connected to the MCU:

- NEC [uPD7004C ADC](/cars/electronics/upd7004c)
- 5128 external SRAM
- [OKI 6260A I/O controller](/cars/electronics/oki6260a)
- 38256 32K EPROM in some ECUs

It reports that `MOVX A,@DPTR` and `MOVX @DPTR,A` instructions access devices on the external bus. Logic gates on some address lines appear to let the MCU select individual devices, but the decode logic was still being investigated.

## Proposed memory map

All addresses below are hexadecimal. The range endings are retained exactly as the source proposed them.

| Start | End | Device | Confidence note |
| --- | --- | --- | --- |
| `1000` | `1FFF` / `11FF` (?) | 5128 XRAM | End address unresolved |
| `2000` | `2FFF` / `3FFF` (?) | OKI 6260A | End address unresolved |
| `4000` | `4FFF` (?) | NEC uPD7004C | End address unresolved |
| `8XXX` | Not stated | Unused in the ECU; earmarked for RTP by the source | Historical proposal |

## Observed DPTR values

The archived page lists these as all addresses it observed the ECU loading into DPTR:

```text
0110Bh  0001000100001011
0110Eh  0001000100001110
01120h  0001000100100000
0112Bh  0001000100101011
0112Eh  0001000100101110
01150h  0001000101010000
01151h  0001000101010001
01152h  0001000101010010
01154h  0001000101010100
01160h  0001000101100000
011F5h  0001000111110101
02000h  0010000000000000
02001h  0010000000000001
02002h  0010000000000010
02003h  0010000000000011
02004h  0010000000000100
02006h  0010000000000110
0200Ah  0010000000001010
0200Bh  0010000000001011
0200Eh  0010000000001110
0200Fh  0010000000001111
04000h  0100000000000000
04001h  0100000000000001
```

These observations led the author to suspect that the address itself controls which support chip is enabled.

## Recorded decode-logic traces

The source identifies the 74HC04 as a hex inverter and records the following traces while trying to understand chip selection:

```text
M5128 Pin 18 (CE) -> 74HC132 Pin 8 (Out 3Y)
74HC132 Pin 9 (In 3A) -> 80C154 Pin 25 (A8) -> 6260 Pin 11 (?)
74HC132 Pin 10 (In 3B) -> 74HC132 Pin 5 (In 2B) -> 74HC04 Pin 13 (in 6Y)
74HC04 Pin 12 (out 6Y) -> 80C154 Pin 9 (RST)
74HC132 Pin 11 (4 out) -> R143 -> 74HC132 Pin 1 (in 1A)
74HC132 Pin 6 (2 out) -> 74HC132 Pin 2 (in 1B)
74HC132 Pin 3 (1 out) -> 74HC132 Pin 12 (in 4A)
74HC132 Pin 13 (in 4B) -> IC13 Pin 5
74HC04 Pin 2 (out 1Y) -> 74HC132 Pin 4 (in 2A)
74HC04 Pin 3 (in 2A) -> 6260A Pin 24 (?)
74HC04 Pin 4 (out 2Y) -> R55 -> C55 -> 74HC04 Pin 6 (out 3Y) -> D7004C Pin 22 (?)
74HC04 Pin 8 (out 4Y) -> ADC board Pin 5
74HC04 Pin 10 (out 5Y) -> 83C154 Pin 14 (P3.4)
6260 Pin 20 -> ADC board Pin 3
6260 Pin 12 -> 80C154 Pin 30 (ALE)
6260 Pin 13 -> 80C154 Pin 16 (WR)
6260 Pin 14 -> D7004C Pin 19
```

The page also claims that when a high-nibble high bit is `0` for addresses `2000h-4001h`, uPD7004C Pin 22 is low, and vice versa. That range and bit description were not resolved.

One source line describes `74HC04 Pin 13` as both an output and an input and loops it back through `74HC132 Pin 5`. It is omitted from the trace list above because it is self-contradictory, not because it has been corrected.

## Related

- [NEC uPD7004C ADC](/cars/electronics/upd7004c)
- [OKI 6260A I/O controller](/cars/electronics/oki6260a)
- [OBD0 PM6/PM7 RAM locations](/cars/electronics/obd0pm6pm7ram-locations)
