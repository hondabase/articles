---
summary: 'O Avanço de Ignição define o número de graus de rotação do virabrequim antes do PMS em que a faísca é disparada, sendo fundamental para a eficiência e proteção do motor.'
tags: [tuning, ignition, sensors, reference]
applies_to:
  obd: [0, 1, 2]
complexity: beginner
---

# Avanço de Ignição (Spark Advance)

O Avanço de Ignição refere-se ao número de graus de rotação angular do virabrequim que ocorrem entre o momento em que a faísca é disparada e o instante em que o pistão atinge o [PMS (TDC)](/cars/sensors/tdc).

## Princípios de Funcionamento

A mistura ar-combustível dentro da câmara de combustão requer um tempo finito para inflamar e atingir a pressão de pico. Como a velocidade do motor (RPM) aumenta, o tempo disponível para essa combustão diminui. O sistema de gerenciamento do motor (ECU) ajusta o ponto de ignição para garantir que a pressão máxima de combustão ocorra no momento ideal para extrair o máximo de torque do ciclo de expansão.

> [!IMPORTANT]
> O avanço excessivo pode causar detonação (batida de pino), o que pode resultar em danos catastróficos aos pistões e componentes internos do motor.

## Fatores de Influência

O mapa de ignição da ECU é calculado com base em diversas variáveis de entrada:

*   **RPM do Motor:** O avanço geralmente aumenta com a rotação para compensar o tempo fixo de queima da mistura.
*   **Carga do Motor (MAP/TPS):** Motores sob alta carga (pressão positiva ou aceleração total) exigem menos avanço para evitar a detonação.
*   **Temperatura do Ar de Admissão (IAT):** Temperaturas mais altas aumentam a probabilidade de detonação, exigindo uma redução no avanço.
*   **Temperatura do Líquido de Arrefecimento (ECT):** Motores frios podem exigir ajustes específicos para estabilidade de marcha lenta e aquecimento.

## Verificação e Ajuste

Para garantir que o avanço comandado pela ECU corresponda ao avanço real no motor, é necessário realizar o procedimento de verificação com uma pistola de ponto estroboscópica.

1.  **Modo de Serviço:** Coloque a ECU em modo de ajuste de ponto (geralmente através de um jumper no conector de serviço).
2.  **Alinhamento:** Verifique a marca de referência na polia do virabrequim em relação à marca na tampa da correia dentada.
3.  **Ajuste:** Caso haja divergência, ajuste a posição do distribuidor até que o ponto real coincida com o valor de referência especificado pelo manual de serviço do veículo.

> [!TIP]
> Sempre verifique o manual de serviço específico do seu chassi para obter o valor de avanço base correto, pois ele varia entre diferentes modelos e tipos de motor (ex: série B, D, H ou K).