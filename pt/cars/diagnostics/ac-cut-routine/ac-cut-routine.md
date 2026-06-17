---
summary: 'Autor: evo (61.88.2.177) Data: 030403 22:15 Após muita reflexão, decidi partilhar a minha rotina de corte do Ar Condicionado.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - sensors
  - reference
  - diagnostics
  - ecu
sources:
  - name: 'pgmfi.org wiki'
    title: 'Rotina de Corte de AC'
    url: /pgmfi/wiki/library/ac-cut-routine
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Rotina de Corte de AC

Autor: evo (61.88.2.177) Data: 03-04-03 22:15 Após muita reflexão, decidi partilhar a minha rotina de corte (Cutoff) do Ar Condicionado. Esta rotina desliga o a/c abaixo de um nível especificado de RPM OU TPS. JBR off 11.2, 4320 ; Jump if A/C switch is Off J XXXX ; Hook Code located at XXXX LC A, 6D8D ; Load Target rpm
 CMP AC, A ; Compare Actual rpm to Target rpm
 JLT 6D8A ; Jump if Actual rpm < Target
 LCB A, 6D8F ; Load Target TPS
 CMPB 6F, A ; Compare Actual TPS to Target TPS
 JGT 6D8A ; Jump if Actual TPS > Target
 SB off 26.4
 J 430C
 J 432B ; Jump to Cut A/C
O código está localizado perto do offset 4300 no P30 203
