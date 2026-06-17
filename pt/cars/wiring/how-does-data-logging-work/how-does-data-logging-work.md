---
summary: 'Existe uma série de programas que lhe permitem registar dados (data logging) sobre o funcionamento do seu motor, lendo informações diretamente da ECU.'
applies_to:
  obd: [0, 1, 2]
complexity: advanced
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - wiring
  - conversion
sources:
  - name: 'pgmfi.org wiki'
    title: 'Como Funciona o Data Logging'
    url: /pgmfi/wiki/library/how-does-data-logging-work
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Como Funciona o Data Logging

Existe uma série de programas que lhe permitem registar dados (datalog) sobre o funcionamento do seu motor, lendo informações diretamente da [ECU](/cars/ecu/ecu). Para as minhas [ECU](/cars/ecu/ecu)s [OBD](/cars/wiring/obd)1, utilizo o software CROME Pro ou Freelog no meu PC para registar o que está a acontecer. Estes pacotes de software utilizam uma porta série no PC (por vezes implementada com um adaptador USB) para enviar comandos e receber dados da [ECU](/cars/ecu/ecu). Há imensa informação nesta wiki sobre como configurar a sua [ECU](/cars/ecu/ecu) para poder comunicar com o PC. Basicamente, precisa de ligar o transmissor da [ECU](/cars/ecu/ecu) ao recetor do PC e ligar o recetor da [ECU](/cars/ecu/ecu) ao transmissor do PC. A porta série da [ECU](/cars/ecu/ecu) funciona com níveis de tensão [TTL](/cars/sensors/ttl) e a maioria das portas série de PC funcionam com níveis de tensão RS232, pelo que deve ser utilizado algum tipo de conversor/tradutor de sinal. Assim que o hardware da porta série estiver operacional, precisa de substituir o software que controla a porta série da [ECU](/cars/ecu/ecu) por um software que a controle de forma a conseguir comunicar com o software no PC. Eu utilizo o plugin de datalogging de John Cui no CROME para instalar este patch de software no binário (programa) da [ECU](/cars/ecu/ecu) que pretendo monitorizar. Esse binário é gravado num chip de memória flash ou [EPROM](/cars/rom/eprom) e instalado na [ECU](/cars/ecu/ecu) do carro. Assim que o motor estiver a funcionar com a [ECU](/cars/ecu/ecu) modificada e o software de datalogging do PC estiver a correr, e ambos estiverem a comunicar entre si, pode iniciar o registo de dados. Quando indica ao software do PC para iniciar o datalogging, este começa a enviar comandos para a [ECU](/cars/ecu/ecu). O software de datalogging adicionado ao binário da [ECU](/cars/ecu/ecu) recebe cada comando, interpreta-o e devolve os resultados, que o software do PC adiciona depois a um ficheiro de registo (log). Tipicamente, é utilizado um comando para obter um dado da [ECU](/cars/ecu/ecu). Com o patch de datalogger do John Cui, por exemplo, existem comandos padrão para obter os dados que a maioria das pessoas deseja, tais como [RPM](/cars/sensors/rpm), leituras da sonda de O2, leituras do sensor MAP, etc. Também existem comandos que lhe permitem ler qualquer endereço de [RAM](/cars/reference/ram) para registar dados monitorizados com menos frequência. O software de datalogging no PC apenas percorre todos os comandos para obter os dados que deseja e depois repete a mesma sequência continuamente, tão rápido quanto o PC consiga processar. Depois de registar os dados do seu carro enquanto este funciona sob diferentes cargas, pode utilizar esses dados para perceber como alterar várias características operacionais do software da [ECU](/cars/ecu/ecu), tais como os mapas de combustível e de ignição. Isto é feito com um software editor de ROM como o CROME para [ECU](/cars/ecu/ecu)s [OBD](/cars/wiring/obd)1. -- markolson - 24 Out 2005
