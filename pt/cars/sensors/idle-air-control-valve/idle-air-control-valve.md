---
summary: 'A válvula de controlo de ar do ralenti, ou IACV, regula o ralenti do carro com base na temperatura do líquido de arrefecimento.'
tags: [ecu, reference, sensors]
applies_to:
  brand: Honda
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Idle Air Control Valve'
    url: /pgmfi/wiki/library/idle-air-control-valve
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Válvula de Controlo de Ar do Ralenti (IACV)

A válvula de controlo de ar do ralenti, ou IACV, regula o ralenti do carro com base na temperatura do líquido de arrefecimento.

- Configurações de ralenti desejado vs. [ECT](/cars/sensors/ect): 
 ![honda_EACV_target_idle.jpg](honda_EACV_target_idle.jpg)

**Nota:** isto é controlado pela [ECU](/cars/ecu/ecu) e pode ser alterado.

## Resolução de Problemas & Reparação

Se tens uma luz de aviso de motor (CEL) persistente com o Código 14 ou um ralenti muito baixo/instável, o circuito integrado de controlo (driver) interno da tua ECU pode estar queimado. Consulta o guia [Reparação do Circuito da IACV - R58 & R59](/cars/diagnostics/iacv-circuit-fix-r58-r59) para veres os passos de diagnóstico e detalhes de reparação dos componentes.
