---
summary: 'O Sensor de Velocidade do Veículo (VSS) envia impulsos de velocidade para o painel de instrumentos e para a ECU. Diagnóstico de falhas no velocímetro e problemas de ativação do VTEC relacionados com o VSS.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - sensor
  - diagnósticos
  - cablagem
sources:
  - name: 'pgmfi.org wiki'
    title: 'Vehicle Speed Sensor'
    url: /pgmfi/wiki/library/vehicle-speed-sensor
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Sensor de Velocidade do Veículo (VSS)

O Sensor de Velocidade do Veículo (VSS) mede a velocidade de rotação do eixo e envia estes dados sob a forma de impulsos elétricos para a ECU e para o painel de instrumentos.

## Visão Geral

Na maioria dos veículos Honda, o VSS gera quatro impulsos de massa por cada rotação do eixo.
*   **OBD0 (Acionado por Cabo):** O velocímetro é acionado por um cabo físico ligado diretamente à transmissão. O próprio VSS é um módulo eletrónico de interruptor de lâminas (reed switch) integrado na parte traseira do painel de instrumentos.
*   **OBD1 / OBD2 (Eletrónico):** O VSS é um sensor eletrónico montado diretamente na carcaça da transmissão (acima do diferencial). Envia sinais eletrónicos diretamente para o painel de instrumentos e para a ECU.

### Funções da ECU
A ECU utiliza o sinal do VSS para várias operações fundamentais:
1.  **Ativação do VTEC:** A ECU não ativa o VTEC a menos que o veículo se desloque acima de um limite de velocidade definido (normalmente 15 mph / 24 km/h).
2.  **Limitador de Velocidade:** Restringe a velocidade máxima do carro (comumente encontrado em ECUs JDM a 180 km/h / 112 mph).
3.  **Correções de Combustível Dependentes da Mudança:** Ajuda a calcular as correções de carga do motor adequadas dependendo da mudança engrenada.
4.  **Cruise Control e Controlo do Ralenti:** Controla o ralenti estável ao desacelerar até parar e mantém as velocidades do cruise control.
5.  **Launch Control / 2-Step:** As ROMs de ECU personalizadas (com chip) utilizam a entrada do VSS para desativar o launch control assim que o veículo começa a mover-se.

## Referência de Cablagem

### Pinagem do VSS OBD1

| Pino | Cor do Fio | Função | Ponto de Ligação |
| :--- | :--- | :--- | :--- |
| **Pino 1** | Amarelo/Preto | Alimentação | +12V Pós-Chave (Fusível 15) |
| **Pino 2** | Preto | Massa | Massa do Chassis (G101 na carcaça do termóstato) |
| **Pino 3** | Laranja (ou Azul/Branco) | Sinal | Envia sinais pulsados para o pino **B10** da ECU e para o painel do velocímetro |

## Resolução de Problemas

### Sintomas de Avaria do VSS
*   A agulha do velocímetro cai para zero, oscila de forma errática ou não se move.
*   A Luz de Aviso do Motor (CEL) acende com o **Código 17** (avaria no VSS).
*   O VTEC recusa-se a ativar (porque a ECU pensa que o carro está parado).
*   Velocidade de ralenti errática ao desacelerar até parar.

### Diagnosticar Problemas no VSS
Se estiver a obter o Código 17 ou se o velocímetro estiver inativo:
1.  **Verifique a Alimentação e a Massa:** Inspecione o conector de 3 pinos na transmissão. Certifique-se de que tem alimentação de 12V no fio Amarelo/Preto com a chave ligada e boa continuidade à massa no fio Preto.
2.  **Inspecione o Veio de Transmissão do VSS:** Remova o VSS da transmissão. Entre o sensor e a transmissão existe um pequeno pino metálico de arrastamento (drive link). Se este pino partir ou cair, o sensor não rodará, fazendo com que envie 0 impulsos.
3.  **Teste de Frequência:** Utilizando um multímetro digital com contador de frequência ou um osciloscópio, meça o fio de sinal Laranja. Eleve as rodas dianteiras do chão, rode-as manualmente e verifique se o sinal pulsa entre 0V e 5V.

### Contornar Limitadores de Velocidade JDM
As ECUs JDM cortam o combustível quando detetam uma velocidade do veículo de 180 km/h (~112 mph).
*   **O Método de Modificação por Chip (Recomendado):** A forma mais limpa de remover o limitador de velocidade é desativá-lo no software da ROM da ECU utilizando um editor de BIN (como o Crome).
*   **O Método do Limitador de Frequência (Hardware):** Se estiver a utilizar uma ECU que não permite a gravação de chips, pode instalar um circuito limitador de frequência entre o VSS e a ECU. Ao registar a frequência a 100 mph (seguramente abaixo do limite), pode construir um circuito que impeça que a frequência de impulsos enviada para a ECU ultrapasse o limite de 100 mph, contornando o limitador e mantendo o VTEC e o cruise control funcionais.

## Relacionado

*   [Solenóide do VTEC](/cars/wiring/vtec-solenoid)
*   [Códigos de Erro da ECU](/cars/diagnostics/ecu-trouble-codes)
*   [Resolução de Problemas da ECU](/cars/diagnostics/ecu-troubleshooting)
