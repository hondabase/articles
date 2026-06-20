---
summary: 'Explicação técnica das funcionalidades de limitador de rotação "two-step" (controlo de arranque) em ECUs Honda, auxiliando em arranques consistentes do veículo parado.'
tags: [hardware, education, tuning, sensors, reference]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Launch Control'
    url: /pgmfi/wiki/library/launch-control
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Controlo de Arranque (Launch Control)

O controlo de arranque (launch control) refere-se a um limitador de rotação de duas etapas ("two-step"). O funcionamento operacional disto é bastante simples: existe um [Limitador de Rotação (Rev Limiter)](/cars/sensors/rev-limiter) mais baixo enquanto o carro está parado, para que possas acelerar a fundo sem causar perigo para o motor. Ao soltar a embraiagem, o carro começa a mover-se e o [Limitador de Rotação](/cars/sensors/rev-limiter) baixo é desativado, permitindo conduzir o carro normalmente. O principal objetivo do [Controlo de Arranque (Launch Control)](/cars/tuning/launch-control) é permitir arranques ***consistentes***, mantendo o carro no mesmo nível de [RPM](/cars/sensors/rpm) em `cada` arranque.

- [addExtrafeatures.js](addExtrafeatures.js):
