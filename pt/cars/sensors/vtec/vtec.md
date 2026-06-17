---
summary: "O VTEC é o sistema patenteado da Honda para perfis de cames variáveis. Efetivamente dá a um motor dois perfis de cames independentes."
applies_to:
  obd: [0, 1, 2]
  brand: Honda
complexity: beginner
tags:
  - sensors
  - reference
sources:
  - name: 'pgmfi.org wiki'
    title: Vtec
    url: /pgmfi/wiki/library/vtec
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# VTEC

O VTEC é o sistema patenteado da Honda para [Cam Profile](/cars/reference/cam-profile)s (perfis de cames) variáveis. Efetivamente dá a um motor dois perfis de cames independentes. A ideia é que o [Low Cam](/cars/sensors/low-cam) tem condições ideais para baixas [RPM](/cars/sensors/rpm)s e o [High Cam](/cars/sensors/high-cam) tem condições ideais para [RPM](/cars/sensors/rpm)s mais elevadas. Os motores VTEC têm geralmente uma faixa de potência mais ampla caracterizada por duas "corcovas" (humps), em oposição a apenas uma corcova nos motores sem VTEC. O [VTEC Crossover Point](/cars/rom/vtec-crossover-point) ideal pode ser encontrado sobrepondo um gráfico de teste de potência (dyno) do [Low Cam](/cars/sensors/low-cam) e do [High Cam](/cars/sensors/high-cam) e vendo onde estes se cruzam.
