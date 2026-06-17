---
summary: 'Aprenda a interpretar as etiquetas de identificação nas ECUs Honda OBD1 para determinar a sua origem, compatibilidade com o motor e tipo de transmissão.'
tags: [ecu, reference, tuning, rom, sensors, diagnostics]
applies_to:
  obd: [1]
  brand: Acura/Honda
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Label Decode'
    url: /pgmfi/wiki/library/label-decode
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Descodificação de Etiquetas

Pode descobrir-se muita coisa ao ler a etiqueta de uma [ECU](/cars/ecu/ecu) [OBD](/cars/wiring/obd)1. Isto aplica-se principalmente às [ECU](/cars/ecu/ecu) de Civic... não sei em relação às de Integra. **37820-ABC-XYZ**| **Dígitos** | **Significado** | | :--- | :--- | | ABC | Motor para o qual a [ECU](/cars/ecu/ecu) foi concebida | | X | Mercado da [ECU](/cars/ecu/ecu) - ver tabela abaixo | | Y | 0: 5 velocidades, 5: Auto | | Z | número par: placa "11F0", número ímpar: placa "1720" | | **Código** | **Mercado** | | :--- | :--- | | Axx | [USDM](/cars/sensors/usdm) 49 estados | | Lxx | [USDM](/cars/sensors/usdm) Emissões de Cali | | xxx | [JDM](/cars/sensors/jdm) | | Jxx | [JDM](/cars/sensors/jdm) | | 9xx | [JDM](/cars/sensors/jdm) (auto) | | Gxx | [EDM](/cars/wiring/edm) | | Qxx | [Oz DM](/cars/reference/oz-dm) | | Cxx | Canadiano | | Nxx | normalmente reprogramada de fábrica, sem mercado específico | Exemplo: **37820-P28-A52**

- P28 = [SOHC](/cars/sensors/sohc) VTEC D16Z6
- A = EUA, 49 estados
- 5 = Auto
- 2 = placa "11F0"

| *Library. LabelDecode movido de Library. OBD1LabelDecode em 21 Abr 2004 - 15:31 por Home.blundar

* - [reverter](https://web.archive.org/web/http://www.pgmfi.org/twiki/bin/rename/Library/LabelDecode?newweb=Library&newtopic=OBD1LabelDecode&confirm=on "Clique para mover o tópico de volta para a localização anterior, com a opção de alterar referências.") | | :--- |
