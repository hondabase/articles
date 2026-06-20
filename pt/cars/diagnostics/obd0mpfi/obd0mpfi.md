---
summary: 'Existe uma família muito distinta de ECUs encontrada nos Honda OBD0 de aproximadamente 88-91. As principais características desta família: MCUs Oki80 C154 ou Oki83 C154 que são essencialmente Intel8051 com uma velocidade de relógio de 12Mhz.'
tags: [ecu, referencia, tuning, rom, sensores, diagnosticos]
applies_to:
  brand: Acura/Honda
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: OBD0MPFI
    url: /pgmfi/wiki/library/obd0mpfi
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD0MPFI

Existe uma família muito distinta de [ECU](/cars/ecu/ecu)s encontrada nos Honda [OBD0](/cars/tuning/obd0) de aproximadamente 88-91. As principais características desta família:

- [MCU](/cars/ecu/mcu)s [Oki80 C154](/cars/diagnostics/oki80c154) ou [Oki83 C154](/cars/diagnostics/oki83c154) que são essencialmente [Intel8051](/cars/ecu/intel8051) com uma [velocidade de relógio](/cars/sensors/clock-speed) de 12Mhz.
- Presença de [EPROM](/cars/ecu/eprom) Oki 38256 nos modelos de 90-91
- Motores [MPFI](/cars/sensors/mpfi) com 4 injetores
- Motores sem VTEC
- Distribuidores com avanço eletrónico
- Presença de chip controlador de [E/S (I/O)](/cars/sensors/io) [Oki6260 A](/cars/ecu/oki6260a)
- Presença de chip [ADC](/cars/wiring/adc) NEC [UPD7004 C](/cars/sensors/upd7004c)
- Presença de chip [SRAM](/cars/sensors/sram) [5128 XRAM](/cars/honda/civic/ef/tuning/5128xram) de 2K

Esta arquitetura também foi utilizada pela Rover no Reino Unido, aparentemente por um período consideravelmente mais longo do que os 4 anos em que esta arquitetura foi utilizada nos carros [USDM](/cars/sensors/usdm) e [JDM](/cars/sensors/jdm). Uma lista parcial de [ECU](/cars/ecu/ecu)s [OBD0](/cars/tuning/obd0):
- PG7 (88-89 Integra D16A1 - **nota**: a versão de 86-87 desta [ECU](/cars/ecu/ecu) comandava o motor D16A1 com avanço por vácuo. Família diferente)
- PM6 ([USDM](/cars/sensors/usdm) Civic/CRX Si - D16A6 [SOHC](/cars/sensors/sohc))
- PM7 ([JDM](/cars/sensors/jdm)/EDM Civic/CRX Si - ZC [DOHC](/cars/sensors/dohc))
- PM8 ([USDM](/cars/sensors/usdm) D15B? [SOHC](/cars/sensors/sohc) HF, [EDM](/cars/wiring/edm) D16Z? ZC [DOHC](/cars/sensors/dohc))
- PR4 ([USDM](/cars/sensors/usdm) 90-91 Int
- PR5 ([JDM](/cars/sensors/jdm) Integra ???)
- PP5 (UKDM Rover Cabrio?)
- PS9 ([USDM](/cars/sensors/usdm) Civic Ex 4 portas D16A6 auto???)
- PK2 ([JDM](/cars/sensors/jdm) Honda Prelude Motor B20A com avanço eletrónico)
- PH3 ([JDM](/cars/sensors/jdm) 86-89 Honda Accord B20A)

Fazer o [chipping de uma ECU de 88-89](/cars/honda/civic/ef/ecu/chipping-an88-89ecu) não é tão fácil como nos computadores de 90-91, porque apenas os computadores mais recentes possuem [ROM](/cars/tuning/rom)s externas substituíveis. Compreender a [comunicação entre chips OBD0](/cars/ecu/obd0-inter-chip-communication) será fundamental para descobrir exatamente como funcionam as [ECU](/cars/ecu/ecu)s. Anexa abaixo está uma biblioteca Eagle (4.09) que contém os dispositivos [MCU](/cars/ecu/mcu) (OKI 8xC154), [RAM](/cars/reference/ram) (`M5128`), [ADC](/cars/wiring/adc) (µPD7004) e CI contador de controlo do motor ([Oki6260 A](/cars/ecu/oki6260a)) para utilizar estes componentes no editor de layout Eagle.

| **Anexo:** | **Modificar:** | **Tamanho:** | **Data:** | **Quem:** | **Comentário:** |
| :--- | :--- | :--- | :--- | :--- | :--- |
| ![](/pgmfi/wiki/assets/icn/else.gif) [pm6.lbr](pm6.lbr) | mod | 11725 | 05 Dec 2004 - 20:57 | l3st4rd | biblioteca eagle 4.09 para alguns componentes de [ECU](/cars/ecu/ecu) [OBD](/cars/wiring/obd)0 |

*Library. OBD0MPFI movido de Library. OBD0CivicIntegra em 20 Fev 2004 - 00:37 por Home.blundar

* - [coloque de volta](https://web.archive.org/web/http://www.pgmfi.org/twiki/bin/rename/Library/OBD0MPFI?newweb=Library&newtopic=OBD0CivicIntegra&confirm=on "Clique para mover o tópico de volta para a localização anterior, com a opção de alterar referências.") | | :--- |
