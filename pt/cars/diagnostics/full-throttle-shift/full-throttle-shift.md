---
summary: 'Um guia para implementar o Full Throttle Shift (FTS) em ECUs Honda OBD1, permitindo passagens de caixa mais rápidas ao manter a pressão de turbo e a rotação durante as mudanças.'
tags: [ecu, referência, afinação, rom, sensores, diagnóstico]
applies_to:
  brand: Honda
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Full Throttle Shift'
    url: /pgmfi/wiki/library/full-throttle-shift
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Full Throttle Shift (Flat Shift)

***Full Throttle Shift*** (Passagem de caixa a aceleração total) Esta é simplesmente uma extensão do conceito por trás do Full-Throttle Launch (também chamado [Launch Control](/cars/tuning/launch-control)) que permite um limite de rotação diferente enquanto o condutor está a mudar de mudança num carro de transmissão manual. O Full-throttle shift é geralmente conseguido intercetando o código do [Limitador de Rotação](/cars/sensors/rev-limiter) para que ele utilize um limite de rotação diferente dependendo do estado de alguma entrada digital, nomeadamente uma ligada a um interruptor na embraiagem... ***Full throttle shift em 3 passos simples:***- Primeiro tem de escrever uma rotina em assembler para fazer [Full Throttle Shift](/cars/diagnostics/full-throttle-shift) (ou em hexadecimal para os masoquistas. ;)
- Depois tem de fazer um interruptor montado na embraiagem. Para muitos Honda sem controlo de velocidade de cruzeiro (cruise control), o [Interruptor do Cruise Control](/cars/wiring/cruise-control-switch) é provavelmente o mais fácil.
- Ligue um dos lados do interruptor à massa (ground)
- Ligue o outro lado do interruptor à entrada digital que utilizou no código (o Pino B7 [off(00211h).5 é uma boa escolha para [OBD1](/cars/wiring/obd1)).

Quase consigo ouvir agora... ''"Mas isso são 4 passos, Dave ! ! !"'' Tem razão, eu ''DISSE'' "3 passos simples"... e o primeiro passo não é um deles :P''
