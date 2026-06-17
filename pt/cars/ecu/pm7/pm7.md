---
summary: 'Especificações de hardware, diferenças de layout de placa e binários de ROM originais para a ECU OBD0 DOHC ZC PM7.'
applies_to:
  brand: Honda
  engines: [D16A8, D16A9, D16Z5]
  obd: [0]
complexity: intermediate
tags:
  - ecu
  - reference
sources:
  - name: 'pgmfi.org wiki'
    title: PM7
    url: /pgmfi/wiki/library/pm7
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Guia da ECU OBD0 ZC PM7

A ECU PM7 era a unidade de controlo do motor principal utilizada nos motores DOHC ZC de 1988–1991 (tais como o D16A8, D16A9 e D16Z5) encontrados nos Civics e CRXs do mercado europeu e japonês (por exemplo, o CRX 1.6i-16). 

Do ponto de vista do software, o código base da PM7 é quase idêntico ao código base da PM6 SOHC D16A6. Devido a esta semelhança arquitetónica, as ROMs personalizadas e afinadas de uma ECU podem ser executadas na outra com pequenos ajustes nas configurações dos sensores.

---

## 1. Revisões e Scans da Placa

Abaixo estão os scans de layout do lado dos componentes e das soldas para diferentes revisões da placa PM7:

### PM7-E020 Europeia
Esta revisão era comummente encontrada nos CRXs DOHC de especificação europeia:

![Scan do Layout do Lado dos Componentes da PM7-E020 Europeia](PM7-E020_component.jpg)
*Scan do lado dos componentes (vista superior) da placa da PM7-E020 europeia.*

![Scan do Layout do Lado das Soldas da PM7-E020 Europeia](PM7-E020_solder.jpg)
*Scan do lado das soldas (vista inferior) da placa da PM7-E020 europeia.*

---

### Layouts Alternativos da PM7

![Scan do Layout do Lado dos Componentes da PM7-0330 JDM](PM7-0330_component.jpg)
*Vista superior do lado dos componentes da placa da PM7-0330 JDM.*

![Scan da placa experimental da Honda ZC PM7](zc-experimental-ecu.jpg)
*Scan superior de um protótipo inicial e experimental da ECU PM7.*

---

## 2. Binários de ROM e Downloads

Para análise e reprogramação, pode descarregar os ficheiros BIN de calibração da ROM original:

*   [Descarregar a ROM Original da PM7-0330 JDM](Pm7-03301989.bin) *(32 KB, Calibração original do DOHC ZC JDM de 1989)*
*   [Descarregar a ROM Original da PM7 Europeia](PM7-euro.bin) *(32 KB, Calibração alemã do DOHC ZC D16Z5 de 125 CV)*
