---
summary: 'Esta página explica como substituir o chip atual 5128 XRAM 2K SRAM por um NVSRAM DS1220 para uma futura solução RTP.'
tags: [hardware, education, ecu, tuning, rom, sensors, reference, wiring, conversion, diagnostics]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Replace M5128'
    url: /pgmfi/wiki/library/replace-m5128
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Substituir `M5128`

Esta página explica como substituir o chip atual [5128 XRAM](/cars/honda/civic/ef/tuning/5128xram) 2K [SRAM](/cars/sensors/sram) por um `DS1220` [NVSRAM](/cars/wiring/nvsram) para uma futura solução [RTP](/cars/sensors/rtp).

- Breve Explicação
- Lista de Peças:
- Construção:
- Passo a passo:
-

**Nota:**

### Breve Explicação 

O chip `M5128` é utilizado para armazenar e calcular valores enquanto o carro está a trabalhar. Por padrão, os pinos 19 e 22 estão ligados à massa (ground), impedindo assim o endereçamento total de 2k. Além disso, é uma boa ideia substituir o atual `M5128` por um módulo `DS1220` [NVSRAM](/cars/wiring/nvsram). Este módulo comporta-se como uma RAM normal, mas o conteúdo da sua [RAM](/cars/reference/ram) será mantido mesmo quando a alimentação for cortada.

### Lista de Peças: 

- 1x DS1220AB
- 1x Suporte de CI de 24 pinos
- Fio de calibre 22 gauge (ou mais fino)

### Construção: 

É bastante simples, mas requer alguma destreza. Primeiro, é necessário dessoldar o `M5128`. Depois, deve cortar as pistas dos pinos 19 e 22, uma vez que ambos ligam à massa (ground). Solde o suporte de CI de 24 pinos. Em seguida, solde um fio do pino 19 do `M5128` ao pino 23 do [MCU](/cars/ecu/mcu) e solde também um fio do pino 22 do `M5128` ao pino 22 do [MCU](/cars/ecu/mcu).

### Passo a passo: 

- Dessoldar o `M5128`
- Cortar as pistas para a massa dos pinos 19 e 22
- Soldar o suporte de CI de 24 pinos
- Soldar um fio do pino 19 do `M5128` ao pino 23 do [MCU](/cars/ecu/mcu)
- Soldar um fio do pino 22 do `M5128` ao pino 22 do [MCU](/cars/ecu/mcu)
- Colocar o DS1220AB

###

**Nota:** 

As pistas a cortar numa [ECU](/cars/ecu/ecu) de 90-91 encontram-se no lado dos componentes. Nas de 88-89, há 1 pista no lado das soldaduras e 1 no lado dos componentes. Pode verificar as digitalizações (scans) para ajudar.

| **Anexo:** | **Modificar:** | **Tamanho:** | **Data:** | **Quem:** | **Comentário:** |
| :--- | :--- | :--- | :--- | :--- | :--- |
| ![](/pgmfi/wiki/assets/icn/bmp.gif) [DS1220-88-89.jpg](DS1220-88-89.jpg) | mod | 681906 | 27 Feb 2004 - 17:48 | synoptic | Lado das soldaduras de uma [ECU](/cars/ecu/ecu) de 1988 - 1989 |
| ![](/pgmfi/wiki/assets/icn/bmp.gif) [DS1220-90-91.jpg](DS1220-90-91.jpg) | mod | 728209 | 27 Feb 2004 - 17:49 | synoptic | Lado das soldaduras de uma [ECU](/cars/ecu/ecu) de 1990 - 1991 |
| ![](/pgmfi/wiki/assets/icn/bmp.gif) [DS1220-TOP-90-91.jpg](DS1220-TOP-90-91.jpg) | mod | 115939 | 27 Feb 2004 - 17:50 | synoptic | Lado dos componentes de uma [ECU](/cars/ecu/ecu) de 1990 - 1991 |
