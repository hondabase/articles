---
summary: 'Respostas arquivadas para iniciantes sobre identificação, seleção e pesquisa de ECUs Honda.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - ecu
  - identification
  - reference
sources:
  - name: 'pgmfi.org wiki'
    title: 'Begginers FAQ'
    url: /pgmfi/wiki/library/begginers-faq
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# FAQ de ECU Honda para Iniciantes

Esta FAQ preserva as orientações introdutórias de identificação e compatibilidade de ECUs da wiki pgmfi. Os códigos de ECU Honda, tais como P28, PM6 e P72, identificam famílias de ECU, mas não confirmam, por si só, uma calibração ou aplicação completa.

## De que carro veio esta ECU?

A FAQ arquivada lista estas aplicações originais comuns. As aplicações podem variar consoante o mercado, ano, transmissão e calibração.

| Código de ECU | Aplicação listada na FAQ arquivada |
| :--- | :--- |
| PG6 | Integra 1988-1989 |
| PM5 | Civic/CRX DX 1988-1991 |
| PM6 | Civic/CRX SOHC Si 1988-1991 |
| PM7 | JDM DOHC ZC EF 1989-1991 |
| PM8 | CRX HF 1988-1991 |
| PR2 | ZC Europeu 1989-1991 |
| PR3 | JDM B16A EF8/EF9 1989-1991; `J00` ou `J51` também listados para 1992 |
| PW0 | JDM B16A EF8/EF9 e DA6 XSi 1989-1991 |
| PR4 | Integra LS/GS 1990-1991 |
| PS9 | Civic EX sedan automático 1988-1991 |
| P05 | Civic CX OBD1 1992-1995 |
| P06 | Civic DX OBD1 1992-1995 |
| P07 | Civic VX OBD1 1992-1995 |
| P08 | Civic JDM D15 OBD1 1992-1995 |
| P0A | Accord EX OBD1 1994-1995 |
| P13 | Prelude VTEC OBD1 1993-1995 |
| P14 | Prelude Si OBD1 1993-1995, não-VTEC |
| P27 | Civic JDM EG 1.6 SOHC OBD1 1992-1995 |
| P28 | Civic Si/EX OBD1 1992-1995 |
| P30 | Del Sol DOHC VTEC Si / EG SiR OBD1 1992-1995 |
| P54-G31 | Accord 1.8 LS 1997 |
| P61 | Integra GS-R OBD1 1992-1993 |
| P72 | Integra GS-R OBD1 1994-1995 e OBD2 1996-2000 |
| P73 | Integra Type R OBD2 1996-2000 |
| P74/P75 | Integra LS/GS OBD1 1992-1995 |
| P75 | Integra LS/GS OBD2 1996-2000 |
| P2N | Civic HX coupe OBD2 1996 e posterior |
| P2P | Civic EX coupe OBD2 1996 e posterior |
| P2E | Civic DX coupe OBD2 1996 e posterior |
| P2M | Civic SOHC VTEC da Nova Zelândia 1996 e posterior |
| P2T | Civic Si coupe 1999 e posterior; geração OBD incerta na fonte |
| P5P | Prelude Type S JDM OBD2 1997-2000 |
| PBA | Acura 1.6EL 1997 e posterior |
| PCT | JDM Integra/Civic Type R 1998 e posterior |
| PCX | S2000 1999 e posterior; geração OBD incerta na fonte |

Consulte a [Referência de Códigos de Definição de ECU Honda](/cars/ecu/ecu-definition-codes) mais ampla para obter informações adicionais sobre números de peça e mercados.

## Que ECU deve estar no meu carro?

A FAQ arquivada recomenda o uso de uma ECU que corresponda ao ano e tipo de motor. Os seus exemplos incluem uma PM6 para um D16A6, uma PR4 OBD0 para um B18 antigo, uma P72 ou P74 OBD1, e uma P73 ou P75 OBD2, conforme apropriado.

Considere estes apenas como exemplos gerais. A ECU correta também depende do mercado, da geração da cablagem, da transmissão, dos injetores, do distribuidor, dos sensores e do equipamento de emissões obrigatório. Leia a [Visão geral das gerações OBD](/cars/wiring/obd) antes de trocar de ECU entre gerações.

## Como identifico uma ECU?

Comece pela etiqueta na lateral da caixa da ECU. A FAQ arquivada descreve um código de família seguido de um sufixo, utilizando o padrão simplificado `LLN-LNN`, onde `L` é uma letra e `N` é um número.

Diz que os três primeiros caracteres identificam a família da ECU. Também descreve os sufixos de `A00` a `A49` como geralmente manuais e `A50` ou superior como geralmente automáticos.

> [!NOTE]
> Considere as faixas de sufixo apenas como uma pista da FAQ arquivada, não como uma regra universal. Verifique o número de peça completo e a configuração da placa.

## Onde posso encontrar o programa original?

A FAQ arquivada direciona os leitores para a lista de definições de ECU para obter os binários originais (stock). Consulte a [Referência de Códigos de Definição de ECU Honda](/cars/ecu/ecu-definition-codes).

## Posso correr código de outra ECU?

A FAQ arquivada remete esta questão para a pesquisa de compatibilidade de código de ECU. Não assuma que duas ECUs são compatíveis a nível de software apenas por partilharem conectores ou nomes de família semelhantes. Diferentes bases de código podem usar diferentes mapas de memória, drivers de hardware, lógica de sensores e atribuições de saídas.

Utilize uma ROM base comprovadamente compatível e verifique a família da ECU, revisão da placa, checksum, configuração dos injetores e saídas ativas antes de testar.

## Como posso contribuir sem escrever código?

A FAQ original encorajava os utilizadores não programadores a testar código, fotografar e identificar ECUs, ajudar outros utilizadores e escrever documentação. As contribuições úteis incluem:

- Fotografar placas de ECU e etiquetas das caixas
- Verificar a pinagem (pinouts) face aos manuais de serviço de fábrica
- Testar procedimentos em hardware claramente identificado
- Preservar informações de ROMs originais (stock) e checksums
- Escrever notas de instalação e de resolução de problemas (troubleshooting)

Registe o número exato da peça da ECU, revisão da placa, veículo, motor, transmissão e resultados com cada contribuição.
