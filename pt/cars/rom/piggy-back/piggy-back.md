---
summary: 'Um controlador Piggyback é um dispositivo que é instalado "à boleia" (piggybacks) em cima da ECU. Os piggybacks intercetam os sinais vindos do motor e alteram-nos antes de chegarem à ECU.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
sources:
  - name: 'pgmfi.org wiki'
    title: 'Piggy Back'
    url: /pgmfi/wiki/library/piggy-back
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Piggyback

Um controlador [Piggyback](/cars/rom/piggy-back) é um dispositivo que funciona "à boleia" em cima da [ECU](/cars/ecu/ecu). Os piggybacks intercetam os sinais vindos do motor e alteram-nos antes de chegarem à [ECU](/cars/ecu/ecu). Os controladores piggyback mais abusados/utilizados incorretamente são os Apexi SAFC, VAFC, SAFC2 e VAFC2. O Greddy E-Manage é um grande e potente controlador piggyback "com esteroides". Podes pensar em muito do lixo que vem com o kit JRSC como um piggyback, pois a sua configuração de relés e tralha faz com que valores falsos de sensores sejam passados à [ECU](/cars/ecu/ecu).
