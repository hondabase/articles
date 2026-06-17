---
summary: 'Procedimento de substituição de resistência para converter uma ECU OBD0 PR3 de transmissão automática para manual.'
applies_to:
  obd: [0]
  ecus: [PR3]
complexity: beginner
tags:
  - ecu
  - referencia
sources:
  - name: 'pgmfi.org wiki'
    title: 'PR3 Auto Manual'
    url: /pgmfi/wiki/library/pr3-auto-manual
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Conversão de Automático para Manual em ECU OBD0 PR3

Para converter uma ECU OBD0 PR3 de transmissão automática para uma configuração de transmissão manual:

1. Localize a resistência marcada como **`R68`** na placa da ECU (localizada perto da divisória central do PCB).
2. Dessorva e mova a resistência de **`R68`** para a pegada vazia em **`R67`**.

Consulte o diagrama de alta resolução da placa abaixo para a localização exata da resistência:

![Localização da modificação da resistência de transmissão automática para manual na ECU OBD0 PR3](OBD0_pr3-auto-manual.jpg)
