---
summary: 'Rom Maps An area to collaborate on all the memory addresses found in ROMs Rom Maps OBD1 Civic and Integra ECUs Memory Locations Programming Resources Other...'
applies_to:
  obd: [0, 1]
  brand: Acura/Honda
complexity: advanced
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - wiring
  - conversion
  - diagnostics
---

# ROM Maps

##  Rom Maps 

An area to collaborate on all the memory addresses found in [ROM](/cars/electronics/rom)s - Rom Maps
    - OBD1 Civic and Integra ECUs
        - Memory Locations
        - Programming Resources
    - Other OBD1
        - Memory Locations
    - OBD0 VTEC ECUs
        - Memory Locations
    - OBD0 Multi-Point Fuel-Injected
        - Memory Locations
        - Programming Resources
    - External Resources

###  [OBD](/cars/electronics/obd)1 Civic and Integra [ECU](/cars/electronics/ecu)s 

*[OBD1 Civic Integra ECUs](/cars/electronics/obd1-civic-integra-ec-us) share a lot of features*####  Memory Locations 

- [P28](/cars/electronics/p28) - [ROM](/cars/electronics/rom)s based on the [USDM](/cars/electronics/usdm) 304 P28 (92-95 Civic D16Z6 [SOHC](/cars/electronics/sohc) VTEC)
- [P30](/cars/electronics/p30) - [ROM](/cars/electronics/rom)s based on the [JDM](/cars/electronics/jdm) 203 P30 (Civic B16A [DOHC](/cars/electronics/dohc) VTEC)
- [P72](/cars/electronics/p72) - [ROM](/cars/electronics/rom)s based on the [USDM](/cars/electronics/usdm) 273 P72 (Integra B18C1-3 [DOHC](/cars/electronics/dohc) VTEC)
- [Uber P72](/cars/electronics/uber-p72) - [ROM](/cars/electronics/rom)s based on Blakes [Uber Data ERM](/cars/electronics/uber-data-erm) code
- [Hi Res P72](/cars/electronics/hi-res-p72) - [ROM](/cars/electronics/rom)s based on John Cui's custom high resolution [P72](/cars/electronics/p72) code

####  Programming Resources 

- [ASM662](/cars/electronics/asm662) - can be used to assemble and disassemble these [ROM](/cars/electronics/rom)s.
- [OBD1 Conversion Formulae](/cars/electronics/obd1-conversion-formulae) - can be used to convert values found in these [ROM](/cars/electronics/rom)s to real-world values.
- [OBD1 Code Compatibility](/cars/electronics/obd1-code-compatibility) - describes the various ways you can run code in an [ECU](/cars/electronics/ecu) other than what was intended.
- Some [66k Assembler Routines](/cars/electronics/66k-assembler-routines) - have been commented, and you can look at the commented [OBD1 Civ Teg Routines](/cars/electronics/obd1-civ-teg-routines).
- [Auto Or Manual](/cars/electronics/auto-or-manual) - There is an interaction between hardware and software to determine transmission behavior.

###  Other [OBD](/cars/electronics/obd)1 

*Everything else [OBD](/cars/electronics/obd)1 - usually `66207` based [MCU](/cars/electronics/mcu)s*####  Memory Locations 

- [P13](/cars/electronics/p13) - The [JDM](/cars/electronics/jdm)/USDM H22 (92-95 Prelude [DOHC](/cars/electronics/dohc) VTEC).

###  [OBD](/cars/electronics/obd)0 VTEC ECUs 

*[OBD0 VTEC ECUs](/cars/electronics/obd0-vtec-ec-us) [ECU](/cars/electronics/ecu)s share a lot of features*####  Memory Locations 

- [PW0](/cars/electronics/pw0) - [ROM](/cars/electronics/rom)s based on the PW0 [JDM](/cars/electronics/jdm) (89-91 CRX/Civic EF8/9 B16A) but also included is some of the Euro PW0 locations.
- [PR3](/cars/electronics/pr3) - [ROM](/cars/electronics/rom)s based on the PR3 [JDM](/cars/electronics/jdm) (89-91 Integra XSi B16A)
- [ASM662](/cars/electronics/asm662) - can be used to assemble and disassemble these [ROM](/cars/electronics/rom)s.
- OBD0 VTEC Routines - have yet to be written.

###  [OBD](/cars/electronics/obd)0 Multi-Point Fuel-Injected 

*[OBD0 MPFI](/cars/electronics/obd0mpfi) [ECU](/cars/electronics/ecu)s share a lot of features*####  Memory Locations 

- [91 PM6](/cars/electronics/91pm6) - [ROM](/cars/electronics/rom)s based on the 91 PM6 ([USDM](/cars/electronics/usdm) CRX/Civic Si w/ [SOHC](/cars/electronics/sohc) D16A6)
- 91 PR4_PA - [ROM](/cars/electronics/rom)s based on the [USDM](/cars/electronics/usdm) 90-91 PR4 with internal PA sensor
- 90 PR4_no_PA - [ROM](/cars/electronics/rom)s based on the [USDM](/cars/electronics/usdm) 90-91 PR4 w/ external PA sensor
- [91 PM7](/cars/electronics/91pm7) - Although very similar to the 91 PM6, George Ricketts and others have done a lot of development with the PM7

####  Programming Resources 

- [OBD0 PM6 PM7 RAM_Locations](/cars/electronics/obd0pm6pm7ram-locations) - the PM6 and PM7 code seems to store important values in really similar [RAM](/cars/electronics/ram) locations.
- [OBD0 Conversion Formulas](/cars/electronics/obd0-conversion-formulas) - can be used to convert values found in these [ROM](/cars/electronics/rom)s to real world values.
- [OBD0 Code Compatibility](/cars/electronics/obd0-code-compatibility) - details what code can be swapped into which [ECU](/cars/electronics/ecu)s.
- OBD0 MPFIRoutines - are often shared between [ECU](/cars/electronics/ecu)s.
- [Intel8051](/cars/electronics/intel8051) - assembler/disassemblers can be used with these [ROM](/cars/electronics/rom)s.

###  External Resources 

- A webpage with some of the [ROM](/cars/electronics/rom) locations and formulas is [here](http://www.ef-honda.com/ben/locations.html).
