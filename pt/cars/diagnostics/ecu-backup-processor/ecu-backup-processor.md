---
summary: 'As ECUs da Honda são projetadas com muitos níveis de redundância. Existe um processador de Backup (rotulado como NEC BACK0004 na maioria das OBD0 e Oki 6534 na maioria das OBD1 (??)).'
applies_to:
  obd: [0, 1, 2]
  brand: Honda
complexity: beginner
tags:
  - ecu
  - reference
  - sensors
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: 'Processador de Backup da ECU'
    url: /pgmfi/wiki/library/ecu-backup-processor
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Processador de Backup da ECU

As [ECU](/cars/ecu/ecu)s da Honda são projetadas com muitos níveis de redundância. Existe um processador de Backup (rotulado como NEC BACK0004 na maioria das [OBD](/cars/wiring/obd)0 e Oki 6534 na maioria das [OBD](/cars/wiring/obd)1 (??)). O processador de backup é responsável pelo funcionamento do carro quando a [ECU](/cars/ecu/ecu) deteta uma falha grave, geralmente indicada por uma [CEL](/cars/wiring/cel) acesa de forma fixa. Não utiliza a gama completa de sensores que o carro possui, destinando-se apenas a permitir que o carro se mova minimamente pelos seus próprios meios em caso de falha "total" da lógica principal da [ECU](/cars/ecu/ecu).
