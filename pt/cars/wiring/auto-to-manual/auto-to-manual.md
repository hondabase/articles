---
summary: 'A maioria das ECUs automáticas pode ser convertida para uma manual de 5 velocidades de forma bastante fácil. Fazer o caminho inverso envolve frequentemente adicionar mais componentes.'
applies_to:
  obd: [0, 1, 2]
  brand: Acura/Honda
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - wiring
  - conversion
  - diagnosticos
sources:
  - name: 'pgmfi.org wiki'
    title: 'Automático para Manual'
    url: /pgmfi/wiki/library/auto-to-manual
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Automático para Manual

A maioria das [ECUs](/cars/ecu/ecu) automáticas pode ser convertida para uma manual de 5 velocidades de forma bastante fácil. Fazer o caminho inverso envolve frequentemente adicionar mais componentes. Neste momento, parece que a conversão pode ser feita tanto por software COMO por hardware: a maioria das [ROMs](/cars/rom/rom) "mugen" desativa a verificação de hardware de transmissão automática, permitindo que uma [ECU](/cars/ecu/ecu) automática controle um motor manual de 5 velocidades sem gerar o código 19 (solenoide de lockup da transmissão automática). Também pode modificar o hardware para fazer com que uma [ECU](/cars/ecu/ecu) automática pense que é Manual. Isto é bastante específico para `cada` [ECU](/cars/ecu/ecu).

- [ECU OBD0 AUTOMÁTICO PARA MANUAL SEM REMOVER NENHUM HARDWARE](/cars/wiring/obd0ecuautotomanualwithoutremoveanyhardware) = Como utilizar uma ECU automática SEM a luz de Check Engine!
- [PS9 Automático para Manual](/cars/sensors/ps9-auto-manual) = Como transformar placas de circuito [OBD0](/cars/rom/obd0) PS9, PG7, PM7, PR5 ou similares numa [ECU](/cars/ecu/ecu) manual tipo PM6
- OBD0 PR4 Automático para Manual = Converter uma PR4 [OBD0](/cars/rom/obd0) automática para manual
- [PR3 Automático para Manual](/cars/ecu/pr3-auto-manual) = Converter uma PR3 automática para manual
- [OBD1 Civic Integra Automático para Manual](/cars/wiring/obd1-civic-integra-auto-manual) = Converter uma [ECU](/cars/ecu/ecu) de Civic e Integra automático de 92-95 de automático para manual
- [OBD1 P08 Automático para Manual](/cars/honda/civic/eg/sensors/obd1p08-auto-manual) = Converter uma [ECU](/cars/ecu/ecu) automática P08 ou P30 [JDM](/cars/sensors/jdm) (estilo mini) de automático para manual
- [OBD1 P13 Automático para Manual](/cars/wiring/obd1p13-auto-manual) = Converter uma [ECU](/cars/ecu/ecu) de Prelude H22A de 92-95 de automático para manual
- [OBD2 P5M Automático para Manual](/cars/wiring/obd2p5m-auto-manual) = Converter um PCM de Prelude H22A de 97-01 de automático para manual
