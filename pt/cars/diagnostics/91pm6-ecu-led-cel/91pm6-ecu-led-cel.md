---
summary: 'Explicação técnica da rotina de piscar do LED de diagnóstico/CEL dentro do código-fonte da ECU PM6 OBD0 de 1991.'
applies_to:
  brand: Honda
  ecus: [PM6]
  obd: [0]
complexity: beginner
tags:
  - diagnosticos
  - ecu
sources:
  - name: 'pgmfi.org wiki'
    title: 'LED de Diagnóstico/CEL da ECU PM6 de 1991'
    url: /pgmfi/wiki/library/91pm6-ecu-led-cel
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Rotina de Piscar do LED de Diagnóstico (CEL) da ECU PM6 de 1991

Nas ECUs Honda OBD0 como a **PM6 de 1991** (encontrada no Civic e CRX Si), os códigos de diagnóstico são lidos através de um LED vermelho montado diretamente na placa de circuito da ECU. Este LED é visível através de uma pequena janela transparente na tampa metálica da ECU. Quando ocorre uma falha no sensor, a luz de verificação do motor (CEL) é ativada e a ECU pisca o LED de diagnóstico para indicar o código de falha.

## Localização e Comportamento do Código

Para programadores que desmontam ou modificam a ROM da PM6 de 1991, a rotina de piscar do LED está localizada em ou perto do offset **`026E`** no código assembly.

Em vez de utilizar um loop de atraso (delay) padrão da CPU — o que interromperia a execução da ECU e perturbaria os cálculos críticos de sincronização de combustível/ignição — a rotina de piscar está integrada no **manipulador de interrupção do Timer 0** (Timer 0 interrupt handler).

### Características Principais:
* **Frequência de Interrupção:** O manipulador de interrupção do Timer 0 é executado a **100 Hz** (100 vezes por segundo).
* **Lógica Não Bloqueante:** A rotina mantém registadores de contagem para monitorizar o número de interrupções decorridas. Ao contar estas interrupções, a ECU sabe exatamente quanto tempo deve manter o LED no estado LIGADO ou DESLIGADO para produzir piscadelas de diagnóstico limpas sem bloquear outros processos.
