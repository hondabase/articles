---
summary: 'Guia detalhado sobre a configuração e reprogramação do código de ROM personalizada UberData para ECUs OBD1 P72.'
applies_to:
  brand: Acura
  ecus: [P72]
  obd: [1]
complexity: advanced
tags:
  - tuning
  - rom
  - software
sources:
  - name: 'pgmfi.org wiki'
    title: 'Uber P72'
    url: /pgmfi/wiki/library/uber-p72
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Mapa de ROM do Uber P72

A ROM **Uber P72** é uma base de código de fábrica modificada da [ECU OBD1 P72](/cars/sensors/p72) do Acura Integra GS-R, concebida para funcionar com a suite de afinação UberData. 

Esta página documenta os offsets de endereço RAM e ROM específicos para as modificações do UberData. Para os endereços de fábrica do P72 Honda/Acura, consulte o [Mapa de ROM do P72](/cars/sensors/p72) padrão.

## Mapeamento de Endereços RAM

A tabela abaixo apresenta localizações de RAM específicas utilizadas pelo código personalizado do UberData numa ROM P72:

| Offset Hex | Comprimento (Bytes) | Descrição | Notas |
| :---: | :---: | :--- | :--- |
| `645D` | 2 | RPM de VTEC Alternativo UberData ERM | Configuração alternativa de limite |
| `645F` | 2 | RPM de VTEC Alternativo UberData ERM | Configuração alternativa de limite |
| `6464` | 2 | RPM de VTEC Alternativo UberData ERM | Configuração alternativa de limite |
| `6466` | 2 | RPM de VTEC Alternativo UberData ERM | Configuração alternativa de limite |
