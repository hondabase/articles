---
summary: 'Um limitador de velocidade restringe a velocidade máxima de um automóvel. Em quase todos os Hondas, o Limitador de Velocidade é implementado como um trecho de código que lê o Sensor de Velocidade do Veículo (VSS) e corta o combustível acima de uma determinada velocidade.'
applies_to:
  obd: [0, 1, 2]
  brand: Honda
complexity: beginner
tags:
  - ecu
  - reference
  - sensors
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: 'Speed Limiter'
    url: /pgmfi/wiki/library/speed-limiter
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Limitador de Velocidade

Um limitador de velocidade restringe a velocidade máxima de um automóvel. Em quase todos os Hondas, o [Limitador de Velocidade](/cars/diagnostics/speed-limiter) é implementado como um trecho de código que lê o [Sensor de Velocidade do Veículo](/cars/wiring/vehicle-speed-sensor) e corta o combustível acima de uma determinada velocidade. As [ECU](/cars/ecu/ecu)s [JDM](/cars/sensors/jdm) são famosas por terem limitadores de velocidade. Se deseja ir a mais de 180 km/h sem reprogramar a [ECU](/cars/ecu/ecu), pode usar o dispositivo Speed Limit Defencer da Hondainfo. [Hondainfo Speed Limit Defencer](http://web.archive.org/web/20041120201535/http://cvs.sourceforge.net:80/viewcvs.py/pgmfi/Speed%20Limit%20Defencer/)
