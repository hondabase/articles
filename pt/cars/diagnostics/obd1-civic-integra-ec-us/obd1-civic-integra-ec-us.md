---
summary: 'Quase todas as ECUs OBD1 utilizadas nos Civics e Integras de 92-95 (mas NÃO nos Preludes, Accords, Legends, etc.) são mais ou menos compatíveis eletricamente.'
applies_to:
  obd: [1]
  brand: Acura/Honda
complexity: advanced
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD1 Civic Integra EC Us'
    url: /pgmfi/wiki/library/obd1-civic-integra-ec-us
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1 Civic Integra EC Us

Quase todas as [ECU](/cars/ecu/ecu)s [OBD1](/cars/wiring/obd1) utilizadas nos Civics e Integras de 92-95 (mas NÃO nos Preludes, Accords, Legends, etc.) são mais ou menos compatíveis eletricamente. Com pequenos ajustes, todo o tipo de modificações de hardware de ECU ([ECUHardware Mods](/cars/rom/ecu-hardware-mods)) são possíveis. O artigo [OBD1 Code Compatibility](/cars/wiring/obd1-code-compatibility) descreve como combinar código e [ECU](/cars/ecu/ecu)s. Esta geração de [ECU](/cars/ecu/ecu) utiliza um [MCU](/cars/rom/mcu) [66207](/cars/sensors/66207). A maioria das [ECU](/cars/ecu/ecu)s é fornecida com o programa para as correr numa [ROM](/cars/rom/rom) interna. A predisposição para uma [ROM](/cars/rom/rom) externa foi contemplada no design da placa, e pode ser ativada adicionando um chip [74 HC373](/cars/rom/74hc373), uma resistência, dois condensadores, o ligador [J1](/cars/rom/obd1j1) e um suporte para a própria [ROM](/cars/rom/rom). <- Isto refere-se principalmente às [ECU](/cars/ecu/ecu)s [USDM](/cars/sensors/usdm). Não vi provas em contrário para as [JDM](/cars/sensors/jdm), visto que a maioria já possui [ROM](/cars/rom/rom)s externas presentes. Não tenho a certeza quanto às [EDM](/cars/wiring/edm). O chip [82 C55](/cars/ecu/82c55) presente na placa da [ECU](/cars/ecu/ecu) é um controlador de [IO](/cars/sensors/io) que é utilizado para controlar a maioria das saídas. O [J12 ](/cars/wiring/obd1j12) controla o funcionamento da interface série da [ECU](/cars/ecu/ecu). Importante para gravação de dados ([Data Logging](/cars/diagnostics/data-logging)). dj_spark - 21 Fev 2006 : As [ECU](/cars/ecu/ecu)s P28/P30 [EDM](/cars/wiring/edm) são modificadas da mesma forma, adicionando os mesmos componentes que a versão [USDM](/cars/sensors/usdm).
