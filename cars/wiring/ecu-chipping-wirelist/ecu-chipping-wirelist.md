---
summary: 'Pin connections and traces between the MCU, latch, and external EPROM socket on OBD1 Honda ECUs.'
tags: [ECU, chipping, hardware, wiring]
applies_to:
  obd: [1]
  models: [civic, del-sol]
  chassis: [eg, eg-eh]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Ecu Chipping Wirelist'
    url: /pgmfi/wiki/library/ecu-chipping-wirelist
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1 ECU Chipping Wirelist

Use this archived Honda OBD1 ECU wirelist to diagnose continuity problems after installing an external ROM socket and `74HC373` latch. It records known connections between the latch, ROM socket, 66K MCU, `IC9`, resistor pack `RM3`, and nearby board components.

> [!CAUTION]
> Disconnect the ECU from the vehicle before continuity testing. These mappings are archived community observations, not a substitute for a verified schematic for your exact board.

## Continuity-testing procedure

1. Inspect the `74HC373` latch and ROM socket for solder bridges.
2. With a continuity tester, check every pair of adjacent pins around both packages. Adjacent pins should not have continuity.
3. Put one probe where each package pin enters the component.
4. Check that pin against at least one expected connection in the searchable wirelist below.
5. Use listed feed-throughs (`FT`) to test continuity between an IC pin and the board where available.

## Pin-numbering notes

- DIP pins begin at pin 1 beside the notch or dot, run down the left side, and continue back up the right side.
- `RM3` is a single-inline-package resistor pack; its pin 1 is marked on the silkscreen.
- On the JDM P30 board, 66K MCU pin 1 is in the middle of one side of the square surface-mount package. Several MCU pin numbers are marked on the board.
- Signal names beginning with `/` are active low.

## Searchable wirelist

Use the ECU-family and component filters, or search for a pin, signal, or connected component.

```wirelist
{
    "title": "OBD1 ECU chipping connections",
    "variants": [
        {
            "id": "jdm-p30-901",
            "label": "JDM P30-901",
            "groups": [
                {
                    "label": "373 latch",
                    "rows": [
                        {
                            "pin": "Pin 1",
                            "signal": "/OE",
                            "path": "373 Pin 10 -> FT -> ROM Pin 14 (GND) -> ROM Pin 20 (/CE)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 2",
                            "signal": "1Q",
                            "path": "RM3 Pin 5 -> ROM Pin 10 (A0)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 3",
                            "signal": "1D",
                            "path": "RM3 Pin 9 -> ROM Pin 11 (I/O0) -> 66K Pin 2 (AD0) -> IC9 Pin 11",
                            "note": ""
                        },
                        {
                            "pin": "Pin 4",
                            "signal": "2D",
                            "path": "RM3 Pin 8 -> ROM Pin 12 (I/O1) -> 66K Pin 3 (AD1) -> IC9 Pin 12",
                            "note": ""
                        },
                        {
                            "pin": "Pin 5",
                            "signal": "2Q",
                            "path": "ROM Pin 9 (A1)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 6",
                            "signal": "3Q",
                            "path": "ROM Pin 8 (A2)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 7",
                            "signal": "2D",
                            "path": "RM3 Pin 7 -> ROM Pin 13 (I/O2) -> 66K Pin 4 (AD2) -> IC9 Pin 13",
                            "note": "The archived latch list identifies this signal as 2D; the corresponding ROM list identifies it differently."
                        },
                        {
                            "pin": "Pin 8",
                            "signal": "2D",
                            "path": "RM3 Pin 6 -> ROM Pin 15 (I/O3) -> 66K Pin 5 (AD3) -> IC9 Pin 14",
                            "note": "The archived latch list identifies this signal as 2D; the corresponding ROM list identifies it differently."
                        },
                        {
                            "pin": "Pin 9",
                            "signal": "4Q",
                            "path": "ROM Pin 7",
                            "note": ""
                        },
                        {
                            "pin": "Pin 10",
                            "signal": "GND",
                            "path": "373 Pin 1 -> FT -> ROM Pin 14 (GND) -> ROM Pin 20 (/CE)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 11",
                            "signal": "LE",
                            "path": "C91 -> 66K Pin 24 (ALE)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 12",
                            "signal": "5Q",
                            "path": "ROM Pin 4 (A6)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 13",
                            "signal": "5D",
                            "path": "ROM Pin 18 (I/O6) -> 66K Pin 8 (AD6) -> IC9 Pin 17",
                            "note": ""
                        },
                        {
                            "pin": "Pin 14",
                            "signal": "6D",
                            "path": "ROM Pin 19 (I/O7) -> 66K Pin 9 (AD7) -> IC9 Pin 18",
                            "note": ""
                        },
                        {
                            "pin": "Pin 15",
                            "signal": "6Q",
                            "path": "FT -> ROM Pin 3 (A7)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 16",
                            "signal": "7Q",
                            "path": "FT -> ROM Pin 5 (A5)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 17",
                            "signal": "7D",
                            "path": "ROM Pin 17 (I/O5) -> 66K Pin 7 (AD5) -> IC9 Pin 16",
                            "note": ""
                        },
                        {
                            "pin": "Pin 18",
                            "signal": "8D",
                            "path": "ROM Pin 16 (I/O4) -> 66K Pin 6 (AD4) -> IC9 Pin 15",
                            "note": ""
                        },
                        {
                            "pin": "Pin 19",
                            "signal": "8Q",
                            "path": "ROM Pin 6 (A4)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 20",
                            "signal": "VCC",
                            "path": "C49 -> ROM Pin 28 (VCC) -> ROM Pin 1 (/WE)",
                            "note": ""
                        }
                    ]
                },
                {
                    "label": "ROM socket",
                    "rows": [
                        {
                            "pin": "Pin 1",
                            "signal": "VCC",
                            "path": "ROM Pin 28 (VCC) -> C49 -> 373 Pin 20 (VCC)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 2",
                            "signal": "A12",
                            "path": "66K Pin 14 (A12)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 3",
                            "signal": "A7",
                            "path": "FT -> 373 Pin 15 (6Q)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 4",
                            "signal": "A6",
                            "path": "FT -> 373 Pin 12 (5Q)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 5",
                            "signal": "A5",
                            "path": "FT -> 373 Pin 16 (7Q)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 6",
                            "signal": "A4",
                            "path": "373 Pin 19 (8Q)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 7",
                            "signal": "A3",
                            "path": "373 Pin 9 (4Q)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 8",
                            "signal": "A2",
                            "path": "FT -> 373 Pin 6 (3Q)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 9",
                            "signal": "A1",
                            "path": "FT -> 373 Pin 5 (2Q)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 10",
                            "signal": "A0",
                            "path": "RM3 Pin 5 -> FT -> 373 Pin 2 (1Q)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 11",
                            "signal": "I/O0",
                            "path": "RM3 Pin 9 -> 373 Pin 3 (1D) -> 66K Pin 2 (AD0) -> IC9 Pin 11",
                            "note": ""
                        },
                        {
                            "pin": "Pin 12",
                            "signal": "I/O1",
                            "path": "RM3 Pin 8 -> 373 Pin 4 (2D) -> 66K Pin 3 (AD1) -> IC9 Pin 12",
                            "note": ""
                        },
                        {
                            "pin": "Pin 13",
                            "signal": "I/O2",
                            "path": "RM3 Pin 7 -> 373 Pin 7 (3D) -> 66K Pin 4 (AD2) -> IC9 Pin 13",
                            "note": ""
                        },
                        {
                            "pin": "Pin 14",
                            "signal": "GND",
                            "path": "ROM Pin 20 (/CE) -> FT -> 373 Pin 10 (GND) -> FT -> 373 Pin 1 (/OE)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 15",
                            "signal": "I/O3",
                            "path": "RM3 Pin 6 -> 373 Pin 8 (4D) -> 66K Pin 5 (AD3) -> IC9 Pin 14",
                            "note": ""
                        },
                        {
                            "pin": "Pin 16",
                            "signal": "I/O4",
                            "path": "373 Pin 18 (8D) -> 66K Pin 6 (AD4) -> IC9 Pin 15",
                            "note": ""
                        },
                        {
                            "pin": "Pin 17",
                            "signal": "I/O5",
                            "path": "373 Pin 17 (7D) -> 66K Pin 7 (AD5) -> IC9 Pin 16",
                            "note": ""
                        },
                        {
                            "pin": "Pin 18",
                            "signal": "I/O6",
                            "path": "373 Pin 13 (5D) -> 66K Pin 8 (AD6) -> IC9 Pin 17",
                            "note": ""
                        },
                        {
                            "pin": "Pin 19",
                            "signal": "I/O7",
                            "path": "373 Pin 14 (6D) -> 66K Pin 9 (AD7) -> IC9 Pin 18",
                            "note": ""
                        },
                        {
                            "pin": "Pin 20",
                            "signal": "/CE",
                            "path": "ROM Pin 14 (GND) -> FT -> 373 Pin 10 (GND) -> FT -> 373 Pin 1 (/OE)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 21",
                            "signal": "A10",
                            "path": "FT -> 66K Pin 12 (A10)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 22",
                            "signal": "/OE",
                            "path": "C29 -> R39 (on the back of the board) -> 66K Pin 25 (/PSEN)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 23",
                            "signal": "A11",
                            "path": "FT -> 66K Pin 13 (A11)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 24",
                            "signal": "A9",
                            "path": "FT -> 66K Pin 11 (A9)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 25",
                            "signal": "A8 ",
                            "path": "FT -> 66K Pin 10 (A8 )",
                            "note": ""
                        },
                        {
                            "pin": "Pin 26",
                            "signal": "A13",
                            "path": "66K Pin 15 (A13)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 27",
                            "signal": "A14",
                            "path": "66K Pin 16 (A14)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 28",
                            "signal": "VCC",
                            "path": "ROM Pin 1 (/WE) -> C49 -> 373 Pin 20 (VCC)",
                            "note": ""
                        }
                    ]
                }
            ]
        },
        {
            "id": "usdm-p28-p05",
            "label": "USDM P28 / P05",
            "groups": [
                {
                    "label": "373 latch",
                    "rows": [
                        {
                            "pin": "Pin 1",
                            "signal": "/OE",
                            "path": "373 Pin 10 -> ROM Pin 14 (GND)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 2",
                            "signal": "1Q",
                            "path": "ROM Pin 10 (A0)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 3",
                            "signal": "1D",
                            "path": "RM3 Pin 2 -> ROM Pin 11 (I/O0) -> 66K Pin 1 (AD0)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 4",
                            "signal": "2D",
                            "path": "RM3 Pin 3 -> ROM Pin 12 (I/O1) -> 66K Pin 2 (AD1)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 5",
                            "signal": "2Q",
                            "path": "ROM Pin 9 (A1)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 6",
                            "signal": "3Q",
                            "path": "ROM Pin 8 (A2)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 7",
                            "signal": "2D",
                            "path": "RM3 Pin 4 -> ROM Pin 13 (I/O2) -> 66K Pin 3 (AD2)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 8",
                            "signal": "2D",
                            "path": "RM3 Pin 5 -> ROM Pin 15 (I/O3) -> 66K Pin 4 (AD3)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 9",
                            "signal": "4Q",
                            "path": "ROM Pin 7",
                            "note": ""
                        },
                        {
                            "pin": "Pin 10",
                            "signal": "GND",
                            "path": "373 Pin 1 -> ROM Pin 14 (GND)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 11",
                            "signal": "LE",
                            "path": "66K Pin 22 (ALE)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 12",
                            "signal": "5Q",
                            "path": "ROM Pin 4 (A6)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 13",
                            "signal": "5D",
                            "path": "RM3 Pin 8 -> ROM Pin 18 (I/O6) -> 66K Pin 7 (AD6)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 14",
                            "signal": "6D",
                            "path": "RM3 Pin 9 -> ROM Pin 19 (I/O7) -> 66K Pin 8 (AD7)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 15",
                            "signal": "6Q",
                            "path": "ROM Pin 3 (A7)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 16",
                            "signal": "7Q",
                            "path": "ROM Pin 5 (A5)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 17",
                            "signal": "7D",
                            "path": "RM3 Pin 7 -> ROM Pin 17 (I/O5) -> 66K Pin 6 (AD5)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 18",
                            "signal": "8D",
                            "path": "RM3 Pin 6 -> ROM Pin 16 (I/O4) -> 66K Pin 5 (AD4)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 19",
                            "signal": "8Q",
                            "path": "ROM Pin 6 (A4)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 20",
                            "signal": "VCC",
                            "path": "ROM Pin 28 (VCC) -> ROM Pin 1 (/WE)",
                            "note": ""
                        }
                    ]
                },
                {
                    "label": "ROM socket",
                    "rows": [
                        {
                            "pin": "Pin 1",
                            "signal": "VCC",
                            "path": "ROM Pin 28 (VCC) -> 373 Pin 20 (VCC)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 2",
                            "signal": "A12",
                            "path": "66K Pin 13 (A12)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 3",
                            "signal": "A7",
                            "path": "373 Pin 15 (6Q)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 4",
                            "signal": "A6",
                            "path": "373 Pin 12 (5Q)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 5",
                            "signal": "A5",
                            "path": "373 Pin 16 (7Q)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 6",
                            "signal": "A4",
                            "path": "373 Pin 19 (8Q)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 7",
                            "signal": "A3",
                            "path": "373 Pin 9 (4Q)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 8",
                            "signal": "A2",
                            "path": "373 Pin 6 (3Q)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 9",
                            "signal": "A1",
                            "path": "373 Pin 5 (2Q)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 10",
                            "signal": "A0",
                            "path": "373 Pin 2 (1Q)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 11",
                            "signal": "I/O0",
                            "path": "RM3 Pin 2 -> 373 Pin 3 (1D) -> 66K Pin 1 (AD0)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 12",
                            "signal": "I/O1",
                            "path": "RM3 Pin 3 -> 373 Pin 4 (2D) -> 66K Pin 2 (AD1)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 13",
                            "signal": "I/O2",
                            "path": "RM3 Pin 4 -> 373 Pin 7 (3D) -> 66K Pin 3 (AD2)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 14",
                            "signal": "GND",
                            "path": "373 Pin 10 (GND) -> 373 Pin 1 (/OE)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 15",
                            "signal": "I/O3",
                            "path": "RM3 Pin 5 -> 373 Pin 8 (4D) -> 66K Pin 4 (AD3)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 16",
                            "signal": "I/O4",
                            "path": "RM3 Pin 6 -> 373 Pin 18 (8D) -> 66K Pin 5 (AD4)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 17",
                            "signal": "I/O5",
                            "path": "RM3 Pin 7 -> 373 Pin 17 (7D) -> 66K Pin 6 (AD5)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 18",
                            "signal": "I/O6",
                            "path": "RM3 Pin 8 -> 373 Pin 13 (5D) -> 66K Pin 7 (AD6)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 19",
                            "signal": "I/O7",
                            "path": "RM3 Pin 9 -> 373 Pin 14 (6D) -> 66K Pin 8 (AD7)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 20",
                            "signal": "/CE",
                            "path": "R54 (and the other side of R54 is connected to GND)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 21",
                            "signal": "A10",
                            "path": "66K Pin 11 (A10)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 22",
                            "signal": "/OE",
                            "path": "R49 -> 66K Pin 23 (/PSEN)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 23",
                            "signal": "A11",
                            "path": "66K Pin 12 (A11)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 24",
                            "signal": "A9",
                            "path": "66K Pin 10 (A9)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 25",
                            "signal": "A8",
                            "path": "66K Pin 9 (A8 )",
                            "note": ""
                        },
                        {
                            "pin": "Pin 26",
                            "signal": "A13",
                            "path": "66K Pin 14 (A13)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 27",
                            "signal": "A14",
                            "path": "66K Pin 15 (A14)",
                            "note": ""
                        },
                        {
                            "pin": "Pin 28",
                            "signal": "VCC",
                            "path": "ROM Pin 1 (/WE) -> 373 Pin 20 (VCC)",
                            "note": ""
                        }
                    ]
                }
            ]
        }
    ]
}
```

## Source notes and uncertainties

> [!IMPORTANT]
> The JDM P30-901 latch list labels latch pins 7 and 8 as `2D`, while the corresponding ROM-socket list labels those connections as `3D` and `4D`. The searchable data preserves the archived labels and flags the contradiction instead of silently correcting it.

- The JDM P30-901 list was recorded on December 28, 2004.
- The USDM P28/P05 list was recorded on November 14, 2005.
- The source says the P05 mapping was validated later and that the ROM pin 20 resistor name was corrected to `R54`.
- Compatibility beyond the named ECUs was not confirmed in the archived source.

## Related

- [Introduction to ECU chipping](/cars/rom/introduction-to-ecu-chipping)
- [Chipping the JDM P30 ECU](/cars/rom/chipping-jdmp30)
- [OBD1 ECU hardware reference](/cars/ecu/ecu-hardware)
- [74HC373 latch reference](/cars/rom/74hc373)
