---
summary: 'Tudo o que precisa de fazer é remover o R135. Quando modifico algumas ECUs P05, às vezes acende-se uma luz fixa do Cruise Control quando uso um painel Ex.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - ecu
  - referência
  - sensores
sources:
  - name: 'pgmfi.org wiki'
    title: 'Como Eliminar a Luz de Upshift / Cruise Control'
    url: /pgmfi/wiki/library/get-rid-of-cruise-control-upshift-light
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Como Eliminar a Luz de Upshift / Cruise Control

Tudo o que precisa de fazer é remover o `R135`. Quando modifico algumas ECUs [P05](/cars/wiring/p05), às vezes acende-se uma luz fixa do Cruise Control ao usar um painel de instrumentos (cluster) EX. Ou uma luz fixa de Upshift ao usar um painel CX/VX. Então fui investigar e descobri que a luz do cruise control e a de upshift usam o mesmo pino na ECU, o D18. Segui as pistas na placa e estas levaram-me ao resistor `R135`. Removi esse resistor e já está, a luz de Cruise/Upshift desapareceu.
