---
summary: 'A base de código VTEC de 1 fio (1wire VTEC) é uma ROM para as ECU OBD0 MPFI que permite utilizar o solenoide de bloqueio da transmissão automática (Automatic Transmission Lockup Solenoid) para controlar a ativação do VTEC.'
applies_to:
  obd: [0]
complexity: beginner
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - wiring
  - conversion
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: '1 Wire Vtec'
    url: /pgmfi/wiki/library/1-wire-vtec
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# 1 Wire VTEC

A base de código VTEC de 1 fio é uma [ROM](/cars/rom/rom) para as [ECU](/cars/ecu/ecu)s [OBD0 MPFI](/cars/diagnostics/obd0mpfi) que permite utilizar o [solenoide de bloqueio da transmissão automática](/cars/sensors/automatic-transmission-lockup-solenoid) para controlar a ativação do VTEC. Jason Parker idealizou as alterações de [hardware para o VTEC de um fio](/cars/rom/hardware-for-one-wire-vtec). Desde 2 de outubro de 2003 que está funcional, mas precisa de alguma ajuda e testes adicionais. Dave Blundell tem vários carros a circular com este sistema. Se quiser contribuir/trabalhar/ver o projeto, consulte o módulo de código ***1w_vtec*** no [Source Forge](/cars/wiring/source-forge).
