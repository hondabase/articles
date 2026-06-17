---
summary: 'Luz de Teste do Motor (Check Engine Light). Este indicador (geralmente no painel) acende-se para indicar que a ECU detetou alguma anomalia.'
applies_to:
  obd: [0, 1, 2]
  brand: Honda
complexity: intermediate
tags:
  - hardware
  - education
  - ecu
  - tuning
  - rom
  - sensors
  - reference
  - wiring
  - conversion
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: CEL
    url: /pgmfi/wiki/library/cel
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# CEL

### Check Engine Light

Este indicador (geralmente no painel de instrumentos) acende-se para indicar que a [ECU](/cars/ecu/ecu) detetou algum problema. A [ECU](/cars/ecu/ecu) costuma indicar um código de erro piscando a [CEL](/cars/wiring/cel) de uma determinada forma.

- Nos carros [OBD0](/cars/rom/obd0), existe um visor na própria [ECU](/cars/ecu/ecu) através do qual se pode ver um LED a piscar para leitura dos códigos.

- Nos carros [OBD1](/cars/wiring/obd1), existe uma ficha localizada sob o painel, junto ao espaço para os pés do passageiro, que deve ser ligada em curto-circuito (shunt). Isto fará com que a [CEL](/cars/wiring/cel) no painel pisque, indicando os códigos de erro registados.

- Nos carros [OBD2](/cars/wiring/obd2), existe uma ficha localizada sob o painel, junto ao espaço para os pés do passageiro, que deve ser ligada em curto-circuito (shunt). Isto fará com que a [CEL](/cars/wiring/cel) no painel pisque, indicando os códigos de erro registados. Também pode utilizar uma ferramenta de diagnóstico (scan tool) [OBD2](/cars/wiring/obd2), que se liga à ficha junto ao espaço para os pés do lado do condutor. É um conector cinzento que deverá ser facilmente identificável.

#### Luz de Motor Acesa Fixa (Solid CEL)

Se a [CEL](/cars/wiring/cel) ficar acesa de forma fixa e não piscar (após fazer o shunt no conector de diagnóstico em [OBD1](/cars/wiring/obd1)) e o carro funcionar mal, o problema poderá ser o seguinte:

- Uma [ECU](/cars/ecu/ecu) avariada (refere-se a qualquer outra falha de componente que não as listadas aqui)
- Soldaduras com mau contacto / soldaduras frias
- Erro de [Soma de Verificação (Checksum)](/cars/diagnostics/check-sum)
- Programa corrompido guardado na [ROM](/cars/rom/rom)
- Chip de [ROM](/cars/rom/rom) danificado
- Chip `74HC373` danificado

Consulte [Resolução de Problemas de CEL Fixa](/cars/diagnostics/troubleshooting-solid-cel)

#### Luz de Motor "Fantasma" (Phantom CEL)

Por vezes, pode surgir uma [CEL](/cars/wiring/cel) que desaparece assim que desliga o carro. Para verificar estes códigos, deve fazer o seguinte:

- NÃO desligue a ignição
- Faça o shunt no conector de diagnóstico como habitualmente

Agora, a [CEL](/cars/wiring/cel) irá apagar-se brevemente e depois começará a piscar os códigos normalmente. Consulte [Códigos de Erro Honda](/cars/diagnostics/diagnostic-trouble-codes)
