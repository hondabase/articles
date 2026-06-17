---
summary: 'Há pessoas a trabalhar numa ROM onde a ECU ativa o solenoide de nitroso em vez do habitual interruptor WOT.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - nitrous
sources:
  - name: 'pgmfi.org wiki'
    title: 'ECU Nitrous Control'
    url: /pgmfi/wiki/library/ecu-nitrous-control
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Controlo de Óxido Nitroso pela ECU

Há pessoas a trabalhar numa [ROM](/cars/rom/rom) onde a [ECU](/cars/ecu/ecu) ativa o solenoide de óxido nitroso em vez do habitual interruptor [WOT](/cars/reference/wot) (Wide Open Throttle). A principal vantagem disto é que a [ECU](/cars/ecu/ecu) sabe quando o nitroso está ativo e, portanto, pode mudar para um conjunto diferente de mapas de combustível/ignição. Kit seco (dry kit) + injetores de 450cc + [ECUNitrous Control](/cars/rom/ecu-nitrous-control) com [Dual Tables](/cars/rom/dual-tables) = kit húmido (wet kit) TOTALMENTE AFINADO!
