---
summary: 'There are a number of programs that enable you to log data about how your engine is working by reading information out of the ECU.'
tags: [ecu, reference, tuning, rom, sensors, wiring, conversion]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'How Does Data Logging Work'
    url: /pgmfi/wiki/library/how-does-data-logging-work
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# How Does Data Logging Work

There are a number of programs that enable you to log data about how your engine is working by reading information out of the [ECU](/cars/ecu/ecu). For my [OBD](/cars/wiring/obd)1 [ECU](/cars/ecu/ecu)s, I use CROME Pro or Freelog software on my PC to log what is going on. These software packages use a serial port on the PC (sometimes implemented with a USB adapter) to send commands to and receive data from the [ECU](/cars/ecu/ecu). There is a ton of information on this wiki about how to set up your [ECU](/cars/ecu/ecu) to be able to communicate with the PC. Basically, you need to hook the [ECU](/cars/ecu/ecu)'s transmitter to the PC's receiver and you need to hook the [ECU](/cars/ecu/ecu)'s receiver to the PC's transmitter. The [ECU](/cars/ecu/ecu) serial works at [TTL](/cars/sensors/ttl) voltage levels and most serial ports work with RS232 voltage levels so some sort of signal translator must be used. Once the serial port hardware is operational, you need to replace the software that controls the [ECU](/cars/ecu/ecu)'s serial port with software that controls the serial port in such a way that it can talk with the software on the PC. I use John Cui's data logging plugin in CROME to install this software patch into the [ECU](/cars/ecu/ecu) binary (program) that I want to log. That binary is programmed into a flash or [EPROM](/cars/rom/eprom) memory chip and installed in the [ECU](/cars/ecu/ecu) in the car. Once the engine is running with the modified [ECU](/cars/ecu/ecu) and the PC logging software is running and the two are communicating with `each` other, you can start data logging. When you tell the PC software to start datalogging, the PC software starts sending commands to the [ECU](/cars/ecu/ecu). The datalogging software added to the [ECU](/cars/ecu/ecu) binary receives `each` command, interprets it and returns the results, which the PC software then adds to a log file. Typically one command is used to get one piece of data from the [ECU](/cars/ecu/ecu). With John Cui's data logger patch, for example, there are standard commands for getting data that most people want to get such as [RPM](/cars/sensors/rpm), O2 sensor readings, MAP sensor readings, etc. There are also commands that allow you to read any [RAM](/cars/reference/ram) location for logging less frequently logged data. The data logging software on the PC just steps through all of the commands to get the data you want, and then repeats the same sequence over and over as fast as the PC can run. After logging the data from your car while it is running under different loads, you can use that data to figure out how to change many operational characteristics of the [ECU](/cars/ecu/ecu) software, such as the fuel and ignition maps. This is done with Rom editor software such as CROME for [OBD](/cars/wiring/obd)1 [ECU](/cars/ecu/ecu)s. -- markolson - 24 Oct 2005
