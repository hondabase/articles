---
summary: "This formula is used to convert values in the high cam table scales to realworld RPMs. If ''x'' is an 8bit highcam scale RPM value, Hi Cam RPM(''x'') = 1875000''x'' / 53248 53248=D000h."
applies_to:
  obd: [1]
complexity: intermediate
tags:
  - ecu
  - reference
  - sensors
---

# OBD1 8bit High Cam RPM

This formula is used to convert values in the high cam table scales to real-world [RPM](/cars/electronics/rpm)s. If ''x'' is an 8-bit high-cam scale [RPM](/cars/electronics/rpm) value,

- Hi Cam RPM(''x'') = 1875000*''x'' / 53248

53248=`D000h`. Here is how it's calculated using standard integer fixed-point math tricks: | |MOV er2, `0ach`|; 0805 0 02 00 B5AC4A | |MOV er0, #`0d000h`|; 0808 0 02 00 449800D0 | |CLR A|; 080C 1 02 00 F9 | |DIV|; 080D 1 02 00 9037 | | |; DIV = (er0, A) <-- (er0, A) / er2; in this case, `0xd0000000` / (1875000/RPM) | | |; using bytes instead of words, (r1,r0,`Ah`,Al) <-- (r1,r0,`Ah`,Al) / (r5,r4) |||''... store the high bit of A, decide whether the divide overflowed, etc...'' | |LB A, r0|; 0817 0 02 00 78 | | |;r0 is the least significant byte of er0, which is the most significant word of the quotient! | |JNE label_081f|; 0818 0 02 00 CE05 |||''... overflow conditions, etc...'' |label_081f:|STB A, `0aah`|; 081F 0 02 00 D5AA
