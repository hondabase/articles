---
summary: 'A válvula solenoide do VTEC ativa os perfis dos cames de alta rotação. Como a ECU aciona o VTEC, os interruptores de pressão e a resolução de problemas de ativação do VTEC.'
tags: [vtec, wiring, hardware]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Solenoide do VTEC'
    url: /pgmfi/wiki/library/vtec-solenoid
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Solenoide do VTEC

A válvula solenoide do VTEC (VTEC spool valve solenoid) é uma válvula hidráulica controlada eletronicamente que ativa o sistema de Controlo Eletrónico de Elevação e Sincronização de Válvulas Variável da Honda (VTEC). Quando acionada pela ECU, a solenoide abre-se, direcionando óleo do motor a alta pressão para os balancins para bloquear os balancins de baixa e alta velocidade juntos, engrenando os perfis das árvores de cames de alta elevação.

![Diagrama mecânico da solenoide do VTEC](vtecsol. GIF)
*Vista de corte mostrando como a solenoide do VTEC direciona a pressão do óleo para bloquear os balancins.*

## Visão Geral

Para que a ECU ative o VTEC (geralmente enviando um sinal de +12V para a solenoide do VTEC), vários parâmetros devem ser cumpridos simultaneamente:
1. **RPM do Motor:** Deve exceder o limite de ativação do VTEC (geralmente entre 4.500 e 6.000 RPM, dependendo do código do motor).
2. **Carga do Motor (MAP):** Deve indicar que o motor está sob carga (não a acelerar em ponto morto).
3. **Velocidade do Veículo (VSS):** Deve estar acima de uma velocidade mínima (normalmente 15 mph / 24 km/h).
4. **Temperatura do Líquido de Refrigeração do Motor (ECT):** Deve estar à temperatura normal de funcionamento (normalmente acima de 60°C / 140°F).
5. **Pressão do Óleo:** Deve ser suficiente para atuar os pinos dos balancins.

### Interruptor de Pressão do VTEC (VTEC Pressure Switch)

Na maioria dos motores OBD0 e OBD1, o conjunto do VTEC inclui um Interruptor de Pressão de Óleo do VTEC (localizado logo abaixo da solenoide). Este interruptor verifica se chegou pressão de óleo suficiente ao conjunto antes de a ECU alterar os seus mapas de combustível e ignição para os perfis de alta rotação (high-cam). Se a pressão do óleo for demasiado baixa, a ECU ativa o Código 22 e interrompe o funcionamento do VTEC para proteger a distribuição (valvetrain).

## Referência de Cablagem

### Esquema de Pinos (Pinout) da Solenoide e Interruptor de Pressão do VTEC OBD1

| Componente | Pino | Terminal da ECU | Descrição |
| :--- | :--- | :--- | :--- |
| **Solenoide do VTEC** | Ficha de 1 pino (Verde) | **A4** | Fio de controlo da solenoide (saída de +12V da ECU para acionar o VTEC) |
| **Interruptor de Pressão do VTEC** | Pino 1 (Azul Claro/Azul) | **D6** | Entrada do interruptor de pressão (enviada para a ECU para verificar a pressão do óleo) |
| **Interruptor de Pressão do VTEC** | Pino 2 (Preto) | Massa do Chassi (Terra) | Retorno de massa para o interruptor de pressão |

## Resolução de Problemas

### O VTEC Não Ativa (Causas Comuns)

1. **Nível de Óleo do Motor Baixo:** Esta é a causa mais comum de falha do VTEC. Se o óleo estiver baixo, a pressão do óleo no coletor cairá sob carga, impedindo o fecho do interruptor de pressão do VTEC.
2. **Filtro da Válvula Solenoide Entupido:** O conjunto da solenoide do VTEC assenta sobre uma junta metálica com uma rede metálica fina integrada. Com o tempo, detritos ou resíduos do motor podem entupir esta rede, restringindo o fluxo de óleo para o interruptor.
 

* *Resolução:* Remova os três parafusos de 10 mm que fixam a solenoide do VTEC, limpe a rede com spray de limpeza de travões ou substitua o conjunto de junta/filtro.
3. **Resolução de Problemas do Interruptor de Pressão do VTEC (Código 22):** Se a sua ECU estiver programada para exigir o interruptor de pressão, mas o seu motor ou cablagem não tiver um (por exemplo, swaps JDM P30 ou JDM B18C), o VTEC não irá ativar e irá despoletar o Código 22.
 

* *Resolução:* Pode desativar a verificação do interruptor de pressão do VTEC no programa da ROM da ECU utilizando um editor de BIN, ou ligar os pinos da ECU com um shunt (jumper).

## Relacionado

* [Sensor de Velocidade do Veículo (VSS)](/cars/wiring/vehicle-speed-sensor)
* [Códigos de Erro da ECU](/cars/diagnostics/diagnostic-trouble-codes)

* [Introdução ao Chipping de ECU](/cars/tuning/introduction-to-ecu-chipping)
