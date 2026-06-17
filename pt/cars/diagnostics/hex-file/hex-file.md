---
summary: 'Um ficheiro "hex" é um ficheiro codificado no formato Intel Hex. O ficheiro Intel HEX é um ficheiro de texto ASCII com linhas de texto que seguem o formato de ficheiro Intel HEX.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - tuning
  - rom
  - sensors
  - reference
  - diagnostics
  - ecu
sources:
  - name: 'pgmfi.org wiki'
    title: 'Ficheiro Hex'
    url: /pgmfi/wiki/library/hex-file
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Ficheiro Hex

Um ficheiro "hex" é um ficheiro codificado no formato Intel Hex. O ficheiro Intel HEX é um ficheiro de texto ASCII com linhas de texto que seguem o formato de ficheiro Intel HEX. `Cada` linha num ficheiro Intel HEX contém um registo HEX. Estes registos são compostos por números hexadecimais que representam código de linguagem de máquina e/ou dados constantes. Os ficheiros Intel HEX são frequentemente utilizados para transferir o programa e os dados que seriam armazenados numa [ROM](/cars/rom/rom) ou [EPROM](/cars/rom/eprom). A maioria dos programadores ou emuladores de [EPROM](/cars/rom/eprom) pode utilizar ficheiros Intel HEX.
