---
summary: 'Guia técnico dos sensores de entrada utilizados pelas ECUs Honda para gerir os parâmetros de injeção de combustível e ignição.'
tags: [ecu, sensores, diagnóstico, injeção]
complexity: beginner
---

# Sensores de Entrada da ECU Honda

A ECU Honda utiliza uma rede de sensores para monitorizar as condições de funcionamento do motor e ajustar a injeção de combustível e o avanço da ignição em tempo real.

## Sensores Principais

Estes sensores são essenciais para o funcionamento básico do motor e gestão de combustível:

*   **Sensor de Posição da Cambota (CKP):** Determina o ponto para a injeção de combustível e ignição de cada cilindro, além de monitorizar a rotação do motor (RPM).
*   **Sensor do Ponto Morto Superior (TDC):** Determina o ponto de ignição durante o arranque (*cranking*) e atua como referência quando o ângulo da cambota é anormal.
*   **Sensor de Posição do Cilindro (CYP):** Deteta a posição do cilindro #1 para permitir a ignição sequencial.
*   **Sensor de Temperatura do Líquido de Refrigeração (ECT):** Termistor que informa a temperatura do motor à ECU.
*   **Sensor de Temperatura do Ar de Admissão (IAT):** Termistor que mede a temperatura do ar que entra no coletor de admissão.
*   **Sensor de Pressão Absoluta do Coletor (MAP):** Mede a pressão no coletor de admissão, permitindo à ECU calcular a densidade do ar e ajustar a relação ar-combustível.
*   **Sensor de Oxigénio (O2):** Monitoriza o teor de oxigénio nos gases de escape para ajuste de malha fechada (*closed loop*).
*   **Sensor de Pressão Atmosférica (PA/BARO):** Mede a pressão atmosférica ambiente para compensação de altitude.
*   **Sensor de Posição do Acelerador (TPS):** Mede o ângulo de abertura da borboleta de aceleração.
*   **Sensor de Velocidade do Veículo (VSS):** Mede a velocidade de rotação dos semi-eixos.
*   **Válvula de Controlo de Ar de Ralenti (IAC/EACV):** Atuador controlado pela ECU para regular a rotação de ralenti.

## Sensores Opcionais e Específicos

Estes componentes dependem da configuração do motor, mercado ou nível de acabamento do veículo:

*   **Sensor de Detetor de Carga Elétrica (ELD):** Presente na maioria dos modelos do mercado norte-americano para medir a carga do sistema elétrico.
*   **Sensor de Detonação (Knock Sensor):** Dispositivo piezoelétrico que deteta pré-ignição (detonação), comum em motores DOHC VTEC.
*   **Solenoide VTEC:** Atuador eletromagnético que direciona o fluxo de óleo para ativar o perfil de cames de alta performance.

> [!NOTE]
> Motores Honda de série não utilizam sensores de massa de ar (MAF), baseando-se inteiramente na leitura de densidade de velocidade (MAP/IAT/RPM) para o cálculo de carga.

{{> sensor-diagnostics-table }}
