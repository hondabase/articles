---
summary: 'Um guia de construção detalhado para um Simulador de Motor (ECU Stimulator) caseiro (DIY) utilizado para testar em bancada e diagnosticar ECUs Honda OBD0, OBD1 e OBD2.'
applies_to:
  obd: [0, 1, 2]
complexity: advanced
tags:
  - bench-testing
  - hardware
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: Sim
    url: /pgmfi/wiki/library/sim
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Simulador de Motor Caseiro (DIY) para Testes de ECU em Bancada

Um **Simulador de Motor** (frequentemente referido como estimulador de ECU ou bancada de testes) é uma peça inestimável de equipamento de teste para programadores de hardware e preparadores (tuners). Simula as cargas elétricas e os sinais dos sensores de um veículo em funcionamento, permitindo-lhe correr uma ECU numa bancada de trabalho para testar firmware personalizado, diagnosticar falhas de hardware ao nível dos componentes ou verificar modificações de circuitos sem correr o risco de danificar um veículo.

Este guia detalha o design de um simulador de motor completo para montagem em rack (rackmount) construído pelo membro da comunidade *b16a2*. Utiliza uma combinação de componentes automóveis reais, resistências de potência para simulação de carga e geradores de sinal variáveis para simular uma cablagem de motor Honda OBD1 PGM-FI completa.

![Vista Frontal do Simulador de Motor DIY](Engine_Sim016.jpg)
*Simulador de motor caseiro (DIY) concluído e alojado num chassis de computador para montagem em rack.*

---

## Subsistemas do Simulador e Componentes de Carga

Para evitar que a ECU ative códigos de erro, o simulador deve imitar de perto os comportamentos elétricos e as cargas de solenoides, aquecedores e injetores reais.

### 1. Simulação de Atuadores e Cargas

* **Injetores**: Os injetores de combustível reais têm baixa resistência e consomem uma corrente significativa. O simulador utiliza quatro **resistências de potência de 12&Omega; 5W** para simular as bobinas dos injetores, evitando o Código 16 (Sistema de Injetores de Combustível).

* **EACV / IACV**: Uma válvula de controlo de ar do ralenti (EACV/IACV) real está ligada ao sistema para aplicar carga ao circuito de controlo de ralenti da ECU.
* **Solenoide VTEC (VTS)**: Um solenoide VTEC real está montado no chassis. Ouvir o "clique" físico do solenoide fornece uma confirmação imediata de que a ECU ativou o VTEC com sucesso.
* **Pressostato de VTEC (VTP)**: Simulado utilizando uma bobina de relé padrão acionada diretamente pelo sinal de saída do VTS, fechando o interruptor à massa (terra) quando o VTEC é ativado.
* **Aquecedor do Sensor de Oxigénio (Sonda Lambda)**: A ECU verifica o consumo de corrente na linha do aquecedor da sonda de O2. Isto é simulado utilizando três **resistências de 3.7k&Omega; 5W** ligadas em paralelo para dissipar o calor de forma segura.

* **Bomba de Combustível**: Um LED bicolor em série está ligado à saída do relé da bomba de combustível, mudando de cor para mostrar quando a bomba está ativada (primed) e a funcionar.
* **Relé Principal (Main Relay)**: Um relé principal Honda padrão de 7 pinos está integrado para distribuir energia para a placa e para a ECU exatamente como numa cablagem de fábrica.

### 2. Simulação de Sinais dos Sensores

* **Sensores Analógicos (TPS, MAP, ECT, IAT, EGR)**: Simulados usando potenciómetros rotativos variáveis de alta qualidade. Pode rodar os botões para variar a tensão entre `0V` e `5V`.
* **Detetor de Carga Elétrica (ELD)**: Uma unidade ELD real extraída de uma caixa de fusíveis de um Integra Type R JDM está ligada em série com as linhas principais de distribuição de energia de +5V/12V. Isto permite que a ECU (incluindo os modelos P13 ou P72) leia flutuações de carga de corrente em tempo real.
* **Sensor de Detonação (Knock Sensor)**: Um sensor de detonação real está montado no chassis metálico do simulador. Bater no chassis com uma chave de fendas gera uma vibração mecânica, permitindo-lhe testar as rotinas de deteção da placa de detonação.

---

## Simulação do Distribuidor e da Rotação do Motor

Simular a rotação do motor (RPM) requer gerar sinais de pulso sincronizados para os sensores **CKP** (Posição da Cambota), **TDC** (Ponto Morto Superior) e **CYP** (Posição do Cilindro). 

Em vez de utilizar geradores de sinal digitais complexos, este simulador utiliza um distribuidor físico OBD1 acionado por um motor elétrico:

![Detalhe do Simulador de Distribuidor](Engine_Sim019.jpg)
*Conjunto do distribuidor e motor montado num gabarito de alinhamento personalizado.*

### Detalhes de Montagem

* **Motor de Acionamento**: Um motor de 12V recuperado de um berbequim sem fios aciona o veio do distribuidor.
* **Controlo de Velocidade**: O gatilho do berbequim sem fios está ligado a um potenciómetro rotativo grande, permitindo-lhe variar a velocidade do motor para simular rotações do motor de 500 RPM a mais de 9.000 RPM.
* **Acoplamento**: A chaveta de acionamento da árvore de cames do distribuidor foi removida e substituída por uma engrenagem de carro telecomandado de 15 dentes (Tamiya), acoplada ao veio do motor através de uma mangueira de combustível de borracha reforçada. Isto proporciona um acoplamento flexível que absorve vibrações.
* **Bobina de Ignição e ICM**: O Módulo de Controlo de Ignição (ICM) e a bobina de ignição estão ligados no interior do distribuidor. Para evitar o Código 15 (Sinal de Saída de Ignição), a alimentação de 12V é fornecida ao cabo preto/amarelo do relé principal, e o corpo do distribuidor é ligado à massa.

> [!TIP]
> Os distribuidores físicos fornecem um excelente feedback mecânico, mas podem ir abaixo a rotações muito baixas (menos de 500 RPM) se o motor não tiver binário suficiente, simulando um motor a ir abaixo.

---

## Painel de Controlo do Utilizador

O painel de interface do utilizador permite ao operador manipular os sinais dos sensores e injetar falhas intencionalmente no sistema.

![Painel de Controlo do Simulador](Engine_Sim001.jpg)
*Layout do painel de controlo mostrando os manípulos dos sensores e interruptores de injeção de falhas.*

### Características do Painel de Controlo

* **Manípulos de Ajuste de Sensores**: Controlos rotativos para ECT, IAT, RPM, VSS, TPS, MAP e EGR. 
* **Interruptores de Falhas (Linhas Superiores)**: Interruptores SPST ligados em série com cada linha crítica de sensores. Mudar a posição de um interruptor corta o sinal, ativando instantaneamente o correspondente Código de Diagnóstico de Avaria (DTC) na ECU para verificar os diagnósticos.
* **LEDs Indicadores**: LEDs bicolores exibem o estado do circuito. Por exemplo, o LED do interruptor de A/C muda de cor quando a ECU ordena a ativação do relé da embraiagem do ar condicionado.
* **Interruptores de Ignição (Linha Inferior)**: Emulam as posições padrão da chave do veículo (Acessórios, Ignição, Arranque). Ligar o interruptor de Arranque (Start) aciona automaticamente o motor do distribuidor.

---

## Interface da ECU e Cablagem

Para tornar o simulador universal, o chassis apresenta um esquema de conectores de interface modular no painel lateral:

![Ligações da Interface da ECU](Engine_Sim018.jpg)
*Conectores de cablagem DB25 na lateral do chassis.*

* **Conectores DB25**: A lateral do chassis possui três portas de computador DB25 sub-D, mapeadas diretamente para as fichas A, B e D da ECU OBD1.
* **Cablagens Intercambiáveis**: Cablagens adaptadoras personalizadas (DB25 para fichas OBD0, OBD1, OBD2a ou OBD2b) permitem ligar qualquer geração de ECU Honda ao simulador em segundos.

---

## Detalhes dos Componentes e Subconjuntos

````carousel
![Layout da Cablagem Interna do Chassis](Engine_Sim009.jpg)
<!-- slide -->
![Detalhe dos Circuitos de Simulação de O2 e VSS](Engine_Sim020.jpg)
<!-- slide -->
![Integração do Sensor ELD](Engine_Sim022.jpg)
<!-- slide -->
![Vista Traseira da Cablagem do Painel de Controlo](Engine_Sim023.jpg)
<!-- slide -->
![Relé Principal, Sensor de Detonação e Resistências de Aquecimento de O2](Engine_Sim024.jpg)
<!-- slide -->
![Relé VTS e Conjunto de Carga do Solenoide EACV](Engine_Sim025.jpg)
````

---

## Esquemas Elétricos

O simulador é cablado de acordo com os esquemas de pinagem PGM-FI padrão dos Civic/Integra OBD1:

![Esquema de Pinagem da ECU OBD1 PGM-FI - Parte 1](gsrwiring1.gif)
*Esquema de Pinagem da ECU OBD1 PGM-FI - Saídas e Distribuição de Energia.*

![Esquema de Pinagem da ECU OBD1 PGM-FI - Parte 2](gsrwiring2.gif)
*Esquema de Pinagem da ECU OBD1 PGM-FI - Sensores e Entradas do Distribuidor.*
