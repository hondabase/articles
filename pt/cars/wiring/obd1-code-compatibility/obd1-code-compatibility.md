---
summary: 'As ECUs de Civic e Integra OBD1 partilham uma plataforma de hardware comum. Isto significa que pode (com pequenas modificações) correr essencialmente qualquer código em qualquer ECU da família.'
tags: [ecu, reference, tuning, rom, sensors, wiring, conversion, diagnostics, obd1]
applies_to:
  brand: Acura/Honda
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Compatibilidade de Código OBD1'
    url: /pgmfi/wiki/library/obd1-code-compatibility
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Compatibilidade de Código OBD1

As [ECUs de Civic e Integra OBD1](/cars/sensors/obd1-civic-integra) são uma plataforma de hardware comum. Isto significa que pode (com pequenas modificações) correr essencialmente qualquer código em qualquer [ECU](/cars/ecu/ecu) desta família. No entanto, existem regras:

- Os programas [VTEC](/cars/sensors/vtec) ([P28](/cars/sensors/p28), [P30](/cars/sensors/p30), [P72](/cars/sensors/p72),...) requerem uma [ECU](/cars/ecu/ecu) [VTEC](/cars/sensors/vtec) ou uma conversão de [Não-VTEC para VTEC](/cars/wiring/non-vtec-to-vtec).
- Os programas Não-[VTEC](/cars/sensors/vtec) correm numa [ECU](/cars/ecu/ecu) [VTEC](/cars/sensors/vtec) sem quaisquer problemas.
- Os programas [VTEC](/cars/sensors/vtec) correm em [ECUs](/cars/ecu/ecu) não-VTEC com o VTEC desativado. (DB: podem até funcionar com o ponto de transição do VTEC acima do redline, embora eu ache que as verificações de sensores para VTP/VTS causem problemas.)
- As [ECUs](/cars/ecu/ecu) com sensor de oxigénio (O2) de 1 fio como a [P05](/cars/wiring/p05) ou [P08](/cars/wiring/p08) requerem ***ou*** a conversão de hardware de [Sensor de Oxigénio de 1 Fio para 4 Fios](/cars/honda/civic/eg/wiring/one-wire-to4-wire-o2-sensor) ***ou*** a desativação do [Circuito do Aquecedor de O2](/cars/wiring/o2-heater-circuit) na [ROM](/cars/rom/rom).
- Os programas [DOHC](/cars/sensors/dohc) [VTEC](/cars/sensors/vtec) ([P30](/cars/sensors/p30), [P72](/cars/sensors/p72),...) geralmente têm um [Sensor de Detonação (Knock Sensor)](/cars/ignition/knock-sensor) ativo. Para utilizar estes programas em [ECUs](/cars/ecu/ecu) que não possuem a [Placa de Detonação (Knock Board)](/cars/sensors/knock-board) ([P28](/cars/sensors/p28), [P08](/cars/wiring/p08), conversões,...), deve primeiro desativar o [Sensor de Detonação](/cars/ignition/knock-sensor).

Para obter informações sobre como desativar o [Sensor de Detonação](/cars/ignition/knock-sensor) ou o [Circuito do Aquecedor de O2](/cars/wiring/o2-heater-circuit) via software, consulte os [Mapas de ROM](/cars/wiring/rom-maps) para o código com o qual está a trabalhar. Além disso, diferentes mercados receberam diferentes funcionalidades nas suas [ECUs](/cars/ecu/ecu).

- As [ECUs](/cars/ecu/ecu) [USDM](/cars/sensors/usdm) são, de longe, as mais completas. Quase todo o código correrá numa [ECU](/cars/ecu/ecu) [USDM](/cars/sensors/usdm) se as regras acima forem seguidas.
- As [ECUs](/cars/ecu/ecu) [JDM](/cars/sensors/jdm) geralmente carecem de vários elementos que têm de ser fisicamente adicionados à [ECU](/cars/ecu/ecu) ou desativados na [ROM](/cars/rom/rom). O sensor de [Pressão Atmosférica](/cars/rom/pressure-atmosphere) (PA), o [Detetor de Carga Elétrica](/cars/sensors/electrical-load-detector) (ELD) e o [Circuito de Teste de Injetores](/cars/diagnostics/injector-test-circuit) são os mais notáveis aqui.
- As [ECUs](/cars/ecu/ecu) [EDM](/cars/wiring/edm) são geralmente as mais despidas. Normalmente não possuem PA, ELD, teste de injetores como as [ECUs](/cars/ecu/ecu) [JDM](/cars/sensors/jdm), e ocasionalmente também não têm o [Sensor de Detonação](/cars/ignition/knock-sensor) nem a respetiva placa de detonação que estão presentes nas [ECUs](/cars/ecu/ecu) [JDM](/cars/sensors/jdm).
