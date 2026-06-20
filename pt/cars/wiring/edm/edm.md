---
summary: 'Referência para as ECUs Honda EDM (Mercado Doméstico Europeu), detalhando as diferenças comuns de hardware, como a falta de um circuito de teste de injetores.'
tags: [ecu, reference, sensors, wiring, conversion, diagnostics]
applies_to:
  brand: Acura/Honda
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: EDM
    url: /pgmfi/wiki/library/edm
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# EDM

Mercado Doméstico Europeu (European Domestic Market) — carros produzidos para a Europa.

**Comparar com:** [JDM](/cars/sensors/jdm), [USDM](/cars/sensors/usdm).

**Nota:** As [ECU](/cars/ecu/ecu)s [EDM](/cars/wiring/edm) [OBD1 Civic Integra](/cars/sensors/obd1-civic-integra) geralmente não possuem os sensores do [Injector Test Circuit](/cars/diagnostics/injector-test-circuit) (Circuito de Teste de Injetores), [Knock Sensor](/cars/ignition/knock-sensor) (Sensor de Detonação), [Electrical Load Detector](/cars/sensors/electrical-load-detector) e [Pressure Atmosphere](/cars/tuning/pressure-atmosphere) (Pressão Atmosférica) (em comparação com as [ECU](/cars/ecu/ecu)s [USDM](/cars/sensors/usdm)). Geralmente são muito parecidas com as [ECU](/cars/ecu/ecu)s [USDM](/cars/sensors/usdm), mas com menos componentes povoados na placa. 

Nota sobre [OBD](/cars/wiring/obd)2: Após 1996, os Hondas [EDM](/cars/wiring/edm) possuem [ECU](/cars/ecu/ecu)s da família [OBD](/cars/wiring/obd)2, mas não são compatíveis com o padrão de diagnóstico OBDII. Possuem apenas um [DLC](/cars/wiring/dlc) de 3 fios e comunicam apenas com testadores PGM.

###

### EOBD é a próxima geração de diagnósticos de sistemas de controlo a bordo utilizados em aplicações automóveis; todos os carros de estrada e camiões ligeiros a gasolina fabricados após o ano de modelo 2000 devem cumprir esta nova norma.
