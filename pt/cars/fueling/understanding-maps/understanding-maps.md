---
summary: 'Um guia introdutório que explica como as tabelas de combustível e de ignição (mapas) são estruturadas e interpretadas nas ROMs das ECUs Honda.'
tags: [tuning, rom, combustível, ignição]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Compreender os Mapas'
    url: /pgmfi/wiki/library/understanding-maps
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Compreender os Mapas de Combustível e Ignição da ECU

As Unidades de Controlo do Motor (ECU) da Honda utilizam tabelas de consulta – comummente referidas como mapas – para controlar a duração da injeção de combustível e o avanço do ponto de ignição. Este guia explica como as tabelas de combustível e de ignição estão estruturadas, como a ECU alterna entre os modos de funcionamento e como interpola os valores entre as células para garantir um funcionamento suave do motor.

## Mapas de Combustível

Na maioria das condições de condução (normalmente abaixo de 80% de abertura de acelerador), a ECU funciona em **modo closed-loop** (malha fechada). Neste modo, a ECU utiliza o feedback da [sonda de oxigénio / sonda lambda](/cars/fueling/oxygen-sensor) para ajustar constantemente a relação ar-combustível a um valor estequiométrico alvo (normalmente 14,7:1).

Assim que a posição do acelerador excede o limite de closed-loop, a ECU muda para o **modo open-loop** (malha aberta). No modo open-loop, a ECU confia inteiramente em tabelas de consulta pré-programadas (mapas) para determinar o tempo de abertura dos injetores (pulse-width):

![Interface do editor do mapa de combustível da ECU OBD0 mostrando colunas de carga e linhas de RPM](pw0fuel.gif)

### Estrutura do Mapa

- **Colunas (Carga/Vácuo):** As colunas correspondem à pressão no coletor de admissão (vácuo/sobrealimentação) medida pelo sensor de pressão absoluta do coletor (MAP). As colunas mais à esquerda representam vácuo elevado (desaceleração ou ralenti), enquanto as colunas mais à direita representam borboleta totalmente aberta (WOT - Wide-Open Throttle).
 - As ECUs OBD0 normalmente utilizam 15 colunas, medidas em polegadas de mercúrio (inHg).
 - As ECUs OBD1 utilizam 10 colunas, medidas em milibares (mBar).
- **Linhas (Rotação do Motor):** As linhas representam a velocidade do motor em rotações por minuto (RPM).
- **Células (Tempo de Injeção / Pulse-width):** Os valores dentro das células representam a duração base de injeção, normalmente calculada em milissegundos. O editor de tuning da ECU traduz os valores hexadecimais brutos de 8 bits em tempos de abertura legíveis utilizando uma fórmula multiplicadora específica (por exemplo, [OBD0 Fuel](/cars/sensors/obd0-fuel) ou [OBD1 8-bit Fuel](/cars/fueling/obd1-8bit-fuel)).

## Mapas de Ignição

Tal como a entrega de combustível, o ponto de ignição é determinado através de tabelas de consulta:

![Interface do editor do mapa de ignição da ECU OBD0 mostrando o avanço de ignição em graus](pw0ignition.gif)

- **Colunas e Linhas:** A estrutura da tabela espelha a dos mapas de combustível, mapeando a velocidade do motor (RPM) contra a pressão do coletor de admissão.
- **Células (Avanço de Ignição):** Os valores das células representam os graus de avanço de ignição antes do ponto morto superior (BTDC - Before Top Dead Center).

## Interpolação de Mapas

Como a velocidade do motor e a carga são variáveis contínuas, a ECU raramente funciona exatamente nas coordenadas de uma única célula. Para manter o funcionamento suave do motor, a ECU realiza uma **interpolação bilinear** para calcular o valor preciso de combustível ou ignição entre as quatro células circundantes.

A ECU calcula a média ponderada das células circundantes utilizando tanto a leitura atual do sensor MAP como as RPM do motor.

### Exemplo de Interpolação Passo a Passo

Considere um motor a funcionar a **5775 RPM** e **20 inHg** de vácuo no coletor.

Olhando para o mapa acima, o estado atual situa-se entre:
- **Colunas 3 e 4** (21 inHg e 19 inHg)
- **Linhas 7 e 8** (5500 RPM e 6050 RPM)

As quatro células circundantes fornecem os seguintes valores:

* **Superior-Esquerda (3,7):** 21 inHg, 5500 RPM $\rightarrow$ **2,16 ms**
* **Superior-Direita (4,7):** 19 inHg, 5500 RPM $\rightarrow$ **2,56 ms**
* **Inferior-Esquerda (3,8):** 21 inHg, 6050 RPM $\rightarrow$ **2,25 ms**
* **Inferior-Direita (4,8):** 19 inHg, 6050 RPM $\rightarrow$ **2,62 ms**

#### Passo 1: Interpolar ao Longo das Colunas (Vácuo)

Calculamos a média ponderada entre as colunas de carga na linha de RPM inferior (Linha 7) e na linha de RPM superior (Linha 8).

Para a Linha 7 (5500 RPM) a 20 inHg (a meio caminho entre 21 e 19):
$$V_7 = \frac{21 - 20}{21 - 19} \times 2.16 + \frac{20 - 19}{21 - 19} \times 2.56 = (0.5 \times 2.16) + (0.5 \times 2.56) = 2.36\text{ ms}$$

Para a Linha 8 (6050 RPM) a 20 inHg:
$$V_8 = \frac{21 - 20}{21 - 19} \times 2.25 + \frac{20 - 19}{21 - 19} \times 2.62 = (0.5 \times 2.25) + (0.5 \times 2.62) = 2.435\text{ ms}$$

#### Passo 2: Interpolar ao Longo das Linhas (RPM)

Em seguida, interpolamos entre os dois valores de RPM calculados ($V_7 = 2.36$ e $V_8 = 2.435$) para o nosso valor alvo de 5775 RPM (a meio caminho entre 5500 e 6050 RPM):

$$\text{Valor Final} = \frac{6050 - 5775}{6050 - 5500} \times 2.36 + \frac{5775 - 5500}{6050 - 5500} \times 2.435 = (0.5 \times 2.36) + (0.5 \times 2.435) = 2.3975\text{ ms}$$

A ECU irá comandar um tempo de abertura do injetor (pulse-width) de **2,3975 ms**.
