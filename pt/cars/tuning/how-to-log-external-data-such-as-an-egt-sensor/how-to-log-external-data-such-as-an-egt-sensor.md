---
summary: Método arquivado de entrada analógica USDM P30 D12 para registo de dados (datalogging) de um sensor externo de 0-5 V.
applies_to:
  ecus: [P30]
  obd: [1]
complexity: advanced
tags: [datalogging, sensor, adc, ecu]
sources:
  - name: 'pgmfi.org wiki'
    title: 'How To Log External Data Such As An Egt Sensor'
    url: /pgmfi/wiki/library/how-to-log-external-data-such-as-an-egt-sensor
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Registar um sensor externo de 0-5 V através de P30 D12

Este método arquivado utiliza a entrada analógica D12 não documentada numa ECU USDM OBD1 P30 para registar um sinal externo de 0-5 V, como a saída de um amplificador EGT ou controlador de O2 de banda larga (wideband).

> [!WARNING]
> A fonte apenas documenta testes diretos numa P30 USDM. Sugere que outras ECUs USDM OBD1 devem partilhar o circuito e refere que uma P28 USDM parece semelhante, mas deixa essa compatibilidade por confirmar. As ECUs JDM P30 utilizam um circuito D12 diferente e incompleto.

## Entrada analógica D12

Na P30 USDM documentada, D12 liga à entrada AI3 do `66207` no Pino 57. O esquema arquivado identifica o circuito de entrada analógica em redor dessa ligação.

![Esquema do ADC D12 da P30 USDM](USDMD12adc.jpg)
*Esquema arquivado da secção de entrada analógica da P30 USDM.*

A fonte descreve os dados registados da seguinte forma:

| Item | Descrição arquivada |
| --- | --- |
| Intervalo de entrada | 0-5 V aplicados em D12 |
| Byte principal registado | RAM `0067h` |
| Escala do byte principal | Aproximadamente 0,02 V por contagem, de `00h` a 0 V até `0FFh` a 5 V |
| Bits adicionais do ADC | RAM `0066h` contém os dois bits menos significativos do resultado de 10 bits do ADC |
| Perda de sinal reportada | Cerca de 1% de D12 para AI3 no Pino 57 do `66207` |

O autor considerou os dois bits adicionais do ADC desnecessários para o registo de EGT. A página reporta a perda de tensão, mas não documenta como foi medida nem fornece dados de calibração.

## Filtro `C42` opcional da fonte

A ECU USDM original documentada pela fonte não tinha qualquer componente instalado em `C42`. A recomendação arquivada era instalar ali um condensador de tântalo de `1 uF`, `35 V` para suavizar a entrada do ADC, com o seu polo positivo virado para o lado oposto ao `66207` e coincidindo com a orientação dos outros condensadores nessa fila.

![Placa P30 USDM com C42 instalado](USDMc42.JPG)
*Foto arquivada mostrando o condensador `C42` adicionado.*

> [!WARNING]
> A polaridade do condensador e o esquema da placa devem ser verificados na ECU real. A recomendação arquivada não foi documentada para todas as revisões da placa P30 ou outros tipos de ECU.

## Diferença na P30 JDM

A fonte refere que a P30 USDM liga o AI5 à massa (terra), enquanto a P30 JDM liga o AI3 à massa e encaminha o D12 para o AI5 no Pino 63 do `66207`. O caminho D12 da JDM também tem componentes não instalados e deve ser modificado antes de poder ser utilizado como descrito.

Ver a [modificação arquivada D12 da P30 JDM](/cars/tuning/japanese-domestic-market-p30d12-modification) para as alterações no circuito e o seu aviso de software AI5 não resolvido.

## Utilizações descritas pela fonte

A página arquivada discute estas possíveis utilizações para o D12:

- Registo de EGT a partir de um amplificador de termopar com saída de 0-5 V.
- Registo de O2 de banda larga (wideband) mantendo a entrada de O2 de banda estreita (narrowband) original inalterada.
- Uma entrada de interruptor interpretada por software com um resistor pull-up.

A ideia do interruptor era apenas um conceito de programação na fonte. Também consumiria o D12, impedindo o registo simultâneo de EGT ou de outro sensor externo.

## Relacionado

- [Visão geral do registo de dados (datalogging) da ECU Honda](/cars/diagnostics/data-logging)
- [Modificação da entrada analógica D12 da P30 JDM](/cars/tuning/japanese-domestic-market-p30d12-modification)
- [Visão geral do O2 de banda larga (Wideband)](/cars/fueling/wide-band-o2)
- [Sensor de temperatura dos gases de escape (EGT)](/cars/tuning/exhaust-gas-temp-sensor)
