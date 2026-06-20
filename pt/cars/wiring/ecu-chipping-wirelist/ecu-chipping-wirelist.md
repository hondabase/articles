---
summary: 'Ligações de pinos e pistas entre o MCU, latch e o suporte de EPROM externa em ECUs Honda OBD1.'
tags: [ECU, chipping, hardware, wiring]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Ecu Chipping Wirelist'
    url: /pgmfi/wiki/library/ecu-chipping-wirelist
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Lista de Ligações para Modificação de ECU OBD1 (Chipping)

Utilize esta lista arquivada de ligações de ECUs Honda OBD1 para diagnosticar problemas de continuidade após instalar um suporte de ROM externo e um latch `74HC373`. Regista as ligações conhecidas entre o latch, o suporte de ROM, o MCU 66K, o `IC9`, o conjunto de resistências (resistor pack) `RM3` e os componentes próximos na placa.

> [!CAUTION]
> Desligue a ECU do veículo antes de testar a continuidade. Estes mapeamentos são observações da comunidade arquivadas, não um substituto para um esquema verificado da sua placa exata.

## Procedimento de teste de continuidade

1. Inspecione o latch `74HC373` e o suporte de ROM à procura de pontes de solda.
2. Com um aparelho de teste de continuidade, verifique cada par de pinos adjacentes em ambos os componentes. Os pinos adjacentes não devem ter continuidade.
3. Coloque uma ponta de prova onde cada pino do componente entra na placa.
4. Verifique esse pino em relação a pelo menos uma ligação esperada na lista de ligações pesquisável abaixo.
5. Utilize as vias de passagem (`FT`) listadas para testar a continuidade entre um pino de CI e a placa, quando disponíveis.

## Notas sobre a numeração dos pinos

- Os pinos DIP começam no pino 1 ao lado do entalhe ou ponto, descem pelo lado esquerdo e continuam subindo pelo lado direito.
- O `RM3` é um conjunto de resistências do tipo SIP (single-inline-package); o seu pino 1 está marcado na serigrafia.
- Na placa P30 JDM, o pino 1 do MCU 66K fica no meio de um dos lados do encapsulamento quadrado de montagem em superfície (SMD). Vários números de pinos do MCU estão marcados na placa.
- Os nomes de sinais que começam com `/` são ativos em nível lógico baixo (active low).

## Lista de ligações pesquisável

Utilize os filtros de família de ECU e componentes, ou pesquise por um pino, sinal ou componente ligado.

```wirelist
{
 "title": "Ligações de chipping da ECU OBD1",
 "variants": [
 {
 "id": "jdm-p30-901",
 "label": "JDM P30-901",
 "groups": [
 {
 "label": "Latch 373",
 "rows": [
 {
 "pin": "Pino 1",
 "signal": "/OE",
 "path": "373 Pino 10 -> FT -> ROM Pino 14 (GND) -> ROM Pino 20 (/CE)",
 "note": ""
 },
 {
 "pin": "Pino 2",
 "signal": "1Q",
 "path": "RM3 Pino 5 -> ROM Pino 10 (A0)",
 "note": ""
 },
 {
 "pin": "Pino 3",
 "signal": "1D",
 "path": "RM3 Pino 9 -> ROM Pino 11 (I/O0) -> 66K Pino 2 (AD0) -> IC9 Pino 11",
 "note": ""
 },
 {
 "pin": "Pino 4",
 "signal": "2D",
 "path": "RM3 Pino 8 -> ROM Pino 12 (I/O1) -> 66K Pino 3 (AD1) -> IC9 Pino 12",
 "note": ""
 },
 {
 "pin": "Pino 5",
 "signal": "2Q",
 "path": "ROM Pino 9 (A1)",
 "note": ""
 },
 {
 "pin": "Pino 6",
 "signal": "3Q",
 "path": "ROM Pino 8 (A2)",
 "note": ""
 },
 {
 "pin": "Pino 7",
 "signal": "2D",
 "path": "RM3 Pino 7 -> ROM Pino 13 (I/O2) -> 66K Pino 4 (AD2) -> IC9 Pino 13",
 "note": "A lista de latches arquivada identifica este sinal como 2D; a lista de ROM correspondente identifica-o de forma diferente."
 },
 {
 "pin": "Pino 8",
 "signal": "2D",
 "path": "RM3 Pino 6 -> ROM Pino 15 (I/O3) -> 66K Pino 5 (AD3) -> IC9 Pino 14",
 "note": "A lista de latches arquivada identifica este sinal como 2D; a lista de ROM correspondente identifica-o de forma diferente."
 },
 {
 "pin": "Pino 9",
 "signal": "4Q",
 "path": "ROM Pino 7",
 "note": ""
 },
 {
 "pin": "Pino 10",
 "signal": "GND",
 "path": "373 Pino 1 -> FT -> ROM Pino 14 (GND) -> ROM Pino 20 (/CE)",
 "note": ""
 },
 {
 "pin": "Pino 11",
 "signal": "LE",
 "path": "C91 -> 66K Pino 24 (ALE)",
 "note": ""
 },
 {
 "pin": "Pino 12",
 "signal": "5Q",
 "path": "ROM Pino 4 (A6)",
 "note": ""
 },
 {
 "pin": "Pino 13",
 "signal": "5D",
 "path": "ROM Pino 18 (I/O6) -> 66K Pino 8 (AD6) -> IC9 Pino 17",
 "note": ""
 },
 {
 "pin": "Pino 14",
 "signal": "6D",
 "path": "ROM Pino 19 (I/O7) -> 66K Pino 9 (AD7) -> IC9 Pino 18",
 "note": ""
 },
 {
 "pin": "Pino 15",
 "signal": "6Q",
 "path": "FT -> ROM Pino 3 (A7)",
 "note": ""
 },
 {
 "pin": "Pino 16",
 "signal": "7Q",
 "path": "FT -> ROM Pino 5 (A5)",
 "note": ""
 },
 {
 "pin": "Pino 17",
 "signal": "7D",
 "path": "ROM Pino 17 (I/O5) -> 66K Pino 7 (AD5) -> IC9 Pino 16",
 "note": ""
 },
 {
 "pin": "Pino 18",
 "signal": "8D",
 "path": "ROM Pino 16 (I/O4) -> 66K Pino 6 (AD4) -> IC9 Pino 15",
 "note": ""
 },
 {
 "pin": "Pino 19",
 "signal": "8Q",
 "path": "ROM Pino 6 (A4)",
 "note": ""
 },
 {
 "pin": "Pino 20",
 "signal": "VCC",
 "path": "C49 -> ROM Pino 28 (VCC) -> ROM Pino 1 (/WE)",
 "note": ""
 }
 ]
 },
 {
 "label": "Suporte de ROM",
 "rows": [
 {
 "pin": "Pino 1",
 "signal": "VCC",
 "path": "ROM Pino 28 (VCC) -> C49 -> 373 Pino 20 (VCC)",
 "note": ""
 },
 {
 "pin": "Pino 2",
 "signal": "A12",
 "path": "66K Pino 14 (A12)",
 "note": ""
 },
 {
 "pin": "Pino 3",
 "signal": "A7",
 "path": "FT -> 373 Pino 15 (6Q)",
 "note": ""
 },
 {
 "pin": "Pino 4",
 "signal": "A6",
 "path": "FT -> 373 Pino 12 (5Q)",
 "note": ""
 },
 {
 "pin": "Pino 5",
 "signal": "A5",
 "path": "FT -> 373 Pino 16 (7Q)",
 "note": ""
 },
 {
 "pin": "Pino 6",
 "signal": "A4",
 "path": "373 Pino 19 (8Q)",
 "note": ""
 },
 {
 "pin": "Pino 7",
 "signal": "A3",
 "path": "373 Pino 9 (4Q)",
 "note": ""
 },
 {
 "pin": "Pino 8",
 "signal": "A2",
 "path": "FT -> 373 Pino 6 (3Q)",
 "note": ""
 },
 {
 "pin": "Pino 9",
 "signal": "A1",
 "path": "FT -> 373 Pino 5 (2Q)",
 "note": ""
 },
 {
 "pin": "Pino 10",
 "signal": "A0",
 "path": "RM3 Pino 5 -> FT -> 373 Pino 2 (1Q)",
 "note": ""
 },
 {
 "pin": "Pino 11",
 "signal": "I/O0",
 "path": "RM3 Pino 9 -> 373 Pino 3 (1D) -> 66K Pino 2 (AD0) -> IC9 Pino 11",
 "note": ""
 },
 {
 "pin": "Pino 12",
 "signal": "I/O1",
 "path": "RM3 Pino 8 -> 373 Pino 4 (2D) -> 66K Pino 3 (AD1) -> IC9 Pino 12",
 "note": ""
 },
 {
 "pin": "Pino 13",
 "signal": "I/O2",
 "path": "RM3 Pino 7 -> 373 Pino 7 (3D) -> 66K Pino 4 (AD2) -> IC9 Pino 13",
 "note": ""
 },
 {
 "pin": "Pino 14",
 "signal": "GND",
 "path": "ROM Pino 20 (/CE) -> FT -> 373 Pino 10 (GND) -> FT -> 373 Pino 1 (/OE)",
 "note": ""
 },
 {
 "pin": "Pino 15",
 "signal": "I/O3",
 "path": "RM3 Pino 6 -> 373 Pino 8 (4D) -> 66K Pino 5 (AD3) -> IC9 Pino 14",
 "note": ""
 },
 {
 "pin": "Pino 16",
 "signal": "I/O4",
 "path": "373 Pino 18 (8D) -> 66K Pino 6 (AD4) -> IC9 Pino 15",
 "note": ""
 },
 {
 "pin": "Pino 17",
 "signal": "I/O5",
 "path": "373 Pino 17 (7D) -> 66K Pino 7 (AD5) -> IC9 Pino 16",
 "note": ""
 },
 {
 "pin": "Pino 18",
 "signal": "I/O6",
 "path": "373 Pino 13 (5D) -> 66K Pino 8 (AD6) -> IC9 Pino 17",
 "note": ""
 },
 {
 "pin": "Pino 19",
 "signal": "I/O7",
 "path": "373 Pino 14 (6D) -> 66K Pino 9 (AD7) -> IC9 Pino 18",
 "note": ""
 },
 {
 "pin": "Pino 20",
 "signal": "/CE",
 "path": "ROM Pino 14 (GND) -> FT -> 373 Pino 10 (GND) -> FT -> 373 Pino 1 (/OE)",
 "note": ""
 },
 {
 "pin": "Pino 21",
 "signal": "A10",
 "path": "FT -> 66K Pino 12 (A10)",
 "note": ""
 },
 {
 "pin": "Pino 22",
 "signal": "/OE",
 "path": "C29 -> R39 (na parte de trás da placa) -> 66K Pino 25 (/PSEN)",
 "note": ""
 },
 {
 "pin": "Pino 23",
 "signal": "A11",
 "path": "FT -> 66K Pino 13 (A11)",
 "note": ""
 },
 {
 "pin": "Pino 24",
 "signal": "A9",
 "path": "FT -> 66K Pino 11 (A9)",
 "note": ""
 },
 {
 "pin": "Pino 25",
 "signal": "A8 ",
 "path": "FT -> 66K Pino 10 (A8 )",
 "note": ""
 },
 {
 "pin": "Pino 26",
 "signal": "A13",
 "path": "66K Pino 15 (A13)",
 "note": ""
 },
 {
 "pin": "Pino 27",
 "signal": "A14",
 "path": "66K Pino 16 (A14)",
 "note": ""
 },
 {
 "pin": "Pino 28",
 "signal": "VCC",
 "path": "ROM Pino 1 (/WE) -> C49 -> 373 Pino 20 (VCC)",
 "note": ""
 }
 ]
 }
 ]
 },
 {
 "id": "usdm-p28-p05",
 "label": "USDM P28 / P05",
 "groups": [
 {
 "label": "Latch 373",
 "rows": [
 {
 "pin": "Pino 1",
 "signal": "/OE",
 "path": "373 Pino 10 -> ROM Pino 14 (GND)",
 "note": ""
 },
 {
 "pin": "Pino 2",
 "signal": "1Q",
 "path": "ROM Pino 10 (A0)",
 "note": ""
 },
 {
 "pin": "Pino 3",
 "signal": "1D",
 "path": "RM3 Pino 2 -> ROM Pino 11 (I/O0) -> 66K Pino 1 (AD0)",
 "note": ""
 },
 {
 "pin": "Pino 4",
 "signal": "2D",
 "path": "RM3 Pino 3 -> ROM Pino 12 (I/O1) -> 66K Pino 2 (AD1)",
 "note": ""
 },
 {
 "pin": "Pino 5",
 "signal": "2Q",
 "path": "ROM Pino 9 (A1)",
 "note": ""
 },
 {
 "pin": "Pino 6",
 "signal": "3Q",
 "path": "ROM Pino 8 (A2)",
 "note": ""
 },
 {
 "pin": "Pino 7",
 "signal": "2D",
 "path": "RM3 Pino 4 -> ROM Pino 13 (I/O2) -> 66K Pino 3 (AD2)",
 "note": ""
 },
 {
 "pin": "Pino 8",
 "signal": "2D",
 "path": "RM3 Pino 5 -> ROM Pino 15 (I/O3) -> 66K Pino 4 (AD3)",
 "note": ""
 },
 {
 "pin": "Pino 9",
 "signal": "4Q",
 "path": "ROM Pino 7",
 "note": ""
 },
 {
 "pin": "Pino 10",
 "signal": "GND",
 "path": "373 Pino 1 -> ROM Pino 14 (GND)",
 "note": ""
 },
 {
 "pin": "Pino 11",
 "signal": "LE",
 "path": "66K Pino 22 (ALE)",
 "note": ""
 },
 {
 "pin": "Pino 12",
 "signal": "5Q",
 "path": "ROM Pino 4 (A6)",
 "note": ""
 },
 {
 "pin": "Pino 13",
 "signal": "5D",
 "path": "RM3 Pino 8 -> ROM Pino 18 (I/O6) -> 66K Pino 7 (AD6)",
 "note": ""
 },
 {
 "pin": "Pino 14",
 "signal": "6D",
 "path": "RM3 Pino 9 -> ROM Pino 19 (I/O7) -> 66K Pino 8 (AD7)",
 "note": ""
 },
 {
 "pin": "Pino 15",
 "signal": "6Q",
 "path": "ROM Pino 3 (A7)",
 "note": ""
 },
 {
 "pin": "Pino 16",
 "signal": "7Q",
 "path": "ROM Pino 5 (A5)",
 "note": ""
 },
 {
 "pin": "Pino 17",
 "signal": "7D",
 "path": "RM3 Pino 7 -> ROM Pino 17 (I/O5) -> 66K Pino 6 (AD5)",
 "note": ""
 },
 {
 "pin": "Pino 18",
 "signal": "8D",
 "path": "RM3 Pino 6 -> ROM Pino 16 (I/O4) -> 66K Pino 5 (AD4)",
 "note": ""
 },
 {
 "pin": "Pino 19",
 "signal": "8Q",
 "path": "ROM Pino 6 (A4)",
 "note": ""
 },
 {
 "pin": "Pino 20",
 "signal": "VCC",
 "path": "ROM Pino 28 (VCC) -> ROM Pino 1 (/WE)",
 "note": ""
 }
 ]
 },
 {
 "label": "Suporte de ROM",
 "rows": [
 {
 "pin": "Pino 1",
 "signal": "VCC",
 "path": "ROM Pino 28 (VCC) -> 373 Pino 20 (VCC)",
 "note": ""
 },
 {
 "pin": "Pino 2",
 "signal": "A12",
 "path": "66K Pino 13 (A12)",
 "note": ""
 },
 {
 "pin": "Pino 3",
 "signal": "A7",
 "path": "373 Pino 15 (6Q)",
 "note": ""
 },
 {
 "pin": "Pino 4",
 "signal": "A6",
 "path": "373 Pino 12 (5Q)",
 "note": ""
 },
 {
 "pin": "Pino 5",
 "signal": "A5",
 "path": "373 Pino 16 (7Q)",
 "note": ""
 },
 {
 "pin": "Pino 6",
 "signal": "A4",
 "path": "373 Pino 19 (8Q)",
 "note": ""
 },
 {
 "pin": "Pino 7",
 "signal": "A3",
 "path": "373 Pino 9 (4Q)",
 "note": ""
 },
 {
 "pin": "Pino 8",
 "signal": "A2",
 "path": "373 Pino 6 (3Q)",
 "note": ""
 },
 {
 "pin": "Pino 9",
 "signal": "A1",
 "path": "373 Pino 5 (2Q)",
 "note": ""
 },
 {
 "pin": "Pino 10",
 "signal": "A0",
 "path": "373 Pino 2 (1Q)",
 "note": ""
 },
 {
 "pin": "Pino 11",
 "signal": "I/O0",
 "path": "RM3 Pino 2 -> 373 Pino 3 (1D) -> 66K Pino 1 (AD0)",
 "note": ""
 },
 {
 "pin": "Pino 12",
 "signal": "I/O1",
 "path": "RM3 Pino 3 -> 373 Pino 4 (2D) -> 66K Pino 2 (AD1)",
 "note": ""
 },
 {
 "pin": "Pino 13",
 "signal": "I/O2",
 "path": "RM3 Pino 4 -> 373 Pino 7 (3D) -> 66K Pino 3 (AD2)",
 "note": ""
 },
 {
 "pin": "Pino 14",
 "signal": "GND",
 "path": "373 Pino 10 (GND) -> 373 Pino 1 (/OE)",
 "note": ""
 },
 {
 "pin": "Pino 15",
 "signal": "I/O3",
 "path": "RM3 Pino 5 -> 373 Pino 8 (4D) -> 66K Pino 4 (AD3)",
 "note": ""
 },
 {
 "pin": "Pino 16",
 "signal": "I/O4",
 "path": "RM3 Pino 6 -> 373 Pino 18 (8D) -> 66K Pino 5 (AD4)",
 "note": ""
 },
 {
 "pin": "Pino 17",
 "signal": "I/O5",
 "path": "RM3 Pino 7 -> 373 Pino 17 (7D) -> 66K Pino 6 (AD5)",
 "note": ""
 },
 {
 "pin": "Pino 18",
 "signal": "I/O6",
 "path": "RM3 Pino 8 -> 373 Pino 13 (5D) -> 66K Pino 7 (AD6)",
 "note": ""
 },
 {
 "pin": "Pino 19",
 "signal": "I/O7",
 "path": "RM3 Pino 9 -> 373 Pino 14 (6D) -> 66K Pino 8 (AD7)",
 "note": ""
 },
 {
 "pin": "Pino 20",
 "signal": "/CE",
 "path": "R54 (e o outro lado do R54 está ligado a GND)",
 "note": ""
 },
 {
 "pin": "Pino 21",
 "signal": "A10",
 "path": "66K Pino 11 (A10)",
 "note": ""
 },
 {
 "pin": "Pino 22",
 "signal": "/OE",
 "path": "R49 -> 66K Pino 23 (/PSEN)",
 "note": ""
 },
 {
 "pin": "Pino 23",
 "signal": "A11",
 "path": "66K Pino 12 (A11)",
 "note": ""
 },
 {
 "pin": "Pino 24",
 "signal": "A9",
 "path": "66K Pino 10 (A9)",
 "note": ""
 },
 {
 "pin": "Pino 25",
 "signal": "A8",
 "path": "66K Pino 9 (A8 )",
 "note": ""
 },
 {
 "pin": "Pino 26",
 "signal": "A13",
 "path": "66K Pino 14 (A13)",
 "note": ""
 },
 {
 "pin": "Pino 27",
 "signal": "A14",
 "path": "66K Pino 15 (A14)",
 "note": ""
 },
 {
 "pin": "Pino 28",
 "signal": "VCC",
 "path": "ROM Pino 1 (/WE) -> 373 Pino 20 (VCC)",
 "note": ""
 }
 ]
 }
 ]
 }
 ]
}
```

## Notas de origem e incertezas

> [!IMPORTANT]
> A lista de latches do JDM P30-901 rotula os pinos 7 e 8 do latch como `2D`, enquanto a lista correspondente do suporte de ROM rotula essas ligações como `3D` e `4D`. Os dados pesquisáveis preservam os rótulos arquivados e sinalizam a contradição em vez de a corrigir silenciosamente.

- A lista do JDM P30-901 foi registada em 28 de dezembro de 2004.
- A lista do USDM P28/P05 foi registada em 14 de novembro de 2005.
- A fonte indica que o mapeamento do P05 foi validado posteriormente e que o nome da resistência do pino 20 da ROM foi corrigido para `R54`.
- A compatibilidade além das ECUs mencionadas não foi confirmada na fonte arquivada.

## Relacionado

- [Introdução à modificação de ECU (chipping)](/cars/tuning/introduction-to-ecu-chipping)
- [Modificando a ECU JDM P30](/cars/ecu/chipping-jdmp30)
- [Referência de hardware de ECU OBD1](/cars/ecu/ecu-hardware)
- [Referência do latch 74HC373](/cars/ecu/74hc373)
