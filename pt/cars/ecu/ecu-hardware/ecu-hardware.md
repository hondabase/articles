---
summary: 'Por dentro de uma ECU Honda: as placas, chips e circuitos.'
tags: [ecu, hardware]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'ECU Hardware'
    url: /pgmfi/wiki/library/ecu-hardware
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Hardware da ECU

Esta página descreve como funciona o hardware numa [ECU](/cars/ecu/ecu) e coisas divertidas que pode fazer com ele. Se quer apenas aprender a chipar a sua [ECU](/cars/ecu/ecu), deve consultar "What You Need". Se procura informações detalhadas sobre o que se passa dentro de um programa específico, pode consultar "Rom Maps". A Honda decididamente não reinventou a roda no que toca à tecnologia de [ECU](/cars/ecu/ecu) para cada novo motor que lançou. Cada "família" de [ECU](/cars/ecu/ecu) geralmente partilha uma ou mais placas de circuito impresso (PCBs) que são povoadas com diferentes componentes para controlar motores diferentes. Isto abre realmente portas para Modificações de Hardware da ECU. Adicionalmente, existem peculiaridades de design que transitam de uma família para outra. Famílias de [ECU](/cars/ecu/ecu):

- [ECU](/cars/ecu/ecu)s OBD0 com Avanço por Vácuo de carros anteriores a 1988 que não possuem distribuidores de avanço eletrónico partilham algumas características comuns.
- [ECU](/cars/ecu/ecu)s OBD0 DPFI de carros de 88-91 são complicadas e faltam-lhes 2 injetores para serem úteis.
- [ECU](/cars/ecu/ecu)s OBD0 MPFI não-VTEC de 88-91 são uma família definida.
- ECUs OBD0 VTEC, como a PW0 e a PR3, são uma família definida.
- ECUs OBD1 Civic Integra são uma família definida.
- [ECU](/cars/ecu/ecu)s OBD1 Prelude Accord são uma família definida.
- ECUs V6 dos carros Acura/Rover/Honda Legend V6, NSX e (?) Accord V6 têm muitas características comuns.
- [ECU](/cars/ecu/ecu)s OBD2 A são bastante semelhantes.
- [ECU](/cars/ecu/ecu)s OBD2 B são bastante semelhantes.
- [ECU](/cars/ecu/ecu)s OBD2 K são uma evolução das [ECU](/cars/ecu/ecu)s OBD2B concebidas para controlar motores da série K.

Se quiser aprender sobre como funciona o MCU Oki 66K, deve consultar "66k Assembler Docs". Existem muitas Modificações de Hardware de ECU que pode fazer para alterar a forma como o hardware da [ECU](/cars/ecu/ecu) funciona. A Honda utilizava frequentemente MCUs com programas internos (on-chip). Estes eram frequentemente protegidos contra cópia. Existem Leitores de MCU para contornar esta proteção contra cópia. Já se perguntou quem desenhou as [ECU](/cars/ecu/ecu)s da Honda? A Keihin Indiana Precision Technology é a culpada... É possível alternar entre mais do que um programa na sua EEPROM sobredimensionada. Tudo o que precisa de fazer é adicionar uma resistência de pull-up às linhas de endereço extra (A15, A16, etc.) e, para alternar entre eles, basta adicionar um interruptor com circuito anti-ressalto (debounced switch) para ligar essas linhas de endereço à massa (ground). **Aqui está um diagrama de EEPROMs de 28 e 32 pinos:**
- Pinagem de EEPROM: 
 ![1.32_pin-2-28PinIC.jpg](1.32_pin-2-28PinIC.jpg)

 **Anexo:** **Modificar:** **Tamanho:** **Data:** **Quem:** **Comentário:** ![](/pgmfi/wiki/assets/icn/bmp.gif) [1.32\_pin-2-28PinIC.jpg](1.32_pin-2-28PinIC.jpg) mod 39713 06 Feb 2007 - 01:39 Jared Karagen Pinagem de EEPROM
