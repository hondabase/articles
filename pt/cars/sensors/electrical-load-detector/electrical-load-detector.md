---
summary: 'O Electrical Load Detector (Detector de Carga Elétrica) mede a carga elétrica para determinar se o alternador deve estar em modo de baixa ou alta potência.'
applies_to:
  obd: [0, 1, 2]
  brand: Honda
complexity: beginner
tags:
  - sensors
  - reference
sources:
  - name: 'pgmfi.org wiki'
    title: 'Electrical Load Detector'
    url: /pgmfi/wiki/library/electrical-load-detector
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Electrical Load Detector

O Electronic Load Detector (Detector de Carga Elétrica) mede a carga elétrica — usado para determinar se o alternador deve estar em modo de baixa ou alta potência. Como os motores Honda funcionam com uma mistura muito pobre ao ralenti, praticamente qualquer carga fará com que a rotação do ralenti diminua. Mesmo pequenas cargas elétricas, como os piscas, farão com que o ralenti flutue. O detector de carga elétrica (ELD) foi adicionado aos modelos mais recentes da Honda para monitorizar quaisquer cargas elétricas significativas. Ele envia um sinal de aviso ao ECM antes que a carga tenha oportunidade de afetar o ralenti. O ECM faz pequenos ajustes na válvula de controlo de ar do ralenti (IAC), no tempo de injeção (PW) e no ponto de ignição para compensar a carga elétrica.
