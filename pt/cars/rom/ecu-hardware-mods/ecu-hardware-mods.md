---
summary: 'Um índice de modificações de hardware para ECUs Honda OBD0 and OBD1, incluindo conversões para VTEC, adições de IAB, entradas de banda larga (wideband) e conversões de transmissão.'
applies_to:
  obd: [0, 1]
complexity: advanced
tags:
  - ecu
  - hardware
  - chipping
sources:
  - name: 'pgmfi.org wiki'
    title: 'Modificações de Hardware da ECU'
    url: /pgmfi/wiki/library/ecu-hardware-mods
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Guia de Modificações de Hardware de ECUs Honda

As unidades de controlo do motor (ECUs) originais da Honda são altamente modulares. A Honda utilizava frequentemente os mesmos layouts de placa de circuito impresso (PCB) para múltiplos modelos de ECU, deixando certos caminhos de componentes sem componentes soldados nos modelos de gama inferior. Esta modularidade permite que os entusiastas soldem fisicamente componentes para adicionar funcionalidades como controlo de VTEC, coletores de admissão secundários (IAB) e entradas personalizadas de datalogging.

Abaixo está um índice de modificações de hardware comuns para ECUs Honda OBD0 e OBD1.

---

## 1. Modificações de Transmissão e Chassis

### Conversão de Automático para Manual (OBD0 e OBD1)

Converta uma ECU de transmissão automática para funcionar num veículo manual sem acender a luz de verificação do motor (CEL) com o Código 19 (solenoide de controlo de bloqueio/lockup). Esta modificação envolve tipicamente dessoldar os jumpers de configuração e substituí-los por resistências de 0 ohms (ou fios de ligação/jumpers) para informar o software da ECU de que uma transmissão manual está presente.

---

## 2. Modificações de ECUs OBD1 (P28, P30, P72, P75, P05, P06)

### Conversão para VTEC (Não-VTEC para VTEC)

Converta ECUs não-VTEC económicas (como a P06 de Civic DX ou P75 de Integra LS) em unidades compatíveis com VTEC. Esta modificação requer a soldadura de um transistor driver de lado alto (high-side), um transistor de travamento (latching), resistências, díodos e condensadores de filtragem na secção de controlo de VTEC não povoada da placa.

### Controlo dos Canais de Admissão Secundários (Adição de IAB)

Adicione controlos de bypass de ar de admissão (IAB) a uma ECU P28. As ECUs P28 padrão não suportam o solenoide do coletor de admissão de duplo estágio encontrado nos coletores de admissão do B18C1 (Integra GS-R) e H22A (Prelude VTEC).
* **A Modificação:** Solde o IC driver do IAB (tipicamente em `IC15`) e as resistências de suporte para ativar o controlo dos canais secundários. Consulte o guia [Adicionar IAB à P28](/cars/sensors/add-iab-to-p28) para mais detalhes.

### Instalação da Placa de Detonação

Modifique uma ECU P75 ou P28 para aceitar um sensor de detonação, instalando a subplaca de processamento de detonação OEM e soldando os pinos das pistas de entrada. Consulte o [guia de instalação da Placa de Detonação](/cars/wiring/add-a-knock-sensor).

### Remoção da Placa de Detonação

Remova ou ignore a subplaca de processamento de detonação em ECUs como a P13 (Prelude) ou JDM P30/P72 para evitar a desativação do VTEC ou erros ativos do Código 23 ao utilizar motores que não possuem sensor de detonação ou que têm comandos de válvulas ruidosos.

### Conversão para Sensor de Oxigénio de 4 Fios

Converta circuitos de sensor de O2 de um único fio (encontrados em ECUs JDM P08 e USDM P05 de base) para circuitos padrão de sensor de O2 aquecido de 4 fios para melhorar a estabilidade em malha fechada (closed-loop).

### Modificação de Entrada de Banda Larga (Wideband) 0–5V

Modifique a rede de resistências de entrada do sensor de oxigénio de fábrica para aceitar um sinal analógico linear de 0–5V diretamente de um controlador de banda larga externo (como um AEM UEGO ou Innovate MTX-L).

### Registo de Sensores Externos (EGT / Pressão de Combustível)

Reutilize pinos de entrada analógica não usados na ficha da ECU (como o pino do sensor de elevação da válvula EGR ou o pino de controlo do EVAP) para registar dados de sensores externos de 5V, tais como sondas de temperatura dos gases de escape (EGT) ou sensores de pressão de combustível. Consulte o guia [Como Registar Dados Externos](/cars/tuning/how-to-log-external-data-such-as-an-egt-sensor).

---

## 3. Modificações de ECUs OBD0 (PM6, PM7, PR4, PG7)

### Conversão para VTEC (VTEC de 1 Fio)

Adicione hardware de controlo de ativação de VTEC de 1 fio a ECUs OBD0 (como a PM6) para utilizar motores VTEC como o D16Z6 ou B16A com cablagens OBD0.

### Bypass do Detetor de Carga Elétrica (ELD)

Desative o circuito de feedback do ELD em ECUs USDM PM6. Este bypass impede que a ECU acenda a luz de erro (CEL) com o Código 20 quando instalada em chassis do mercado canadiano ou em veículos com swap que não possuem uma unidade ELD na caixa de fusíveis do compartimento do motor.

### Conversão do Sensor de Pressão Barométrica (PA)

Reconfigure as ECUs de Integra PR4 de 1990–1991 para usar um sensor Barométrico/PA interno ou externo, ajustando as resistências das pistas do jumper.

---

## 4. Aquisição de Hardware

Para encontrar números de peça específicos, tamanhos de encapsulamento e especificações eletrónicas para as resistências, transístores e díodos necessários para executar estas modificações, consulte a [Lista de Aquisição de Peças de ECU](/cars/ecu/parts-for-ec-us).
