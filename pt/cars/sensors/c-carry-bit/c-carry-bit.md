---
summary: 'Na arquitetura 8051, "C" é o nome do carry bit. Quando uma operação aritmética sofre um overflow, o carry bit é ativado para registar essa alteração.'
applies_to:
  obd: [0, 1, 2]
complexity: advanced
tags:
  - sensors
  - reference
sources:
  - name: 'pgmfi.org wiki'
    title: 'C Carry Bit'
    url: /pgmfi/wiki/library/c-carry-bit
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# C Carry Bit

Na arquitetura 8051, "C" é o nome do carry bit (bit de transporte). Quando uma operação aritmética ultrapassa o limite (overflow), o carry bit é ativado (set) para registar essa alteração. Este bit também é frequentemente utilizado como um espaço de armazenamento temporário para transferência de bits. Isto também se aplica à arquitetura Oki 66k; as instruções `MB C, x` e `MB x, C` permitem um acesso fácil à carry flag.
