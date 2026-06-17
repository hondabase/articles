---
summary: 'A Pressão Relativa ocorre quando desconsideramos o facto de estarmos constantemente rodeados pela pressão atmosférica (aproximadamente 14,5 psi).'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - tuning
  - rom
  - sensors
  - reference
sources:
  - name: 'pgmfi.org wiki'
    title: 'Relative Pressure'
    url: /pgmfi/wiki/library/relative-pressure
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Pressão Relativa

A [Pressão Relativa](/cars/rom/relative-pressure) ocorre quando desconsideramos o facto de estarmos constantemente rodeados pela pressão atmosférica (aproximadamente 14,5 psi). Portanto, se se disser que um recipiente contém 10 psi de pressão relativa, a sua pressão absoluta será na verdade 10 psi + 14,5 == 24,5 psi. ---

Um editor que exibe em [Pressão Relativa](/cars/rom/relative-pressure) assemelha-se a isto: ![rel_pressure_uber.jpg](rel_pressure_uber.jpg) A coluna 10 é aproximadamente a pressão atmosférica, ligeiramente menor devido a interpolação ou ao facto de que, mesmo em [WOT](/cars/reference/wot), existirá algum vácuo. A coluna 1 é um tanto arbitrária, e não o zero real, ou seja, vácuo absoluto. Veja também o [Sensor MAP](/cars/fueling/map-sensor) para obter os valores que o [Sensor MAP](/cars/fueling/map-sensor) original (OEM) é capaz de ler.
