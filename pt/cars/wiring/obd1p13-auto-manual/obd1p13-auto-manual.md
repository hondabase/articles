---
summary: 'A maioria das ECU Automáticas tem uma ponte (jumper) em RP11 e um espaço em branco em RP12. Mova RP11 para RP12 e passará a ter uma ECU Manual.'
applies_to:
  obd: [1]
complexity: beginner
tags:
  - ecu
  - reference
  - sensors
  - wiring
  - conversion
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD1P13 Auto Manual'
    url: /pgmfi/wiki/library/obd1p13-auto-manual
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1P13 Auto Manual

A maioria das ECUs Automáticas tem uma ponte (jumper) em RP11 e um espaço em branco em RP12. Mova RP11 para RP12 e passará a ter uma [ECU](/cars/ecu/ecu) Manual. Aqui está um grande plano da configuração de jumpers [JDM](/cars/sensors/jdm): as pontes de transmissão automática [Auto Jumpers](/pgmfi/wiki/media/library/P13/JDM-p13-resistors.jpg) `R96`, `C49` e `R82` parecem estar relacionadas com alguns controlos de transmissão automática, mas podem ser deixadas no sítio. Algumas [ECU](/cars/ecu/ecu)s (como a [JDM P13-900](/pgmfi/wiki/media/library/P13/P13-900_jumpers.jpg)) têm resistências em ambos os sítios. Pode simplesmente remover ambas e substituir RP12 por um fio de ponte (jumper wire). Isto aplica-se a todas as [ECU](/cars/ecu/ecu)s que partilham a mesma placa (P11, P12, P13, P14 e P39).
