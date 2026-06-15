---
summary: 'Rom Maps An area to collaborate on all the memory addresses found in ROMs Rom Maps OBD1 Civic and Integra ECUs Memory Locations Programming Resources Other...'
tags: [ecu, reference, tuning, rom, sensors, wiring, conversion, diagnostics]
applies_to:
  obd: [0, 1]
  brand: Acura/Honda
  models: [civic, crx, del-sol, integra, prelude]
  chassis: [bb, da, dc2, ef, eg, eg-eh, ek]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Rom Maps'
    url: /pgmfi/wiki/library/rom-maps
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# ROM Maps

##  Rom Maps 

An area to collaborate on all the memory addresses found in [ROM](/cars/rom/rom)s - Rom Maps
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

###  [OBD](/cars/wiring/obd)1 Civic and Integra [ECU](/cars/ecu/ecu)s 

*[OBD1 Civic Integra ECUs](/cars/diagnostics/obd1-civic-integra-ec-us) share a lot of features*####  Memory Locations 

- [P28](/cars/sensors/p28) - [ROM](/cars/rom/rom)s based on the [USDM](/cars/sensors/usdm) 304 P28 (92-95 Civic D16Z6 [SOHC](/cars/sensors/sohc) VTEC)
- [P30](/cars/sensors/p30) - [ROM](/cars/rom/rom)s based on the [JDM](/cars/sensors/jdm) 203 P30 (Civic B16A [DOHC](/cars/sensors/dohc) VTEC)
- [P72](/cars/sensors/p72) - [ROM](/cars/rom/rom)s based on the [USDM](/cars/sensors/usdm) 273 P72 (Integra B18C1-3 [DOHC](/cars/sensors/dohc) VTEC)
- [Uber P72](/cars/rom/uber-p72) - [ROM](/cars/rom/rom)s based on Blakes [Uber Data ERM](/cars/rom/uber-data-erm) code
- [Hi Res P72](/cars/rom/hi-res-p72) - [ROM](/cars/rom/rom)s based on John Cui's custom high resolution [P72](/cars/sensors/p72) code

####  Programming Resources 

- [ASM662](/cars/diagnostics/asm662) - can be used to assemble and disassemble these [ROM](/cars/rom/rom)s.
- [OBD1 Conversion Formulae](/cars/wiring/obd1-conversion-formulae) - can be used to convert values found in these [ROM](/cars/rom/rom)s to real-world values.
- [OBD1 Code Compatibility](/cars/wiring/obd1-code-compatibility) - describes the various ways you can run code in an [ECU](/cars/ecu/ecu) other than what was intended.
- Some [66k Assembler Routines](/cars/sensors/66k-assembler-routines) - have been commented, and you can look at the commented [OBD1 Civ Teg Routines](/cars/rom/obd1-civ-teg-routines).
- [Auto Or Manual](/cars/diagnostics/auto-or-manual) - There is an interaction between hardware and software to determine transmission behavior.

###  Other [OBD](/cars/wiring/obd)1 

*Everything else [OBD](/cars/wiring/obd)1 - usually `66207` based [MCU](/cars/rom/mcu)s*####  Memory Locations 

- [P13](/cars/sensors/p13) - The [JDM](/cars/sensors/jdm)/USDM H22 (92-95 Prelude [DOHC](/cars/sensors/dohc) VTEC).

###  [OBD](/cars/wiring/obd)0 VTEC ECUs 

*[OBD0 VTEC ECUs](/cars/diagnostics/obd0-vtec-ec-us) [ECU](/cars/ecu/ecu)s share a lot of features*####  Memory Locations 

- [PW0](/cars/sensors/pw0) - [ROM](/cars/rom/rom)s based on the PW0 [JDM](/cars/sensors/jdm) (89-91 CRX/Civic EF8/9 B16A) but also included is some of the Euro PW0 locations.
- [PR3](/cars/sensors/pr3) - [ROM](/cars/rom/rom)s based on the PR3 [JDM](/cars/sensors/jdm) (89-91 Integra XSi B16A)
- [ASM662](/cars/diagnostics/asm662) - can be used to assemble and disassemble these [ROM](/cars/rom/rom)s.
- OBD0 VTEC Routines - have yet to be written.

###  [OBD](/cars/wiring/obd)0 Multi-Point Fuel-Injected 

*[OBD0 MPFI](/cars/diagnostics/obd0mpfi) [ECU](/cars/ecu/ecu)s share a lot of features*####  Memory Locations 

- [91 PM6](/cars/diagnostics/91pm6) - [ROM](/cars/rom/rom)s based on the 91 PM6 ([USDM](/cars/sensors/usdm) CRX/Civic Si w/ [SOHC](/cars/sensors/sohc) D16A6)
- 91 PR4_PA - [ROM](/cars/rom/rom)s based on the [USDM](/cars/sensors/usdm) 90-91 PR4 with internal PA sensor
- 90 PR4_no_PA - [ROM](/cars/rom/rom)s based on the [USDM](/cars/sensors/usdm) 90-91 PR4 w/ external PA sensor
- [91 PM7](/cars/sensors/91pm7) - Although very similar to the 91 PM6, George Ricketts and others have done a lot of development with the PM7

####  Programming Resources 

- [OBD0 PM6 PM7 RAM_Locations](/cars/rom/obd0pm6pm7ram-locations) - the PM6 and PM7 code seems to store important values in really similar [RAM](/cars/reference/ram) locations.
- [OBD0 Conversion Formula](/cars/wiring/obd0-conversion-formula) - can be used to convert values found in these [ROM](/cars/rom/rom)s to real world values.
- [OBD0 Code Compatibility](/cars/diagnostics/obd0-code-compatibility) - details what code can be swapped into which [ECU](/cars/ecu/ecu)s.
- OBD0 MPFIRoutines - are often shared between [ECU](/cars/ecu/ecu)s.
- [Intel8051](/cars/rom/intel8051) - assembler/disassemblers can be used with these [ROM](/cars/rom/rom)s.

###  External Resources 

- A webpage with some of the [ROM](/cars/rom/rom) locations and formulas is [here](http://web.archive.org/web/20120411164611/http://ef-honda.com:80/ben/locations.html).
