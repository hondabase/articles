---
summary: 'Referência técnica de componentes eletrônicos e números de peças históricos para manutenção, reparo e modificação de ECUs Honda OBD0 e OBD1.'
tags: [ecu, hardware, reparo, componentes, eletrônica]
applies_to:
  obd: [0, 1]
complexity: advanced
---

# Referência de componentes para ECUs Honda

Esta documentação fornece uma lista de componentes eletrônicos utilizados em ECUs Honda OBD0 e OBD1. Os números de peças listados são referências históricas de fornecedores; verifique sempre as especificações técnicas (invólucro, valor, classificação de tensão, pinagem e dimensões) antes de realizar a aquisição ou instalação.

> [!WARNING]
> Componentes com aparência semelhante não são necessariamente intercambiáveis. Sempre verifique a revisão da placa da ECU e a folha de dados (datasheet) do componente de substituição antes da soldagem.

## Condensadores

| Valor | Descrição | Localizações na placa | Número Digi-Key histórico |
| :--- | :--- | :--- | :--- |
| 22 pF | Condensador de disco cerâmico | C72, C74, C75, C89 | `1330PH-ND` |
| 0.1 uF | Condensador de disco cerâmico | C51, C52 | `399-2081-ND` |
| 1 uF, 35 V | Condensador eletrolítico | C60 | `478-1835-ND` |
| 4.7 uF | Condensador eletrolítico de tântalo | C94 | `399-1358-ND` |
| 0.004 uF | Condensador SMD | C49, C50 | `399-1230-1-ND` |
| 0.00001 uF | Condensador SMD | C91, C92 | `399-1192-1-ND` |

## Resistências

| Valor | Descrição | Localizações na placa | Número Digi-Key histórico |
| :--- | :--- | :--- | :--- |
| 1 kohm | Resistência 1/4 W, 5% | R54 | `1.0KEBK-ND` |
| 1.2 kohm | Resistência 1/4 W, 5% | R54 | `1.2KEBK-ND` |
| 220 ohm | Resistência 1/4 W, 5% | R107 | `220EBK-ND` |
| 10 kohm | Resistência 1/4 W, 5% | R142, R144, RM11 (1-2) | `10KEBK-ND` |
| 15 kohm | Resistência 1/4 W, 5% | R143 | `15KEBK-ND` |
| 820 ohm | Resistência 1/4 W, 5% | R66, R67 | `820EBK-ND` |
| 51 kohm | Resistência 1/4 W, 5% | RM11 (2-3) | `51KEBK-ND` |
| 12 kohm | Resistência 1/4 W, 5% | RM11 (3-8) | `12KEBK-ND` |

## Memória, Latches e Sockets

| Componente | Descrição | Número de fornecedor histórico |
| :--- | :--- | :--- |
| SST 27SF512 | ROM apagável | Mouser `804-27SF5127CPG` |
| AT29C256 | ROM apagável | Digi-Key `AT29C256-70PC-ND` |
| AT27C256R | EPROM | Digi-Key `AT27C256R-70PC-ND` |
| Socket DIP 28 pinos | Socket de ROM | Digi-Key `ED3628-ND` |
| Socket ZIF 28 pinos | Socket de ROM (ZIF) | Digi-Key `A347-ND` |
| 74HC373N | Latch de endereço DIP | Digi-Key `296-1591-5-ND` |
| Socket DIP 20 pinos | Socket para latch DIP | Digi-Key `ED3120-ND` |
| 74HC373NS | Latch de endereço SOP | Digi-Key `296-8310-1-ND` |

## Transístores, Díodos e Conectores

| Componente | Localização | Referência Cruzada | Número de fornecedor histórico |
| :--- | :--- | :--- | :--- |
| PNP A143 | Q101 | A143 / NTE2362 | `2SB1030ARACT-ND` |
| NPN C144 | Q26, Q30 | C144 / C2785 / NTE2361 | `2SD1423ARACT-ND` |
| 1N4001 | D11 | - | `1N4001DICT-ND` |
| Conector 4 pinos | Datalogging (CN2) | Fabricante `640456-4` | `A1922-ND` |
| Sensor MAP | Boost (2.5 bar) | Motorola `737390003` | `MPX4250AP-ND` |

## Relacionado
- [Introdução ao chipping de ECU](/cars/rom/introduction-to-ecu-chipping)
- [Lista de cablagem para chipping de ECU OBD1](/cars/wiring/ecu-chipping-wirelist)