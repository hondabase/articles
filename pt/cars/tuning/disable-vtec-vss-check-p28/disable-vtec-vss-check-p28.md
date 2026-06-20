---
summary: 'Guia técnico para contornar a verificação do Sensor de Velocidade do Veículo (VSS) na rotina de VTEC para ECUs Honda P28 OBD1.'
tags: [tuning, sensors, reference]
applies_to:
  ecus: [P28]
  make: Honda
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Disable Vtec VSS Check P28'
    url: /pgmfi/wiki/library/disable-vtec-vss-check-p28
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Disable VTEC VSS Check P28

**Autor:** Gimpy

Accord

**Data:** 08-14-03 03:42

- 1286- `C5` 22 19 : SB 22.1
- 1289- `C5` F3 `C0` 32 : CMPB F3, #32
- 128D- CA 1B : JLT 12AA
- 128F- `C5` D9 `C0` 44 : CMPB D9, #44
- 1293- CD 15 : JGE 12AA
- 1295- 90 9D FA 60 : LCB A, 60FA
- 1299- CE 03 : JNE 129E
- 129B- D8 31 0C : JBR off 31.0, 12AA
- 129E- DB 1E 03 : JBR off 1E.3, 12A4
- 12A1- ED 19 03 : JBS off 19.5, 12A7
- 12A4- E9 31 0B : JBS off 31.1, 12B2
- 12A7- E9 27 21 : JBS off 27.1, 12CB
- 12AA- `C5` 22 08 : RB 22.0
- 12AD- `C4` 27 0A : RB off 27.2
- 12B0- CB 29 : SJ 12DB

Compreendo que este é um tópico antigo, mas para os utilizadores de ROM P28 como eu (dar de ombros) definam `60FA` para `FF`. Basicamente, insiram os mesmos comentários onde apropriado a partir do post do doc... a menos que sejam picuinhas. Isto tornou-se um problema real no meu Accord. A minha transição VTEC (VTEC xover) é às 3000 rpm e é difícil chegar aos 20 mph (32 km/h) às 3000 rpm no meu carro :) Por isso, o VTEC só ativava por volta das 4000 rpm em 1ª mudança.
