---
summary: 'Métodos arquivados de instalação de suporte (socketing) e modificação (chipping) para as primeiras ECUs OBD0 da Honda e Acura de 1988-1989.'
applies_to:
  obd: [0]
complexity: advanced
tags:
  - ecu
  - chipping
  - hardware
sources:
  - name: 'pgmfi.org wiki'
    title: 'Chipping An88-89ECU'
    url: /pgmfi/wiki/library/chipping-an88-89ecu
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Modificação (Chipping) de ECUs OBD0 de 1988-1989

A maioria das ECUs MPFI OBD0 de 1990-1991 usa uma ROM externa compatível com 38256 que pode ser removida e substituída. Em vez disso, muitas ECUs de 1988-1989 usam um processador OKI M83C154 com ROM interna. O guia arquivado também indica que todas as ECUs USDM PM8 HF de 1988-1991 usam este design de ROM interna.

Este artigo preserva as três abordagens de modificação e as duas tabelas de ligações descritas pela comunidade original pgmfi.

> [!WARNING]
> Desliga a ECU do veículo antes de soldar. Verifica cada ligação com um teste de continuidade e verifica se existem curto-circuitos antes de ligar a alimentação.

## Ativar o acesso à ROM externa

O guia indica para ligar o Pin 31, o pin de acesso externo (`_EA`) do M83C154, ao Pin 20 (massa/terra) para que o MCU execute o código a partir de uma ROM externa.

> [!WARNING]
> Nas placas PM7-B020, a fonte indica que o Pin 31 do MCU deve ser desligado da PCB antes de ser ligado à massa. É reportada uma luz de aviso de motor (CEL) acesa fixa e um funcionamento intermitente se esse pin continuar ligado. A fonte sugere considerar isto noutras placas apenas quando a colocação normal de jumpers falhar e as ligações do suporte não tiverem falhas.

## Três abordagens documentadas

### 1. Substituir o MCU

Substituir o MCU OKI de 40 pins por um MCU compatível com Intel 8051 que contenha ROM interna. O guia arquivado refere que isto requer a modificação do programa para remover a utilização da instrução `A5` e a realização de outras alterações para compatibilidade com o Intel 8051. Também requer um programador para o MCU de substituição.

A fonte observou em janeiro de 2004 que esta abordagem não estava concluída.

### 2. Instalar uma placa filha (daughterboard) para o MCU

Substituir o MCU de 40 pins por uma placa filha contendo:

- Um suporte para o MCU OKI original
- Um trinco de endereço (address latch) `74HC373`
- Um suporte EPROM externo
- Hardware que configura o `_EA` para ROM externa

Esta abordagem mantém o MCU OKI original e, portanto, não requer as mesmas alterações no programa, mas exige uma placa de circuito impresso, componentes adicionais e mais soldadura.

### 3. Ligar uma EPROM externa (Flywire)

Instalar um suporte EPROM de 28 pins e ligá-lo ao MCU e ao trinco de endereço. A fonte descreve um método de ligação direta por fios (flywire) e um método de sobreposição XRAM (XRAM piggyback).

## Mapeamento de ligações diretas (Flywire)

Esta tabela é um mapeamento direto de pins da página arquivada.

| Pin da EPROM | Pin do MCU M83C154 | Pin do `74HC373` |
| :---: | :---: | :---: |
| 1 | 40 | - |
| 2 | 25 | - |
| 3 | - | 19 |
| 4 | - | 2 |
| 5 | - | 16 |
| 6 | - | 5 |
| 7 | - | 15 |
| 8 | - | 6 |
| 9 | - | 12 |
| 10 | - | 9 |
| 11 | 39 | - |
| 12 | 38 | - |
| 13 | 37 | - |
| 14 | 20 | - |
| 15 | 36 | - |
| 16 | 35 | - |
| 17 | 34 | - |
| 18 | 33 | - |
| 19 | 32 | - |
| 20 | - | 10 |
| 21 | 23 | - |
| 22 | 29 | - |
| 23 | 24 | - |
| 24 | 22 | - |
| 25 | 21 | - |
| 26 | 26 | - |
| 27 | 27 | - |
| 28 | 20 na tabela da fonte; ver nota | - |

> [!NOTE]
> A tabela de flywire arquivada lista o Pin 20 do MCU para o Pin 28 da EPROM, mas um esclarecimento posterior na mesma página diz que os Pins 28 e 1 da EPROM ligam ambos ao Pin 40 do MCU (+5 V). O Pin 20 é identificado como massa noutro local da página. Verifica o circuito antes de efetuar as ligações.

## Mapeamento de sobreposição XRAM (piggyback)

O método alternativo monta o suporte EPROM numa pequena placa de prototipagem por cima da RAM externa. A fonte avisa que a montagem empilhada pode causar problemas de espaço e não recomenda este método para quem se está a iniciar na soldadura.

| Pin da EPROM | Pin do MCU M83C154 | Pin da RAM externa |
| :---: | :---: | :---: |
| 1 | 40 | - |
| 2 | 25 | - |
| 3 | - | 1 |
| 4 | - | 2 |
| 5 | - | 3 |
| 6 | - | 4 |
| 7 | - | 5 |
| 8 | - | 6 |
| 9 | - | 7 |
| 10 | - | 8 |
| 11 | - | 9 |
| 12 | - | 10 |
| 13 | - | 11 |
| 14 | - | 12 |
| 15 | - | 13 |
| 16 | - | 14 |
| 17 | - | 15 |
| 18 | - | 16 |
| 19 | - | 17 |
| 20 | Ligar ao Pin 14 da EPROM | - |
| 21 | 23 | - |
| 22 | 29 | - |
| 23 | 24 | - |
| 24 | 22 | - |
| 25 | - | 23 |
| 26 | 26 | - |
| 27 | 27 | - |
| 28 | Ligar ao Pin 1 da EPROM | - |

A fonte clarifica que o Pin 20 da EPROM liga ao Pin 14 da EPROM e ao Pin 12 da RAM para a massa, enquanto os Pins 28 e 1 da EPROM ligam ao Pin 40 do MCU para +5 V. Refere novamente para ligar o Pin 31 do MCU ao Pin 20 do MCU para selecionar a ROM externa.

## Fotos da instalação da sobreposição (piggyback)

![EPROM socket daughterboard top](DSC00663.jpg)
*Vista superior do suporte da placa filha.*

![EPROM socket daughterboard bottom](DSC00662.jpg)
*Vista inferior do suporte da placa filha.*

![Header pins soldered to external RAM](DSC00667.jpg)
*Pins de cabeçalho (header pins) soldados na RAM externa.*

![Completed external RAM connections](DSC01263_small.jpg)
*Ligações da XRAM concluídas.*

![Completed piggyback installation](DSC00672.JPG)
*Instalação concluída da sobreposição empilhada na placa da ECU.*
