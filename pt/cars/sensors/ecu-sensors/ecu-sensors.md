---
summary: 'Os sensores de entrada que uma ECU Honda lê para gerir o combustível e a ignição.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - ecu
  - sensors
sources:
  - name: 'pgmfi.org wiki'
    title: 'Sensores da ECU'
    url: /pgmfi/wiki/library/ecu-sensors
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Sensores da ECU

Sensores presentes em quase todos os motores Honda:

- [Sensor de Posição da Cambota (Crankshaft Position Sensor)](/cars/ignition/crankshaft-position-sensor) - Determina o ponto para a injeção de combustível e ignição de `cada` cilindro, e também deteta a velocidade do motor.
- Sensor do Ponto Morto Superior (Top Dead Center Sensor) - Determina o ponto de ignição no arranque (cranking) e quando o ângulo da cambota é anormal.
- [Sensor de Posição do Cilindro (Cylinder Position Sensor)](/cars/sensors/cylinder-position-sensor) - Deteta a posição do cilindro #1 para ignição sequencial para `cada` cilindro.
- Temperatura do Líquido de Refrigeração do Motor - ou entrada de termopar ''ECT'' para a temperatura do líquido de refrigeração do motor
- [Sensor de Temperatura do Ar de Admissão](/cars/sensors/intake-air-temperature-sensor) - ou entrada de termopar ''IAT'' para a temperatura do ar de admissão
- Sensor MAP - Sensor de Pressão Absoluta do Coletor, permite à [ECU](/cars/ecu/ecu) ajustar a Relação Ar-Combustível com base na densidade do ar de admissão
- Sensor de Oxigénio - Mede o teor de oxigénio nos gases de escape
- Pressão Atmosférica - ou ''PA'' ou ''Sensor de Pressão Barométrica'' mede a pressão atmosférica.
- Sensor TPS - Sensor de Posição do Acelerador
- Sensor de Velocidade do Veículo - ou ''VSS'' mede a velocidade a que os ***semi-eixos*** estão a rodar
- Válvula de Controlo do Ar de Ralenti / Válvula de Controlo de Ar Eletrónica - Ou ''IAC/EACV'' ajuda a controlar o ralenti

Sensores opcionais:
- Detetor de Carga Elétrica - ou ''ELD'' presente na maioria dos carros dos EUA para medir o nível de carga elétrica
- [Sensor de Detonação (Knock Sensor)](/cars/ignition/knock-sensor) - Um dispositivo semelhante a um microfone para detetar a Pré-Ignição (detonação) em motores DOHC VTEC.
- Sensor Pa - Sensor de Pressão Atmosférica
- Solenoide VTEC = solenoide para direcionar o fluxo de óleo para ativar o VTEC (apenas em motores VTEC :) )

---

Outros Sensores de [ECU](/cars/ecu/ecu) normalmente não presentes em motores Honda:
- Sensor Maf
