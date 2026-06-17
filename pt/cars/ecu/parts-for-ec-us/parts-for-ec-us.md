---
summary: 'Números de peças históricos de fornecedores para componentes utilizados na instalação de sockets, modificação ou reparação de ECUs Honda OBD0 e OBD1.'
applies_to:
  obd: [0, 1]
complexity: advanced
tags:
  - ecu
  - hardware
  - reference
sources:
  - name: 'pgmfi.org wiki'
    title: 'Parts For EC Us'
    url: /pgmfi/wiki/library/parts-for-ec-us
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Referência de fornecimento de componentes de ECU Honda

Esta é uma transcrição limpa dos números de componentes e fornecedores recolhidos pela comunidade pgmfi original para trabalhos em ECUs Honda OBD0 e OBD1. Os catálogos dos fornecedores mudam, por isso utilize estes números como referências de pesquisa e verifique o invólucro, valor, classificação de tensão, pinagem (pinout) e dimensões antes de encomendar.

> [!WARNING]
> Componentes com aspeto semelhante não são necessariamente intercambiáveis. Verifique a revisão da placa da ECU e a ficha técnica (datasheet) do componente de substituição antes de o soldar.

## Condensadores

| Valor | Descrição | Localizações na placa | Nota de origem | Número Digi-Key histórico |
| :--- | :--- | :--- | :--- | :--- |
| 22 pF | Condensador de disco cerâmico | C72, C74, C75, C89 | - | `1330PH-ND` |
| 0.1 uF | Condensador de disco cerâmico | C51, C52 | - | `399-2081-ND` |
| 1 uF, 35 V | Condensador eletrolítico | C60 | - | `478-1835-ND` |
| 4.7 uF | Condensador eletrolítico de tântalo | C94 | - | `399-1358-ND` |
| 0.004 uF | Condensador de montagem em superfície (SMD) | C49, C50 | ECUs JDM P30 e similares com montagem em superfície | `399-1230-1-ND` |
| 0.00001 uF | Condensador de montagem em superfície (SMD) | C91, C92 | ECUs JDM P30 e similares com montagem em superfície | `399-1192-1-ND` |

## Resistências

| Valor | Descrição | Localizações na placa | Número Digi-Key histórico |
| :--- | :--- | :--- | :--- |
| 1 kohm | Resistência de 1/4 W, 5% | R54 | `1.0KEBK-ND` |
| 1.2 kohm | Resistência de 1/4 W, 5% | R54 | `1.2KEBK-ND` |
| 220 ohm | Resistência de 1/4 W, 5% | R107 | `220EBK-ND` |
| 10 kohm | Resistência de 1/4 W, 5% | R142, R144, RM11 pinos 1-2 | `10KEBK-ND` |
| 15 kohm | Resistência de 1/4 W, 5% | R143 | `15KEBK-ND` |
| 820 ohm | Resistência de 1/4 W, 5% | R66, R67 | `820EBK-ND` |
| 51 kohm | Resistência de 1/4 W, 5% | RM11 pinos 2-3 | `51KEBK-ND` |
| 12 kohm | Resistência de 1/4 W, 5% | RM11 pinos 3-8 | `12KEBK-ND` |

## Memória, latches e sockets

| Componente | Descrição ou nota de origem | Número de fornecedor histórico |
| :--- | :--- | :--- |
| SST 27SF512 | ROM apagável para um ficheiro bin | Mouser `804-27SF5127CPG` |
| AT29C256 | ROM apagável; listada como obsoleta na fonte | Digi-Key `AT29C256-70PC-ND` |
| AT27C256R | EPROM; a fonte inclui a nota não explicada `15/12/10` | Digi-Key `AT27C256R-70PC-ND` |
| Socket DIP de 28 pinos | Socket de ROM | Digi-Key `ED3628-ND` |
| Socket ZIF de 28 pinos | Socket de ROM de força de inserção zero (ZIF) | Digi-Key `A347-ND` |
| 74HC373N | Latch de endereço DIP para placas USDM | Digi-Key `296-1591-5-ND` |
| Socket DIP de 20 pinos | Socket de estanho para latch DIP | Digi-Key `ED3120-ND` |
| 74HC373NS | Latch de endereço SOP para placas JDM de montagem em superfície | Digi-Key `296-8310-1-ND` |

## Transístores, díodo e conector

| Componente | Localizações na placa ou utilização | Referência cruzada da fonte | Número de fornecedor histórico |
| :--- | :--- | :--- | :--- |
| PNP A143 | `Q101` | A143 / NTE2362 | `2SB1030ARACT-ND` |
| NPN `C144` | `Q26`, `Q30` | `C144` / C2785 / NTE2361 | `2SD1423ARACT-ND` |
| 1N4001, díodo de 1 A | D11 | - | `1N4001DICT-ND` |
| Conector de travamento por fricção de 4 pinos e 0,1 polegadas | Datalogging OBD1 `CN2` | Fabricante `640456-4` | `A1922-ND` |
| Sensor MAP Motorola de 2,5 bar | Pressão de sobrealimentação (boost) aumentada | Nota do fabricante `737390003` | `MPX4250AP-ND` |

## Relacionado

- [Introdução ao chipping de ECU](/cars/rom/introduction-to-ecu-chipping)
- [Lista de cablagem para chipping de ECU OBD1](/cars/wiring/ecu-chipping-wirelist)
- [Lista de preços de fornecedores arquivada](prices.rtf)
