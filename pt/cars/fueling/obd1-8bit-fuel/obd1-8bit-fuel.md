---
summary: 'Referência de fórmula técnica para interpretar valores de combustível de 8 bits em tabelas de editores de ROM para a gestão de motor Honda OBD1.'
tags: [ecu, reference, tuning, sensors, obd1]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD1 8bit Fuel'
    url: /pgmfi/wiki/library/obd1-8bit-fuel
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1 8bit Fuel

Dado o valor da tabela ''v'' e o valor do multiplicador ''m'', o valor do combustível conforme visto num editor de [ROM](/cars/tuning/rom) é: Fuel(''v'',''m'') = ''v*m''/4

---

O resultado é presumivelmente proporcional à quantidade de combustível que entra no motor. Tem um intervalo efetivo de 0-16256.25 -- então, como se relaciona isto com o ciclo de trabalho (duty cycle) dos injetores?

Largura de pulso (ms) = PW = (''v*m''/4)/100 + 0.60ms = ''v*m''/400 + 0.60ms
O Ciclo de Trabalho Máximo é (((1000*60*2/rpm)*0.9ms)
Ciclo de Trabalho (Duty Cycle) = PW/TRPM = (''v*m''/400 + 0.60)/(60000/''RPM'')
Simplificando, Ciclo de Trabalho = ''RPM''*(''v*m'' + 240)/24000000

***Isto baseia-se em informações fornecidas por Didier Pelegri e não foi verificado por mim.***--AndySloane
