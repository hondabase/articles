---
summary: 'Notas de engenharia reversa sobre o barramento de memória da ECU OBD0, gamas de endereços de periféricos e lógica de seleção de chip (chip-select).'
tags: [ecu, hardware, memory, reverse-engineering, obd0]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD0 Inter Chip Communication'
    url: /pgmfi/wiki/library/obd0-inter-chip-communication
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Notas de comunicação inter-chip da OBD0

Estas notas de engenharia reversa arquivadas descrevem como um MCU OBD0 OKI M83C154 ou M80C154 parece comunicar com a RAM externa, o controlador de I/O, o ADC e, em algumas ECUs, uma EPROM.

> [!NOTE]
> Esta é uma investigação incompleta, e não um esquema confirmado. A fonte assinala várias gamas e ligações com pontos de interrogação e inclui descrições de pinos contraditórias. Essas incertezas são aqui preservadas.

## Dispositivos no barramento

A fonte identifica estes dispositivos como estando ligados ao MCU:

- NEC [uPD7004C ADC](/cars/sensors/upd7004c)
- SRAM externa 5128
- [Controlador de I/O OKI 6260A](/cars/ecu/oki6260a)
- EPROM 38256 de 32K em algumas ECUs

Refere que as instruções `MOVX A,@DPTR` e `MOVX @DPTR, A` acedem a dispositivos no barramento externo. Portas lógicas em algumas linhas de endereço parecem permitir que o MCU selecione dispositivos individuais, mas a lógica de descodificação ainda estava a ser investigada.

## Mapa de memória proposto

Todos os endereços abaixo estão em hexadecimal. Os limites das gamas são mantidos exatamente como foram propostos pela fonte.

| Início | Fim | Dispositivo | Nota de fiabilidade |
| --- | --- | --- | --- |
| `1000` | `1FFF` / `11FF` (?) | XRAM 5128 | Endereço final não resolvido |
| `2000` | `2FFF` / `3FFF` (?) | OKI 6260A | Endereço final não resolvido |
| `4000` | `4FFF` (?) | NEC uPD7004C | Endereço final não resolvido |
| `8XXX` | Não indicado | Não utilizado na ECU; reservado para RTP pela fonte | Proposta histórica |

## Valores de DPTR observados

A página arquivada lista estes como sendo todos os endereços que observou a ECU a carregar no DPTR:

```text
0110Bh 0001000100001011
0110Eh 0001000100001110
01120h 0001000100100000
0112Bh 0001000100101011
0112Eh 0001000100101110
01150h 0001000101010000
01151h 0001000101010001
01152h 0001000101010010
01154h 0001000101010100
01160h 0001000101100000
011F5h 0001000111110101
02000h 0010000000000000
02001h 0010000000000001
02002h 0010000000000010
02003h 0010000000000011
02004h 0010000000000100
02006h 0010000000000110
0200Ah 0010000000001010
0200Bh 0010000000001011
0200Eh 0010000000001110
0200Fh 0010000000001111
04000h 0100000000000000
04001h 0100000000000001
```

Estas observações levaram o autor a suspeitar que o próprio endereço controla qual chip de suporte é ativado.

## Traçados da lógica de descodificação registados

A fonte identifica o 74HC04 como um inversor sêxtuplo (hex inverter) e regista os seguintes traçados enquanto tentava compreender a seleção de chips:

```text
M5128 Pin 18 (CE) -> 74HC132 Pin 8 (Out 3Y)
74HC132 Pin 9 (In 3A) -> 80C154 Pin 25 (A8) -> 6260 Pin 11 (?)
74HC132 Pin 10 (In 3B) -> 74HC132 Pin 5 (In 2B) -> 74HC04 Pin 13 (in 6Y)
74HC04 Pin 12 (out 6Y) -> 80C154 Pin 9 (RST)
74HC132 Pin 11 (4 out) -> R143 -> 74HC132 Pin 1 (in 1A)
74HC132 Pin 6 (2 out) -> 74HC132 Pin 2 (in 1B)
74HC132 Pin 3 (1 out) -> 74HC132 Pin 12 (in 4A)
74HC132 Pin 13 (in 4B) -> IC13 Pin 5
74HC04 Pin 2 (out 1Y) -> 74HC132 Pin 4 (in 2A)
74HC04 Pin 3 (in 2A) -> 6260A Pin 24 (?)
74HC04 Pin 4 (out 2Y) -> R55 -> C55 -> 74HC04 Pin 6 (out 3Y) -> D7004C Pin 22 (?)
74HC04 Pin 8 (out 4Y) -> ADC board Pin 5
74HC04 Pin 10 (out 5Y) -> 83C154 Pin 14 (P3.4)
6260 Pin 20 -> ADC board Pin 3
6260 Pin 12 -> 80C154 Pin 30 (ALE)
6260 Pin 13 -> 80C154 Pin 16 (WR)
6260 Pin 14 -> D7004C Pin 19
```

A página também afirma que quando um bit alto do nibble alto é `0` para os endereços `2000h-4001h`, o Pino 22 do uPD7004C fica em nível lógico baixo (low), e vice-versa. Essa gama e descrição de bits não foram resolvidas.

Uma linha da fonte descreve o `74HC04 Pin 13` como sendo simultaneamente uma saída e uma entrada, fazendo um loop de retorno através do `74HC132 Pin 5`. Este pino foi omitido da lista de traçados acima por ser autocontraditório, e não por ter sido corrigido.

## Relacionado

- [NEC uPD7004C ADC](/cars/sensors/upd7004c)
- [Controlador de I/O OKI 6260A](/cars/ecu/oki6260a)
- [Localizações de RAM do OBD0 PM6/PM7](/cars/honda/civic/ef/tuning/obd0pm6pm7ram-locations)
