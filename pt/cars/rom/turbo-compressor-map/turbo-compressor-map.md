---
summary: 'Alguns mapas comuns de compressores de turbo. A leitura de mapas de compressores de turbo é bastante simples e útil para escolher o turbo ideal.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - tuning
  - rom
  - sensors
  - reference
sources:
  - name: 'pgmfi.org wiki'
    title: 'Turbo Compressor Map'
    url: /pgmfi/wiki/library/turbo-compressor-map
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Mapa do Compressor do Turbo (Turbo Compressor Map)

Alguns mapas de compressores de turbo comuns encontram-se aqui: [https://www.borgwarner.com](https://www.borgwarner.com)

---

Ler mapas de compressores de turbo é bastante simples, e é algo que qualquer pessoa que esteja a equipar o seu carro com um turbo deveria saber ler. Um mapa de compressor de turbo indica-lhe várias coisas sobre as características de um turbo que o ajudam a adequar o turbo correto à configuração específica do seu motor. Um mapa de compressor de turbo assemelha-se a isto: [T-3 Super 60 ](t3-60.jpg)

1) **Relação de Pressão (Pressure Ratio):** Este número representa a pressão de sobrealimentação (boost) que pretende utilizar, constituindo o eixo Y do gráfico. O valor numérico da relação de pressão é calculado pegando na sua pressão alvo em psi (15 psi, por exemplo), somando depois 1 Atmosfera (14,7 psi) e dividindo o total por 1 bar (14,7 psi). A equação para o nosso exemplo é a seguinte: 15 + 14,7 = 29,7; 29,7 / 14,7 = 2,02. O valor 2,02 é o número de referência que procuraria no eixo Y.

2) **Fluxo de Ar (Airflow):** O eixo X do gráfico representa o fluxo de ar em libras por minuto (lb/min). Como regra geral, `cada` libra de ar gerada representa 10 cv (cavalos de potência). Esta é a potência ao volante do motor (flywheel hp) e não à roda (wheel hp), por isso não confunda as duas. Ao analisar isto, certifique-se de que contabiliza as perdas da transmissão ao estimar a sua potência de saída. DICA: utilize CFM x 0,075 para obter os números em lb/min. O gráfico apresentado está em LB/min, enquanto outros gráficos estão em CFM. Como distingui-los? Os gráficos em CFM têm números no eixo X na ordem das centenas (por exemplo, 400), em oposição às dezenas (por exemplo, 26) dos gráficos em LB/min.

3) **Ilha de Eficiência (Efficiency Island):** A terceira área representa a ilha de eficiência. Esta é a área alvo onde deseja manter a sua pressão de sobrealimentação. É onde o turbo se encontra no pico de eficiência e, por isso, funciona melhor.

4) **Anéis de Eficiência Externos:** Estes são os anéis externos de eficiência ou eficiência da turbina (wheel efficiency). Como pode ver pelos números, `cada` anel diminui em eficiência e, por conseguinte, diminui a potência de saída. A percentagem de eficiência perdida e a perda de potência variam de turbo para turbo, mas, por regra geral, deve manter-se o mais próximo possível da sua ilha de eficiência (ilha central).

5) **Limite de Sobretensão / Bloqueio (Surge Limit):** Esta linha tracejada é o limite de surge. Quaisquer pontos à esquerda desta linha indicam que a turbina compressora em questão é demasiado grande para o boost esperado e para a potência de saída planeada. Não haveria volume de gases de escape suficiente para fazer a turbina rodar rápido o suficiente para gerar uma pressão útil.

6) **Choke Limit / Estrangulamento por Rotação Excessiva:** Esta área à direita do gráfico mapeia o estrangulamento por sobre-rotação (overspin choke). Isto significa que a turbina compressora é demasiado pequena e terá de rodar demasiado depressa para atingir o boost/potência alvo. A estas velocidades extremas, a eficiência é perdida porque a turbina agita o ar de forma tão severa que provavelmente causará uma perda dramática de potência.

7) **Velocidade da Turbina Compressora (Compressor Wheel Speed):** Esta é a velocidade de rotação do veio da turbina compressora em rpm. Mede a velocidade de rotação do veio da turbina do compressor. Quanto mais rápido estiver a rodar, mais quente será a carga de ar na saída e, consequentemente, menor será a potência de saída. É aqui que entra em jogo um bom intercooler.
