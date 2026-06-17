---
summary: 'É possível correr o código de uma ECU OBD0 MPFI noutra? A resposta curta é sim. O seguinte já foi testado antes e sabe-se que funciona com sucesso:...'
applies_to:
  obd: [0]
complexity: advanced
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: 'Compatibilidade de Código OBD0'
    url: /pgmfi/wiki/library/obd0-code-compatibility
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Compatibilidade de Código OBD0

É possível correr o código de uma [ECU OBD0 MPFI](/cars/diagnostics/obd0mpfi) noutra? A resposta curta é sim. O seguinte já foi testado antes e sabe-se que funciona com sucesso:

- PM6 em PR4 (ver notas)
- PR4 em PM6 (ver notas)
- PM7 em PM6
- PM7 em PR4 (ver notas)
- PM6 em PS9
- PS9 em PR4 (ver notas)

Em teoria, o código também deverá ser intercambiável quase na perfeição entre:
- PG7
- Trash.PM6
- PM7
- PS9
- PR5
- PP5

A PR4 e a PM8 [USDM](/cars/sensors/usdm) utilizam placas de circuito ligeiramente diferentes. A PM8 parece estar mais próxima das restantes [ECUs](/cars/ecu/ecu) desta família do que a PR4, que apresenta algumas diferenças assinaláveis.

***Notas***: No entanto, existem alguns aspetos a ter em conta que poderão causar problemas:
* **Presença ou ausência de um sensor PA interno.** (isto verifica-se principalmente na [OBD0 PR4](/cars/ecu/obd0pr4))
* **Presença ou ausência de um sensor ELD.** (este está presente nos carros/software dos EUA e ausente na maioria dos carros/programas [JDM](/cars/sensors/jdm) e [EDM](/cars/wiring/edm))
* **Presença ou ausência de um sensor de oxigénio (O2).** (alguns motores ZC PM7 [EDM](/cars/wiring/edm) possuem um sensor IMA em vez de O2. O mesmo acontece com a Mugen XE3)
* **Utilização invulgar de entradas:** Direção assistida (Power Steering) na PR4.
* **[Oki83 C154](/cars/diagnostics/oki83c154) vs [Oki80 C154](/cars/diagnostics/oki80c154) e design de EPROM** - as [ECUs](/cars/ecu/ecu) de 88-89 quase sempre carecem de [EPROMs](/cars/rom/eprom).

Em resumo, a maior parte do código das [ECUs](/cars/ecu/ecu) desta família correrá noutras [ECUs](/cars/ecu/ecu) da mesma família, mas poderão existir sistemas secundários (AC, ELD, Direção Assistida, para ser mais específico) que não funcionem bem quando a PR4 está envolvida. Resta saber exatamente o que deve ser feito com as [ECUs](/cars/ecu/ecu) PM8 [USDM](/cars/sensors/usdm).
