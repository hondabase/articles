---
summary: 'Valores de RP17 e RP18 : : Automático RP17 2.7K RP18 4.7K isto é para placa c/ ref: 02d015501500 Auto para Manual: remover rp17, remover rp18, adicionar uma ponte em rp18...'
applies_to:
  obd: [1]
  brand: Honda
complexity: intermediate
tags:
  - ecu
  - reference
  - sensors
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD1P08 Auto Manual'
    url: /pgmfi/wiki/library/obd1p08-auto-manual
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1P08 Auto Manual

| | Valores de RP17 e RP18 | | :--- | :--- | | | **Automático** | | RP17 | 2.7K | | RP18 | 4.7K | isto é para o número de peça de placa: 02d01550-1500 Auto para Manual: remover rp17, remover rp18, adicionar uma ponte (jumper) em rp18 Manual para Auto:

- remover a ponte (jumper) em RP18 (Não tenho a certeza do que estará aqui)
- adicionar 4.7kOhm +/- 5% em RP18 SMD
- adicionar 2.7kOhm +/- 5% em RP17 SMD
- adicionar `IC15` & `IC16` [5050 S](/cars/rom/515x-high-side-switch) ou equiv.
- adicionar condensadores em `C73`, c74, c75, c76 (valores??? 0.1 uf ? devem ser cerâmicos)
- adicionar díodos em D13 e D12 (montagem em superfície [SMD] de 1A serve)
- adicionar q29 q28
- adicionar c57

- Ainda não tenho a certeza sobre quaisquer transístores... Se alguém tiver uma P08 Manual e puder tirar uma foto de alta qualidade da parte superior e inferior, por favor envie-as por e-mail para mim.. CRXSi RVtec (mailto:[email protected]) | **Anexo:** | **Modificar:** | **Tamanho:** | **Data:** | **Autor:** | **Comentário:** | | :--- | :--- | :--- | :--- | :--- | :--- | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [PC030021.JPG](PC030021.JPG) | mod | 143950 | 30 Mar 2004 - 02:14 | eg6ajk | [ECU](/cars/ecu/ecu)s [JDM](/cars/sensors/jdm) P08 (auto) |
