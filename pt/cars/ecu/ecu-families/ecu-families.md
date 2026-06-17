---
summary: 'Uma visão geral de diferentes gerações e famílias de unidades de controlo do motor (ECU) da Honda (OBD0, OBD1 e OBD2) e a sua compatibilidade.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - ecu
  - referência
sources:
  - name: 'pgmfi.org wiki'
    title: 'Ecu Families'
    url: /pgmfi/wiki/library/ecu-families
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Famílias e Gerações de ECUs Honda

As Unidades de Controlo do Motor (ECUs) da Honda estão agrupadas em diferentes gerações e famílias com base no ano do modelo, configuração do motor e tipo de injeção de combustível. Compreender estas famílias é crítico ao planear swaps de motor, conversões de OBD ou modificação de sockets para afinação personalizada (tuning).

## Visão Geral das Gerações de ECUs
- **Pre-OBD:** Sistemas de injeção de combustível antigos (tipicamente 1985–1987).
- **OBD0 DualPoint (DPFI):** Sistemas de injeção de combustível dual-point (1988–1991, até 1995 na Europa).
- **OBD0 MultiPoint (MPFI):** Sistemas de injeção de combustível multi-point para motores não-VTEC e antigos VTEC (1988–1991).
- **OBD1 MPFI:** A geração mais popular para socketing e afinação personalizada (1992–1995).
- **OBD2 MPFI:** Geração de diagnóstico avançado (1996+).

## Famílias Pre-OBD
Estes designs antigos de injeção de combustível tipicamente utilizam mecanismos externos de avanço de vácuo.
- **PG7:** Acura Integra USDM/JDM 1986–1987 (motor D16A1 com avanço de vácuo).
- **PE7:** Civic/CRX Si EDM/USDM 1985–1987 (motores EW3/EW4 com avanço de vácuo).
- **PJ1:** Integra 1.6i-16 / CRX Mk1 1.6i-16 EDM 1985–1987.
- **PJ7:** Prelude 2.0 Si 1986–1987 (motor B20A3).
- **PJ0:** Accord A20 1986–1989 (avanço de vácuo).
- **PL2:** Honda/Acura V6 1986–1988 (motores `C25`/`C27`).

## Famílias OBD0 DualPoint (DPFI)
Usadas em modelos Honda de entrada de gama que apresentam injeção dual-point.
- **PM5:** Civic Std / CRX DX 1988–1991.
- **PM9:** Civic Std / CRX DX 1988–1991.
- **P04:** EG Civic DXi Europeu 1992–1995.
- **PW1:** Concerto 1.5i Europeu 1989–1995.

## Famílias OBD0 MultiPoint (MPFI)

### Civic e Integra Não-VTEC (Design de Placa Comum)
As seguintes ECUs partilham um layout comum de placa de circuito com pequenas variações de componentes:
- **PG7:** Acura Integra 1988–1989 (motor D16A1 com avanço eletrónico).
- **PM6:** Civic/CRX SOHC Si 1988–1991 (motor D16A6).
- **PM7:** Civic Si DOHC ZC 1989–1991 (EF3 JDM ou Accord A20A Europeu).
- **PP5:** Honda Concerto / Rover UK 216/220/416/420 (GSi/GTi) 1988–1994.
- **PR5:** JDM Integra ZXi 1990–1991 (SOHC 1.6L).
- **PS9:** Civic EX USDM 1990–1991 (SOHC 1.6L, tipicamente automático).
- **XE5:** Plataforma Mugen Race 1988–1991 (motor ZC).

### Prelude e Accord B20A Não-VTEC
- **PK2:** Prelude 1988–1991 (3ª Geração com motor B20A).
- **PH3:** Accord JDM 1986–1989 (motor B20A).

### Designs Únicos de Placa OBD0
As PM8 e PR4 apresentam designs únicos de placa-mãe, embora o seu código ROM partilhe compatibilidade com outras ECUs MPFI:
- **PM8:** CRX HF 1988–1991.
- **PR4:** Integra LS/GS USDM 1990–1991 (motor B18A1). Nota: Também existe uma versão OBD1 da PR4.

## Famílias OBD1 (1992–1995) MPFI Families
Todas as ECUs de Civic e Integra de 92–95 utilizam um de três designs principais de placa-mãe. As ECUs individuais podem ser convertidas ou modificadas (ex: adicionando VTEC, controlo de transmissão automática ou coletores de admissão secundários) preenchendo os componentes em falta na placa.

### ECUs OBD1 Civic e Integra 92-95
- **P05:** Civic CX 1992–1995 (motor D15B8, sensor O2 de 1 fio).
- **P06:** Civic DX/LX 1992–1995 (motor D15B7).
- **P07:** Civic VX 1992–1995 (motor D15Z1 VTEC-E, utiliza um sensor O2 de mistura pobre de 5 ou 6 fios).
- **P08:** Civic/CRX VTi/VXi JDM 1992–1995 (SOHC VTEC D15B).
- **P27:** Civic Euro/Asiático 1992–1995 (1.6L não-VTEC).
- **P28:** Civic EX/Si 1992–1995 (SOHC VTEC D16Z6).
- **P29:** Domani JDM 1992–1995 (DOHC ZC).
- **P30:** Del Sol VTEC / Civic SiR JDM 1992–1995 (DOHC VTEC B16A).
- **P54:** Domani/Accord JDM 1992–1995 (1.8L B18B DOHC).
- **P61:** Acura Integra GS-R 1992–1993 (DOHC VTEC B17A1).
- **P70:** Domani JDM 1992–1995 (SOHC VTEC ZC - sem interruptor de pressão de óleo).
- **P71:** Integra JDM 1992–1995 (SOHC VTEC D16A).
- **PR3:** Integra RSi/XSi JDM 1992–1993 (DOHC VTEC B16A).
- **PR4:** Acura Integra RS/LS/GS 1992–1993 (B18A1).
- **P72:** Acura Integra GS-R 1994–1995 (DOHC VTEC B18C1 com coletores de admissão secundários/IAB).
- **P74 / P75:** Acura Integra RS/LS/GS 1992–1995 (B18B1).
- **P76:** Integra JDM 1994–1995 (SOHC ZC).
- **P84:** Civic ETi JDM 1992–1995 (VTEC-E, transmissão automática).
- **P91:** Civic Coupe JDM 1992–1995 (SOHC VTEC 1.6L).
- **P1J / P1K:** Civic fabricado no Reino Unido 1996–2000 (motores D14, 75cv/90cv).

### ECUs OBD1 Prelude e Accord 92-95
Estas ECUs partilham princípios de design semelhantes aos da família Civic/Integra, mas estão alojadas em caixas diferentes:
- **P0A:** Accord EX 1994–1995 (F22B1 SOHC VTEC).
- **P0B:** Accord 1992–1995 (F22B2 SOHC não-VTEC).
- **P0C:** Accord 1992–1995 (F22B DOHC não-VTEC).
- **PT3:** Accord 1990–1993 (F22A1/F22A4/F22A6 SOHC).
- **PT5:** Accord Europeu 1990–1993 (F20A7).
- **PT6:** Accord EX 1991–1993 (F22A6, SOHC não-VTEC com IAB).
- **P11:** Prelude 2.0i 1992–1995 (BB3 com F20A4 non-VTEC).
- **P12:** Prelude S 1992–1995 (F22A6 SOHC não-VTEC).
- **P13:** Prelude VTEC 1993–1995 (H22A DOHC VTEC).
- **P14:** Prelude Si 1993–1995 (H23A1 DOHC não-VTEC).
- **P39:** Prelude BB4 JDM 1992–1995 (F22B DOHC não-VTEC).
