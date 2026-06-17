---
summary: 'Modelação da tensão de saída do sensor MAP num valor utilizável.'
applies_to:
  obd: [0, 1, 2]
  brand: Honda
complexity: intermediate
tags:
  - tuning
  - rom
  - sensors
  - reference
sources:
  - name: 'pgmfi.org wiki'
    title: 'Map Sensor Equation'
    url: /pgmfi/wiki/library/map-sensor-equation
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Equação do Sensor MAP

Modelação da tensão de saída do [Sensor MAP](/cars/fueling/map-sensor) num valor utilizável. (Do Manual Helm:) ![honda_stock_map_volt.jpg](/pgmfi/wiki/media/library/MapSensor/honda_stock_map_volt.jpg) y = mx + b y = mx + 2.85v y = (-.1)x + 2.85v (-.1)x = y - 2.85 ***x = (y - 2.85v) / (-.1)***A Alldata publica uma especificação para o sensor MAP. Recolhi dados do meu sensor MAP para comparar e adicionei os dados de acordo com a fórmula baseada no manual Helm:

```

05 in Hg| Alldata: 2.5 | 2.35 fórmula baseada no Helm | meu valor real: 2.460 
10 in Hg| Alldata: 2.0 | 1.85 fórmula baseada no Helm | meu valor real: 1.938 
15 in Hg| Alldata: 1.5 | 1.35 fórmula baseada no Helm | meu valor real: 1.509 
20 in Hg| Alldata: 1.0 | 0.85 fórmula baseada no Helm | meu valor real: 1.012 
25 in Hg| Alldata: 0.5 | 0.35 fórmula baseada no Helm | meu valor real: 0.558 
```

Com base na especificação da Alldata, a fórmula é: ***x = (y - 3.0v)/(-.1)***Parece que estas duas fórmulas te podem dar um intervalo razoável para calibração. -- markolson - 04 Mar 2005
