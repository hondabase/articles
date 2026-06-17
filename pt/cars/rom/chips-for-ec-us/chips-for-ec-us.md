---
summary: 'Guia de seleção para chips de memória utilizados no chipping de ECUs Honda OBD0 e OBD1, abordando limitações de velocidade, compatibilidade e variações de pinout.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - ecu
  - chipping
  - hardware
sources:
  - name: 'pgmfi.org wiki'
    title: 'Chips For EC Us'
    url: /pgmfi/wiki/library/chips-for-ec-us
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Onde Obter Chips de Memória para ECUs Honda

A instalação de um suporte (socketing) ou chipping numa ECU Honda OBD0 ou OBD1 de 1990–1995 requer a instalação de um chip de memória paralela de 32 KB (256-kilobit). Embora vários tipos de chips se ajustem à pegada física do suporte DIP-28, estes têm diferentes velocidades de acesso, procedimentos de apagamento e pinouts.

---

## 1. Tecnologias de Chip Suportadas

Os preparadores (tuners) escolhem habitualmente entre três tecnologias de chip distintas:

* **SST 27SF256 (Memória Flash - Recomendado):** Este é o padrão da indústria para afinação (tuning) de Hondas. É eletricamente apagável e regravável, o que significa que pode ser programado repetidamente em segundos utilizando um programador USB padrão.

* **27C256 (EPROM):** ROM Programável Apagável (Erasable Programmable ROM). As versões sem janela são programáveis uma única vez (OTP). As versões com janela podem ser apagadas utilizando luz ultravioleta (UV), o que demora 15–20 minutos numa caixa de apagamento UV.

* **AT29C256 (EEPROM):** PROM Eletricamente Apagável (Electrically Erasable PROM). Compatível com suportes padrão e facilmente regravável, mas menos comum que os chips flash SST.

---

## 2. Especificações de Velocidade (Tempo de Acesso)

Os microcontroladores das ECUs requerem uma recuperação de dados extremamente rápida para coordenar os impulsos dos injetores de combustível e os eventos de ignição. 

* **A Especificação:** As especificações da Honda exigem chips de memória com uma classificação de **170 nanossegundos (ns) ou mais rápidos**. 
* **Recomendação:** Embora alguns chips marcados com 200ns funcionem porque excedem as suas velocidades nominais na prática, é altamente recomendado obter chips classificados a **150ns, 120ns, 90ns ou 70ns** para garantir a estabilidade sob calor elevado e altas RPM.

### Sufixos de Velocidade de Acesso:

* `-20` = 200ns (arriscado; usar apenas se verificado)
* `-17` = 170ns (especificação mínima de fábrica)

* `-15` = 150ns
* `-12` = 120ns

* `-9` ou `-90` = 90ns
* `-7` ou `-70` = 70ns

### Exemplo Histórico

Os primeiros lotes de produção da ECU OBD0 Acura Integra PR4 (com data de junho de 1989) saíram de fábrica com um chip com janela `27C256-17` (170ns) num suporte de fábrica. Como as mask ROMs de produção em massa não estavam prontas a tempo, a Honda utilizou estes chips reprogramáveis para cumprir os prazos iniciais de entrega dos veículos.

![EPROM 27C256-17 de fábrica com janela numa ECU PR4 OBD0 antiga](chipmarkings.jpg)
*EPROM com janela em suporte de fábrica de uma ECU Acura Integra PR4 de 1989.*

---

## 3. Avisos de Incompatibilidade

### O EEPROM `28C256`

Não confunda o `27SF256` ou `29C256` recomendado com o EEPROM padrão **`28C256`**. Embora o `28C256` partilhe a mesma capacidade de 32 KB e o mesmo invólucro DIP de 28 pinos, este utiliza uma configuração de pinos diferente (especificamente nos pinos de controlo de escrita). Se for inserido num suporte padrão `27C256`, o `28C256` não comunicará com a ECU e acenderá a CEL de forma fixa. Requer modificação das pistas do circuito para funcionar.
