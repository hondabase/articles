---
summary: 'Dave Blundell diz "Vernon (deluded) enviou-me grande parte desta informação." Como regra geral, as PR4 de 90 têm sensores PA externos, e as ECUs de 91 têm sensores PA internos.'
applies_to:
  obd: [0, 1, 2]
  ecus: [PR4]
complexity: intermediate
tags:
  - ecu
  - referência
  - afinação
  - rom
  - sensores
  - diagnósticos
sources:
  - name: 'pgmfi.org wiki'
    title: 'Adjust PR4 Pa Sensor'
    url: /pgmfi/wiki/library/adjust-pr4-pa-sensor
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Ajustar o Sensor PA da PR4

Dave Blundell diz "Vernon (deluded) enviou-me grande parte desta informação." Como regra geral, as PR4 de 90 têm sensores PA externos, e as [ECU](/cars/ecu/ecu)s de 91 têm sensores PA internos. Pode identificar (até certo ponto) ao olhar para o "código" da [ECU](/cars/ecu/ecu): | **Etiqueta** | **Descrição** | | :--- | :--- | | A00 | 90 5 Velocidades (programa -33) | | A01 | 90 5 Velocidades (programa ??) | | A02 | 90 5 Velocidades (programa -54) | | A51 | 90 Automático (programa ??) | | A52 | 90 Automático (programa -54) | | A10 | 91 5 Velocidades (programa -92) | | A12 | 91 5 Velocidades (programa -92) | | A60 | 91 Automático (programa -92) | | A62 | 91 Automático (programa -92) | Ok, com isso esclarecido... É fácil selecionar se deve usar um sensor [PA](/cars/rom/pressure-atmosphere) interno ou externo. Veja a seguinte tabela: | **Componente** | **PA Externo** | **PA Interno** | | :--- | :--- | :--- | | Sensor PA | em falta | instalado | | `C103` | em falta | presente(103Z) | | `R92` | jumper | 10Kohm | | `C106` | em falta | presente(103Z) | ***editar***Parece que a [ECU](/cars/ecu/ecu) com PA Interno não tem o `C106`, e a [ECU](/cars/ecu/ecu) com PA Externo tem o `C106` presente.
