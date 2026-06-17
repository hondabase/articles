---
summary: 'A Pressão Absoluta refere-se a medições de pressão feitas numa escala onde o Vácuo Absoluto = 0. A Pressão Atmosférica é de aproximadamente 14.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - tuning
  - rom
  - sensors
  - reference
  - diagnostics
  - ecu
sources:
  - name: 'pgmfi.org wiki'
    title: 'Absolute Pressure'
    url: /pgmfi/wiki/library/absolute-pressure
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Pressão Absoluta

A Pressão Absoluta refere-se a medições de pressão feitas numa escala onde o [Vácuo Absoluto](/cars/sensors/absolute-vacuum) = 0. *

- A [Pressão Atmosférica](/cars/wiring/atmospheric-pressure) é de aproximadamente 14.7 psi ao nível do mar, medindo a pressão absoluta.
- 10 psi de [Boost](/cars/rom/boost) é aproximadamente 24.7 psi (14.7 psi de [Pressão Atmosférica](/cars/wiring/atmospheric-pressure) + 10 psi de [Boost](/cars/rom/boost)) ao nível do mar, medindo a pressão absoluta.
- Da mesma forma, 30 psi no manómetro de pressão dos pneus do seu carro é aproximadamente 44.7 psi de [Pressão Absoluta](/cars/diagnostics/absolute-pressure) (14.7 psi de [Pressão Atmosférica](/cars/wiring/atmospheric-pressure) + 30 psi de pressão dos pneus).

---

Um editor que exibe em [Pressão Absoluta](/cars/diagnostics/absolute-pressure) assemelha-se a isto: ![abs_pressure_crome.jpg](abs_pressure_crome.jpg)A Coluna 10 é aproximadamente a pressão atmosférica, ligeiramente inferior devido a interpolação ou ao facto de que mesmo em [WOT](/cars/reference/wot) haverá algum vácuo. A Coluna 1 é algo arbitrária, e não o zero verdadeiro (também conhecido como vácuo absoluto). Veja também [Sensor MAP](/cars/fueling/map-sensor) para os valores que o [Sensor MAP](/cars/fueling/map-sensor) OEM é capaz de ler.
