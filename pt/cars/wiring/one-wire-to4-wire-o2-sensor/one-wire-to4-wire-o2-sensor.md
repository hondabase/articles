---
summary: 'Se tens uma ECU a que falta o circuito de aquecimento de O2, como uma P05, é fácil ativar esta funcionalidade.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - ecu
  - referência
  - sensores
  - cablagem
  - conversão
  - diagnósticos
sources:
  - name: 'pgmfi.org wiki'
    title: 'One Wire To4 Wire O2 Sensor'
    url: /pgmfi/wiki/library/one-wire-to4-wire-o2-sensor
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Conversão de Sensor de O2 de 1 Fio para 4 Fios

Se tiveres uma [ECU](/cars/ecu/ecu) a que falte o circuito de aquecimento do sensor de O2, como uma P05, é fácil ativar esta funcionalidade. Para converter uma P05 em praticamente qualquer outra, precisas de adicionar um transístor para ativar o aquecedor do sensor de O2, caso contrário irás obter um código de erro. É necessário adicionar o `Q30` - o seu valor é [C144](/cars/sensors/c144). Para [ECU](/cars/ecu/ecu)s [JDM](/cars/sensors/jdm) a que falte o circuito de aquecimento do sensor de O2, como a P08, basta adicionar uma versão SMT do 2N4401 (transístor de comutação NPN de uso geral) na localização `Q15` na parte inferior da [PCB](/cars/wiring/pcb). O part number correto para o transístor é MMBT4401, e estes estão facilmente disponíveis através de fornecedores retalhistas como [http://web.archive.org/web/20260612163410/https://www.digikey.com/](http://web.archive.org/web/20260612163410/https://www.digikey.com/)
