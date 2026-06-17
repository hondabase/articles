---
summary: 'Como dimensionar os injetores de combustível para o seu objetivo de potência.'
complexity: intermediate
tags:
  - injectors
  - fueling
  - tuning
sources:
  - name: 'pgmfi.org wiki'
    title: 'Dimensionamento de Injetores'
    url: /pgmfi/wiki/library/injector-sizing
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Dimensionamento de Injetores

Os injetores de combustível devem ser dimensionados para fornecer um fluxo de combustível adequado em valores máximos de HP/RPM/Boost (pressão de sobrealimentação), garantindo ao mesmo tempo que sejam suficientemente pequenos para permitir um fluxo reduzido durante o ralenti. A maioria dos sistemas PGM-FI tem uma largura de pulso (pulsewidth) mínima do injetor de 1 milissegundo, o que limita o tamanho máximo do injetor. Por exemplo, um injetor de 1000cc irá afogar um motor Honda 1.6L de fábrica em ralenti porque uma largura de pulso de 1ms é simplesmente demasiado combustível. Poderíamos entrar em muita teoria aqui, mas, de longe, a explicação mais abrangente sobre o dimensionamento de injetores pode ser encontrada na [RC Engineering](http://www.rceng.com).

### Upgrades de Injetores

Um upgrade comum para Hondas turboalimentados ou atmosféricos de alta potência é substituir os injetores originais (geralmente de 240cc ou 290cc) por injetores de 450cc de veículos Mitsubishi e Chrysler de 4 cilindros turbo (frequentemente chamados de DSM para Diamond-Star Motors, uma parceria colaborativa entre as duas empresas cujo nome é baseado no logótipo de cada uma das empresas), mas estes injetores estão a tornar-se mais caros à medida que todos descobrem esta modificação. Existem muitos outros injetores OEM de outros carros que são adequados para uso em Hondas... certifique-se apenas de obter também as fichas dos injetores de combustível, pois estas costumam ser diferentes entre marcas, além de investigar se os injetores são Peak and Hold ou Saturados, pois uma caixa de resistências (resistor box) pode ser necessária. Uma lista de taxas de fluxo de injetores para muitos carros OEM pode ser encontrada [aqui](http://www.robietherobot.com/storm/fuelinjectorguide.htm).
