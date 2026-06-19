---
summary: 'Layouts de hardware, localizações de componentes e instruções de chipping para a ECU OBD1 Acura Integra PR4.'
tags: [ecu, reference]
applies_to:
  brand: Acura
  ecus: [PR4]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: OBD1PR4
    url: /pgmfi/wiki/library/obd1pr4
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Hardware e Referência da ECU OBD1 PR4

A ECU **PR4** é a unidade de controlo do motor OBD1 padrão usada nos modelos Acura Integra RS, LS e GS de 1992–1993 equipados com o motor 1.8L B18A1 sem VTEC. 

> [!NOTE]
> A Acura também utilizou uma ECU PR4 nos modelos Integra de 1990–1991. No entanto, esses modelos iniciais são OBD0. Se estiveres a modificar uma unidade de 1990–1991, consulta a documentação da [OBD0 PR4](/cars/ecu/obd0pr4).

## Layout da Placa e Chipping

A PR4 OBD1 partilha um layout de hardware muito semelhante ao de outras ECUs Honda/Acura OBD1 da sua época (como a [P28](/cars/sensors/p28) ou a [P75](/cars/sensors/p75)). Como resultado, pode ser modificada (chipped) usando kits de chipping OBD1 padrão para aceitar ROMs personalizadas (como Crome, UberData ou Neptune).

Para fazer o chipping de uma ECU PR4 OBD1, devem ser preenchidas as seguintes localizações de componentes:

* **Socket de 28 pinos (`IC3`):** Para o chip EPROM/EEPROM personalizado.

* **Trinco (Latch) `74HC373` (`IC4`):** Para desmultiplexagem de endereços.

* **Resistência `R54` (1k ohm):** Para ativar o endereçamento de memória externa (ou um fio de ponte [jumper], dependendo da revisão da placa).

* **Condensadores `C1` e `C2` (0.1 uF):** Para filtragem de ruído nas linhas do trinco (latch) e da ROM.

Abaixo estão imagens (scans) do hardware da placa PR4 OBD1 para referência:

### 1. Vista Superior da Placa

O layout principal da PR4 OBD1 mostrando as pegadas (footprints) dos componentes padrão:

![Vista superior da placa de circuito da ECU OBD1 PR4 mostrando os layouts dos componentes](PR4OBD1top.jpg)

### 2. Montagem Geral da Placa

Uma visão geral mais ampla da montagem da placa PR4 OBD1:

![Vista completa da placa de montagem da ECU OBD1 PR4](122505058Large.jpg)

### 3. Primeiro Plano da Secção Modificada (Chipped)

Vista detalhada da área modificada com um socket ZIF/IC de 28 pinos e o trinco (latch) `74HC373` instalado:

![Primeiro plano da secção de componentes modificada na placa PR4](122505053Large.jpg)

### 4. Layout Traseiro da Placa

O lado inferior da PCB mostrando os pontos de soldadura de fábrica e modificação:

![Lado traseiro da placa PR4 mostrando os pinos soldados](122505057Large.jpg)

### 5. Verificação da Montagem de Fábrica

Primeiro plano da pegada de uma placa OBD1 de fábrica antes da modificação ou mostrando a configuração de ponte (jumper)/resistência de fábrica:

![Primeiro plano do layout da placa modificada de fábrica](122505063Large.jpg)
