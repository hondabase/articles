---
summary: 'Existem duas formas de corrigir um erro de checksum. A primeira consiste em alterar o programa da ROM de modo a desativar/remover a rotina de checksum.'
applies_to:
  obd: [0, 1]
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: 'Manual Checksum'
    url: /pgmfi/wiki/library/manual-checksum
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Checksum Manual

Existem duas formas de corrigir um erro de checksum. A primeira consiste em alterar o programa da [ROM](/pt/cars/rom/rom) de modo a desativar/remover a rotina de checksum. Aprenda a programar se quiser fazer isto. Se se contenta em contornar o procedimento de checksum, continue a ler.

O checksum em todas as [ROM](/pt/cars/rom/rom)s [OBD0](/pt/cars/rom/obd0) /1 é de 8 bits - o que significa que irá variar de 0 a 255. (00-FF hex) Para descobrir qual é o checksum, precisa de fazer um [Check Sum](/pt/cars/diagnostics/check-sum) de 8 bits sobre o ficheiro. Creio que a PM6 se preocupa com a área de 0000-4FFF. A maioria das [ECU](/pt/cars/ecu/ecu)s [OBD1](/pt/cars/wiring/obd1) preocupa-se com toda a [ROM](/pt/cars/rom/rom).

Creio que o WinHex pode calcular isto, e também pode obter um utilitário chamado check8 em [http://www.keil.com](http://www.keil.com). Isto também funcionará muito bem... De qualquer forma, digamos que executa o programa de checksum e obtém um checksum de A3 (hex). Subtraia A3 de FF: FF - A3 = 5C. Agora, encontre um "FF" em algum lugar do intervalo que a [ECU](/pt/cars/ecu/ecu) está a utilizar para o checksum. O melhor é procurar um bloco de "FF"s, pois isso geralmente indica espaço não utilizado na [ROM](/pt/cars/rom/rom). Altere o FF para o resultado da sua subtração. Voila. Checksum corrigido.
