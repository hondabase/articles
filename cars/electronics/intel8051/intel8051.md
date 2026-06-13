---
summary: 'for all you could want to know and a great tutorial, go to http://www.8052.comAny 8051 assembler will work fine for coding.'
applies_to:
  obd: [0, 1, 2]
complexity: advanced
tags:
  - hardware
  - education
  - tuning
  - rom
  - sensors
  - reference
---

# Intel8051

for all you could want to know and a great tutorial, go to [http://www.8052.com](http://www.8052.com)Any 8051 assembler will work fine for coding. Sysrad51, available [here](http://www.systronix.com/RAD51/RAD51.exe) seems popular. Be careful when re-assembling a file after making changes to it... Sysrad seems to have some odd bugs in this regard. [Batronix](http://www.batronix.com) [Prog Studio](/cars/electronics/prog-studio) seems fairly popular too. [ASEM-51](http://plit.de/asem-51/download.htm) seems interesting. It has a couple companion IDEs, [MIDE](http://www.opcube.com/home.html) and [4Flash](http://reinerjansen.de/4flash/). Blundar's preferred development environment is now MIDE+ASEM-51. Note: make sure you have a colon ":" after all labels - ASEM51 is much pickier than SYSRAD. Dave Blundell modified [d51](http://www.8052.com/users/disasm/) to support Oki's non-standard use of [A5](/cars/electronics/a5) by creating [Pgmfi D51](/cars/electronics/pgmfi-d51). Chris Favreau compiled some windows binaries for it. You can download the source and linux/win binaries [here](/cars/electronics/pgmfi-d51). This looks like an interesting [8051 sim](http://home.t-online.de/home/Jens.Altmann/jsim-e.htm)Some 8051 resources:

- [Compact lil ref guide](http://myhome.naver.com/zxcv0070/chip/8051data%20book.htm)
- [Another compact ref](http://www.stack.nl/~wvengen/uni/elec/8051ref.pdf)
- [jEdit](http://jedit.org) - jEdit 4.2pre8 and higher includes a MCS51 syntax highlighting Edit Mode definition for 8051 assembly editing

| **Attachment:** | **Modify:** | **Size:** | **Date:** | **Who:** | **Comment:** | | :--- | :--- | :--- | :--- | :--- | :--- | | ![](/pgmfi/wiki/assets/icn/exe.gif) [RAD51.exe](RAD51.exe) | mod | 5891853 | 20 Jul 2004 - 04:21 | blundar | Copy of Sysrad51 as of 7/18/04 locally |
