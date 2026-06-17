---
summary: 'PP5 : 90-93 (??) UK Rover 216 Cabrio. A Rover (Reino Unido) tinha um acordo com a Honda onde motores Honda (ZC, principalmente) acabavam em carros Rover.'
applies_to:
  obd: [0]
  brand: Honda
complexity: intermediate
tags:
  - hardware
  - education
  - ecu
  - tuning
  - rom
  - sensors
  - reference
  - wiring
  - conversion
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: PP5
    url: /pgmfi/wiki/library/pp5
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# PP5

## PP5 : 90-93 (??) UK Rover 216 Cabrio

A Rover (Reino Unido) tinha um acordo com a Honda através do qual os motores Honda (principalmente o ZC) eram utilizados em carros da Rover. Aparentemente, continuaram a utilizar fichas e distribuidores do estilo [OBD0](/cars/rom/obd0) até ao início dos anos 90. Parecem ser bastante semelhantes à maioria das [ECU](/cars/ecu/ecu)s da época.

O PP5-E01 é uma ECU sem ROM (romless) que equipava os primeiros Rover 216, 416, GSi, GTi e possivelmente os 220 e 420. Estas primeiras [ECU](/cars/ecu/ecu)s sem ROM estão maioritariamente instaladas em Rovers sem sensores Lambda. As primeiras ECU são difíceis de chipar e requerem algum tipo de adaptador, semelhante às PM6 e PM7 sem ROM.
As alternativas são as PP5-G01, PP4-`R00` ou PP4-G01, que creio serem todas ECU com [ROM](/cars/rom/rom) externa e comuns no Reino Unido. São todas ECU OBD0 não-VTEC, devendo ser intercambiáveis com as PM7, PM6, etc. Algumas destas [ECU](/cars/ecu/ecu)s utilizam um APS (Sensor de Pressão Atmosférica) que pode causar [CEL](/cars/wiring/cel)/Limp Mode quando este não está presente. 

PP5-E01 Rover 216 GTi (sem lambda)
PP5-G01 Rover 216 GTi (com lambda), Honda Concerto 1.6 litros (DOHC) 93-96
PP4-G01 Rover 216 16V (com lambda), Honda Concerto 1.6 litros (SOHC) 92-96 
PP4-`R00` Rover 220 Coupe (com lambda), Honda Concerto 1.6 litros (SOHC) 93-96 
PP5-`R00` Honda Concerto 1.6 litros (DOHC) 93-96 

| **Anexo:** | **Modificar:** | **Tamanho:** | **Data:** | **Quem:** | **Comentário:** |
| :--- | :--- | :--- | :--- | :--- | :--- |
| ![](/pgmfi/wiki/assets/icn/bmp.gif) [PP5-E01-zdyne\_component.jpg](PP5-E01-zdyne_component.jpg) | mod | 1260999 | 18 Dec 2003 - 21:18 | The Admin | Digitalização do lado superior da ECU PP5 de Mark Lamond - Zdyne SECU |
| ![](/pgmfi/wiki/assets/icn/bmp.gif) [PP5-E01zdyne\_solder.jpg](PP5-E01zdyne_solder.jpg) | mod | 1763475 | 18 Dec 2003 - 21:18 | The Admin | Digitalização da parte inferior da PP5 de Mark Lamond - Zdyne SECU |
| ![](/pgmfi/wiki/assets/icn/bmp.gif) [IMG\_1436.JPG](IMG_1436.JPG) | mod | 1793377 | 21 Oct 2004 - 09:14 | CREX | PP5-G01 |
| ![](/pgmfi/wiki/assets/icn/bmp.gif) [PP5-G01.JPG](PP5-G01.JPG) | mod | 1793377 | 21 Oct 2004 - 11:47 | CREX | PP5-G01 |
