---
summary: 'There are a number of programs that enable you to log data about how your engine is working by reading information out of the ECU.'
applies_to:
  obd: [0, 1, 2]
complexity: advanced
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - wiring
  - conversion
---

# How Does Data Logging Work

There are a number of programs that enable you to log data about how your engine is working by reading information out of the [ECU](/cars/electronics/ecu). For my [OBD](/cars/electronics/obd)1 [ECU](/cars/electronics/ecu)s, I use CROME Pro or Freelog software on my PC to log what is going on. These software packages use a serial port on the PC (sometimes implemented with a USB adapter) to send commands to and receive data from the [ECU](/cars/electronics/ecu). There is a ton of information on this wiki about how to set up your [ECU](/cars/electronics/ecu) to be able to communicate with the PC. Basically, you need to hook the [ECU](/cars/electronics/ecu)'s transmitter to the PC's receiver and you need to hook the [ECU](/cars/electronics/ecu)'s receiver to the PC's transmitter. The [ECU](/cars/electronics/ecu) serial works at [TTL](/cars/electronics/ttl) voltage levels and most serial ports work with RS232 voltage levels so some sort of signal translator must be used. Once the serial port hardware is operational, you need to replace the software that controls the [ECU](/cars/electronics/ecu)'s serial port with software that controls the serial port in such a way that it can talk with the software on the PC. I use John Cui's data logging plugin in CROME to install this software patch into the [ECU](/cars/electronics/ecu) binary (program) that I want to log. That binary is programmed into a flash or [EPROM](/cars/electronics/eprom) memory chip and installed in the [ECU](/cars/electronics/ecu) in the car. Once the engine is running with the modified [ECU](/cars/electronics/ecu) and the PC logging software is running and the two are communicating with `each` other, you can start data logging. When you tell the PC software to start datalogging, the PC software starts sending commands to the [ECU](/cars/electronics/ecu). The datalogging software added to the [ECU](/cars/electronics/ecu) binary receives `each` command, interprets it and returns the results, which the PC software then adds to a log file. Typically one command is used to get one piece of data from the [ECU](/cars/electronics/ecu). With John Cui's data logger patch, for example, there are standard commands for getting data that most people want to get such as [RPM](/cars/electronics/rpm), O2 sensor readings, MAP sensor readings, etc. There are also commands that allow you to read any [RAM](/cars/electronics/ram) location for logging less frequently logged data. The data logging software on the PC just steps through all of the commands to get the data you want, and then repeats the same sequence over and over as fast as the PC can run. After logging the data from your car while it is running under different loads, you can use that data to figure out how to change many operational characteristics of the [ECU](/cars/electronics/ecu) software, such as the fuel and ignition maps. This is done with Rom editor software such as CROME for [OBD](/cars/electronics/obd)1 [ECU](/cars/electronics/ecu)s. -- markolson - 24 Oct 2005
