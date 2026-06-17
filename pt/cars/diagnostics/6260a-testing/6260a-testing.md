---
summary: 'Análise técnica do código de teste da ECU Honda 6260A, explicando como ativa o LED de diagnóstico para piscar os códigos de erro do motor.'
tags: [ecu, referência, sensores, diagnósticos]
applies_to:
  obd: [0, 1, 2]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: '6260A Testing'
    url: /pgmfi/wiki/library/6260a-testing
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Teste do 6260A

J. Wong: sobre a questão do 6260A... se olhares para o código ([91 PM6_ECU_LED_CEL](/cars/diagnostics/91pm6-ecu-led-cel)) que faz piscar o LED da [ECU](/cars/ecu/ecu) para os códigos, verás que escreve #16 ou #96 em X2000, dependendo de certas condições. Uma experiência de bancada que quero fazer é substituir 16/96 por outros valores e ver o que acontece... por exemplo, em vez de o led piscar, observar que outra linha iria alternar estado
