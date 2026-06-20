---
title: Honda OBD0/1 ECU Component List
summary: 'Reference of the components on Honda/Acura OBD0 and OBD1 ECU boards: IDs, types, specs, and repair notes.'
tags: [ecu, components, obd0, obd1, pcb, hardware, repair]
applies_to:
  make: [honda, acura]
  models: [accord, civic, crx, del-sol, integra, prelude, nsx, legend]
  chassis: [da, ef, ba, cb, eg, eh, ej, dc, bb, cd, na1]
complexity: advanced
---

# Honda OBD0/1 ECU Component List

A reference list of the physical components populating Honda and Acura **OBD0** and **OBD1** ECU
circuit boards, compiled from various sources. For every board reference designator (ID) it records the
component type, electrical specs, and repair notes, along with which ECU board(s) the part appears on.
It is intended as a bench reference for ECU repair, recapping, and reverse-engineering across the
OBD0/OBD1 era of Honda/Acura engine management.

> [!NOTE]
> This list was originally maintained as a community project. To contribute a correction or a missing
> part, open a pull request or issue on [GitHub](https://github.com/hondatabase/ecucomponents). The
> source board photographs are archived in the files collection under
> [ecu-components/componentlist](https://files.hondabase.com/browse/ecu-components/componentlist).

## Board legend

Components are mapped to the ECU board revision(s) they appear on. A blank board column means the part
is common across the boards (or the board has not been recorded).

- **OBD0:** N/A
- **OBD1:** `11F0`, `1720`, `1980` (with some `1820` references)

## Components

| ID(s) | Type | Specs | Notes | Board(s) |
|-------|------|-------|-------|----------|
| `BR2, BR3, BR4, BR5` |  |  | Empty |  |
| `BR1, R69` | Jumper/Resistor | `(0 OHM)` |  |  |
| `C14` | Condenser | `(220 uF) (35 V)` | Low ESR RADIAL HF |  |
| `C15, C19, C21` | Condenser | `(33 uF) (35 V)` | Low ESR RADIAL HF |  |
| `C18` | Condenser | `(220 uF) (10 V)` | Low ESR RADIAL HF |  |
| `C201` | Condenser | `(100 uF) (35 V)` | Low ESR RADIAL HF |  |
| `C24` | Condenser | `(47 uF) (10 V)` | Low ESR RADIAL HF |  |
| `C26, C30, C37` | Capacitor | `(33 uF) (35 V)` | Low ESR RADIAL HF |  |
| `C28` | Capacitor | `(330 uF) (35 V)` | Main / Low ESR RADIAL HF |  |
| `C31, C36, C47` | Capacitor | `(470 uF) (10 V)` | Low ESR RADIAL HF |  |
| `C40` | Condenser | `(100 uF) (10 V)` | Low ESR RADIAL HF |  |
| `C71` | Capacitor |  |  |  |
| `C49, C50` | Capacitor | `Surface mount, (0.004 uF)` | JDM and alike ECU |  |
| `C51, C52` | Capacitor | `(0.1 uF)` | Non-polarized capacitor, 104 marking. Non-polarized capacitor. |  |
| `C56, C57` | Capacitor | `(100 pF Ceramic)` | Digital Test Circuit |  |
| `C58, C59` | Capacitor | `(100 pF Ceramic)` | Digital Test Circuit |  |
| `C60` | Capacitor | `(1 uF Polar) (+/- 35 V)` | Check Polarity! |  |
| `C65` | Capacitor |  | External compensation of the O2 sensor |  |
| `C72, C74, C75, C89` | Capacitor | `Ceramic disk, (2.2 pF)` |  |  |
| `C86` | Capacitor |  | External barometric sensor |  |
| `C87` | Capacitor | `Ceramic .01 (103)` | PSP Related |  |
| `C91, C92` | Capacitor | `Surface mount, (0.00001 uF)` | JDM and alike ECU |  |
| `C94` | Capacitor | `TANTALIUM, (4.7 uF)` |  |  |
| `CM1` |  | `C103Z` | 7 Pins |  |
| `CN2` | Pin Header | `Datalog` | 1234 = GND/RX/5V/TX. 2.54 DIP 4 pin, 2.54 mm between pins, 3 mm length |  |
| `CN3` | SOLDER PORT |  | Related to Datalogging |  |
| `D1, R6` |  |  | A/T, Gear input 4 |  |
| `D10` | Rectifier Diode | `sf34, RM4Z/RG4Z grey RU4Z red` | EGR Valve Protection (SANKEN) |  |
| `D11` | Diode | `1N4001 (50 V)` | VTEC with high switch SK5151S | `11F0, 1720, 1980` |
| `D3, D7` | Diode | `1N4001` |  |  |
| `D14` | Zener Diode | `1N5230BTR (4.7 V), 1N5261BTR (4.7 V)` | Must be under the Transistor C-E voltage | `11F0` |
| `D20` | Protector |  | External BARO sensor |  |
| `D24` | Sanken Rectifier Diode | `RU4Z red` | EGR Valve Protection |  |
| `D26` |  | `JDM?` | MIL CHECK LIGHT |  |
| `D34` |  | `USDM?` | MIL CHECK LIGHT |  |
| `D4` | Diode |  | (Input) Gear 3 in A/T ECU |  |
| `D5` | Diode | `SR4418/SR4416 1.5KE27A` | Digital to analog (DAC) |  |
| `D6` | Supressor | `1AZ24/1.5KE20A, (21 V)` | Protects IC17 (circuit, very rare to mount.) |  |
| `DM1, DM2, DM3` | Transistor | `S233 IT` |  |  |
| `DM11, DM7, DM8, DM9` | Transistor | `S235 IT` |  |  |
| `DM4` | Transistor | `S233 IT` | PSP - Related - Double Diode to prevent overload on circuit. |  |
| `HIC1` |  | `AH1-D` |  |  |
| `HIC3` |  | `D IS168 8P17` | BAROMETRIC sensor. Little hole in it |  |
| `IC1` |  | `OKI M66X301` | Main Processor |  |
| `IC11` |  | `Current measurement circuit` | IACV |  |
| `IC12` | High-side Switch | `SK3001S` |  |  |
| `IC13` | High-side switch | `Same as Q37` | Safety switch/prevent VTEC on the CPU code fly away |  |
| `IC14` | High-side switch | `SK5050S / SK5151S / SI5151S / SI5151SG / IR-6220` | 5050 \> 5151 \> 5154 can be replaced with a bigger number, but not smaller due to power difference | `11F0, 1720, 1980` |
| `IC15` |  | `IDEM NR AS IC14 (wat?)` | A/T SWITCH. Up and down shift ic15+ic16 |  |
| `IC16` |  | `IDEM NR AS IC13 (wat?)` | A/T SWITCH. With solenoid gearbox valves |  |
| `IC17` |  | `TA8903SN` | Component for fuel pump and more.. @. R25 = RESET PULSE ON (HONDARULEZ\* BOOSTEDNW APOLLO) |  |
| `IC19` | Integrated Switch | `TOSHIBA TA8001S` |  |  |
| `IC22` |  | `M51945BL` |  |  |
| `IC3` | EEPROM Memory | `OKI M38256AP` | (256/512) 28 PIN. SST/ATMEL/27C,SF/ 29C,SF dip 2.54 and PLCC options. PLCC32 to 28 dip. MTP ALSO. You need a socket for it. |  |
| `IC4` | Integrated Circuit | `74HC373 / MC74HC373N / MM74HC373` | 20 PIN. You need a socket for it |  |
| `IC5` | Integrated Switch Circuit | `TOSHIBA TA7900S-D` |  |  |
| `J1` | Resistor | `(0.0 OHM)` | Must be bridged for the ECU to read from the EEPROM memory. |  |
| `J10` | Bridge |  | Must be bridged for IC14 to work | `11F0, 1980` |
| `J12` | Resistor | `(0.0 OHM)` | Must be cut/disconnected for datalog to work. |  |
| `PA1` |  | `D IS168` | BAROMETRIC SENSOR |  |
| `Q10, Q12, Q13, Q46` | PNP Transistor | `A143XSA` |  |  |
| `Q101` | PNP Transistor | `11FO BOARD P28,P06..A143XSZ FJN4305/NTE2368/` | PNP Transistor A1048/2SB1030, are with ECB pin holder (R4305)(dta) Transistors. | `11F0` |
| `Q102, Q103` | Transistor |  |  |  |
| `Q11` | Transistor | `NECB965 NPN (A143XSA)` | Green Color |  |
| `Q16` | PNP Transistor | `DTA143XSA` |  |  |
| `Q17` | PNP Transistor | `A143XSA` | (A/T) INTERLOCK/IAB\* INTAKE AIR BUTTERFLY | `1980` |
| `Q20` | PNP Transistor | `A143XSA/B1030/2SB1030` | PWM Digital |  |
| `Q21` | Transistor | `NEC 01594` | IACV |  |
| `Q22, Q23, Q24, Q25, Q43, Q44` | PNP Transistor | `DTA144, A144 dta144xsa/esa NTE2361` | Digital Test Circuit |  |
| `Q26` | NPN Transistor | `2SC2785/2SD1423` |  | `1720, 1820` |
| `Q27, Q28` | NPN Transistor | `2SC2785` |  | `1720` |
| `Q29` | MOSFET Transistor | `(10 A) (60 V) (75 W)` | MJE3055T PWM |  |
| `Q3` | NPN Transistor | `NEC 2SD1779` | IAT |  |
| `Q30` | NPN Transistor | `Built-in bias resistor` | AIL4L on the "1720 BOARD". Replacement: "FJN3302RTA". DTC144XSC on the "11FO BOARD". Option to D14 A/F 5V reading. | `11F0, 1720` |
| `Q31` | SANKEN Transistor | `D1796 / 2SD1780 (RACT-ND)` | EVAP (PCS) - Black Color.; From \<b\>Jason Katman\</b\>: 'A common component that burns up when you have the EVAP purge solenoid mis-plugged into the IAT sensor. It doesn’t usually throw a CEL code unless the IAT melts pretty bad. I’d pull your IAT off and see if the tip has melted.' |  |
| `Q34, R135` |  | `R135 is (10 OHM) (0.25 W)` | (A/T) Q17/Q34 output together. |  |
| `Q35` | NPN Transistor | `C124XSZ` |  |  |
| `Q36` | NPN Transistor | `C3225 1K` |  |  |
| `Q37` | NPN Transistor | `Digital SK5151 high side switch` | Prevents ROM disappearing. 2SD1430/2SC2785\* P28/P06. 2SD1423 P30 C2785\*. D1423/C2785 on board 1980 | `1980, 11F0` |
| `Q38` | NPN Transistor | `C2240 GR1K` | Ignition | `11F0, 1720` |
| `Q39` | NPN Transistor | `C144ESA` | Ignition | `11F0, 1720` |
| `Q4` | Transistor | `B1068` |  | `1720` |
| `Q41` | PNP Transistor | `A1175` | PSP RELATED SWITCH | `11F0` |
| `Q42` | NEC Transistor | `A1442` | Green Color | `11F0` |
| `Q45` | Transistor | `J103GR1` |  |  |
| `Q6, Q7, Q8, Q9` | PNP Transistor | `Integrated bias resistor (resistor or Transistor?)` | A143 dta143xsa/NTE2362, digital Test Circuit |  |
| `QM1, QM2` | (Needs confirmation!) NPN Transistor Array/Sanken Module | `(Needs confirmation!) INJECTOR DRIVER/SLA4010` | (Needs confirmation!) SK STA460C - Black Color/MULTY PIN |  |
| `QM3` | NPN Transistor Array | `FUEL PUMP DRIVER SK STA413A` | FLR, ACC, 02HTR, FANC.. |  |
| `R4` | Resistor | `(10k OHM) (0.25 W)` | Vref input OPamp |  |
| `R5` | Resistor |  | Input resistor for the O2 input |  |
| `R23` | Resistor | `(10k OHM) (0.25 W)` | For digital Test Circuit |  |
| `R25` | Resistor |  | Reset pulse for TA8903SN |  |
| `R52` | Resistor | `(1.2k OHM) (0.25 W)` |  |  |
| `R54` | Resistor | `(1k OHM) (1/4 W - needs confirmation)` |  |  |
| `R66, R67` | Resistor | `(820 OHM) (0.25 W)` |  |  |
| `R70` | Resistor | `(220 OHM) (0.25 W)` | EGR boost control output. |  |
| `R71` | Resistor | `(330 OHM) (0.25 W)` | EGR solenoid between the wastegate and turbo cold side/not after the TB. |  |
| `R75, R76, R77` | Resistor |  | CEL light |  |
| `R85` | Resistor |  | External compensation of the O2 sensor |  |
| `R89` | Resistor | `(10k OHM) (0.25 W)` | Starter signal |  |
| `R90, R93, R97` | Resistor |  |  |  |
| `R94` | Resistor |  | Part of the starter input |  |
| `R98` | Resistor |  | External barometric sensor |  |
| `R99, R101` | Resistor | `22K OHM` | PSP Related - To correct idle |  |
| `R100, R102` | Resistor | `4K7 OHM` | PSP Related - Idle when used steering wheel |  |
| `R103, R104, R105, R106` | Resistor | `(3.3k OHM) (0.25 W)` | Digital Test Circuit |  |
| `R107` | Resistor | `(220 OHM) (1/4 W)` |  |  |
| `R109, R116, R140, R141` |  |  | Knock Board related |  |
| `R136` | Resistor 1 |  | Pull up 1+2. For setting the (default v)oltage on input if sensor not present/voltage set. |  |
| `R137` | Resistor 3 |  | ELD input |  |
| `R138` | Resistor 2 |  | Pull down |  |
| `R142` | Resistor | `(10k OHM) (0.25 W)` |  | `1980` |
| `R143` | Resistor | `(51K OHM) (0.25 W)` | Not sure about 51K OHM... | `1980` |
| `R144` | Resistor | `(12k OHM) (0.25 W)` |  | `1980` |
| `R201` | Resistor | `(10k OHM) (0.25 W)` | Most of the times present in all ECUs | `11F0` |
| `RM1` |  | `M-5431 00` |  |  |
| `RM10` | Resistor Array | `(2.2k OHM)` | 2.54 DIP 6 pin |  |
| `RM11` | Resistor | `2.54 DIP 8 pin (resistor board)` | VTEC Activation. PIN 1/2 (10k OHM), PIN 2/3 (51k OHM), PIN 3/8 (12k OHM) | `11F0, 1720` |
| `RM3, RM13` | Resistor Array | `(10k OHM)` | 2.54 DIP 9 pin |  |
| `RM2, RM4` | Resistor Array | `(4.7k OHM)` | IACV. Current measurement circuit? |  |
| `RM7` |  | `M-5432 07` |  |  |
| `RM8` |  | `6E223/152J` | 2.54 DIP 7 pin |  |
| `RP17` | Resistor | `(1.5k OHM)` | A/T - Resistor 2X (RP17 + RP18) |  |
| `RP18` | Resistor | `(0 OHM)` |  |  |
| `XTL1` |  | `10akss4b, 10 MHz / 7.90KSSOG, 7.90 Mhz` | Quartz Crystal Resonator. Specs need to be confirmed. |  |
| `XTL2` |  | `500E, CSB (Control Station Board)?` |  |  |