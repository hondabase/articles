---
summary: Modificação arquivada do circuito D12 do P30 JDM para registar uma entrada analógica de 0-5 V através da ECU.
applies_to:
  ecus: [P30]
  obd: [1]
complexity: advanced
tags: [ecu, datalogging, hardware, adc]
sources:
  - name: 'pgmfi.org wiki'
    title: 'Japanese Domestic Market P30D12 Modification'
    url: /pgmfi/wiki/library/japanese-domestic-market-p30d12-modification
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Modificação da entrada analógica D12 do P30 JDM

Esta modificação arquivada utiliza a entrada D12, de outra forma não utilizada, numa ECU P30 OBD1 JDM para registar um sinal analógico de 0-5 V, como a saída de um amplificador de termopar EGT.

> [!WARNING]
> Este procedimento corta ou altera circuitos da placa da ECU. A fonte relata testes bem-sucedidos em ECUs P30 USDM e JDM, mas não estabelece compatibilidade com outras ECUs OBD1. Verifique o circuito e o comportamento do software antes de modificar uma ECU.

## Diferenças entre o P30 USDM e o JDM

A investigação original utilizou um P30 USDM para os testes iniciais e um P30 JDM para a modificação e respetivos testes. Previa-se que outras ECUs OBD1 da Honda fossem semelhantes, mas isso não foi confirmado.

| Detalhe | USDM P30 | JDM P30 |
| --- | --- | --- |
| Componentes de D12 | Todos instalados | Alguns componentes em falta |
| Circuito D12 | Descrito como mais simples | Descrito como mais complexo |
| Entrada analógica D12 | AI3, pino 57 do `66207` no encapsulamento DIP de 64 pinos | AI5, pino 63 do `66207` no encapsulamento PLCC de 68 pinos |
| Entrada analógica ligada à massa | AI5, pino 59 do `66207` | AI3, descrito como pino 61 do `66207` |
| Oito bits superiores do ADC | RAM `067h` | RAM `06Bh` |
| Dois bits restantes do ADC | A fonte descreve os dois bits mais significativos da RAM `066h` como os dois bits menos significativos do valor do ADC | A fonte descreve os dois bits mais significativos da RAM `06Ah` como os dois bits menos significativos do valor do ADC |

> [!NOTE]
> A secção JDM arquivada utiliza duas vezes "USDM" ao descrever o circuito JDM: designa a entrada AI3 ligada à massa como parte de um P30 USDM e designa o caminho D12 para AI5 como "cablagem D12 USDM". A tabela acima segue o contexto JDM envolvente, mas essas designações não foram corrigidas ou verificadas de forma independente.

![USDM P30 D12 input schematic](USDMP30D12Schematics.jpg)
*Esquema arquivado do circuito D12 do P30 USDM.*

## Modificação JDM arquivada

A fonte indica que todas estas alterações são feitas na parte de trás da placa da ECU:

1. Substitua `R15` por um díodo.
2. Instale outro díodo em `R14`. A fonte utilizou díodos `1N-4148` de montagem em superfície (SMD) e descreveu-os como proteção para a entrada analógica `66207`.
3. Adicione uma ponte (jumper) em `R13`.
4. Adicione uma ponte (jumper) entre as ligações não ligadas à massa de `Q3` para levar D12 ao circuito modificado.
5. Deixe a resistência `R16` de `33 kohm` e o condensador `C17` inalterados. A fonte não identificou o valor de `C17` e referiu que parecia ser um condensador de tântalo.

![JDM P30 D12 circuit before and after modification](JDMP30D12CircuitEGTModR1.jpg)
*Esquema arquivado de antes e depois para a modificação do D12 do P30 JDM.*

![Modified JDM P30 board at the D12 and AI5 circuit](JDMp30D12ModPin63.JPG)
*Foto arquivada em alta resolução da placa modificada do P30 JDM.*

O autor testou ambas as variantes do P30 com um potenciómetro de `10 kohm` utilizado como divisor de tensão variável numa fonte de alimentação de 5 V, e com um sensor EGT EGADS. Esses testes não confirmam o funcionamento com outros sensores ou variantes de ECU.

## Aviso de software para o AI5

A página arquivada avisa que o código OBD1 parece ler o AI5 e executar uma função não identificada. Até que esse código fosse compreendido, propôs-se uma disposição diferente e mais invasiva:

1. Corte as pistas para AI3 e AI5 no `66207`.
2. Ligue AI5 à massa.
3. Encaminhe o circuito D12 para AI3.

A fonte esperava que essa troca de pinos fizesse com que uma ECU JDM registasse o D12 como uma ECU USDM. Não documentou a função desconhecida do AI5 nem forneceu uma validação mais ampla, pelo que deve tratar isto como uma proposta histórica não verificada e não como uma recomendação atual.

## Relacionado

- [Registar um sensor externo de 0-5 V através de D12](/cars/tuning/how-to-log-external-data-such-as-an-egt-sensor)
- [Visão geral do datalogging de ECUs Honda](/cars/diagnostics/data-logging)
- [Referência da ECU P30](/cars/sensors/p30)
