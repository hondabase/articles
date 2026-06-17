---
summary: 'Como funciona o Sensor de Posição do Acelerador (TPS), como calibrar/ajustar e como diagnosticar problemas comuns do TPS.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - sensor
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: 'Sensor TPS'
    url: /pgmfi/wiki/library/tps-sensor
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Sensor de Posição do Acelerador (TPS)

O Sensor de Posição do Acelerador (TPS - Throttle Position Sensor) determina o ângulo da borboleta de aceleração dentro do corpo de borboleta. A ECU utiliza estes dados juntamente com as leituras do sensor MAP, sensor de oxigénio e outros sensores do motor para calcular a carga do motor e as correções de combustível/ignição.

![Honda stock throttle position sensor](honda_stock_tps.jpg)

## Visão Geral

O TPS é um potenciómetro simples (uma resistência variável) que recebe um sinal de referência de 5V da ECU. À medida que a borboleta de aceleração roda, a resistência interna altera-se, devolvendo uma tensão variável à ECU.

*   **Ralenti:** ~0.5V (reportado como 0% de ângulo de aceleração)
*   **Abertura Total (WOT):** ~4.5V (reportado como 100% de ângulo de aceleração)

A literatura técnica da Honda indica que uma tensão de TPS acima de um determinado limiar (frequentemente citado como 4.0V) aciona o funcionamento em malha aberta (open-loop), onde a ECU ignora o feedback do sensor de oxigénio e utiliza tabelas de combustível pré-definidas para potência máxima.

## Procedimento

### Calibração e Ajuste do TPS

Se substituiu o seu corpo de borboleta, instalou um TPS pós-venda (aftermarket), ou está a sentir uma má resposta do acelerador ou soluços ao arrancar, deve calibrar o TPS.

#### Passo 1: Remover os Parafusos Invioláveis
O TPS de fábrica é mantido no lugar por dois parafusos de cisalhamento que parecem rebites. As cabeças destes parafusos quebram-se quando são apertados na fábrica para evitar a manipulação.
1.  Utilize uma ferramenta rotativa (Dremel) com um disco de corte para fazer uma ranhura reta na cabeça de `cada` parafuso de cisalhamento.
2.  Utilize uma chave de fendas plana para desapertar e remover os parafusos.
3.  *Alternativa:* Utilize um alicate de pressão pequeno (Vise-Grips) para agarrar as extremidades da cabeça do parafuso e rodá-los, embora isto acarrete o risco de danificar a carcaça do sensor.
4.  Substitua estes parafusos de fábrica por parafusos M5 novos (recomenda-se vivamente parafusos de cabeça sextavada interior/Allen, pois são muito mais fáceis de aceder no espaço apertado atrás do coletor de admissão).

#### Passo 2: Calibrar Utilizando um Multímetro
1.  Desaperte ligeiramente os dois parafusos de montagem para que o TPS possa rodar.
2.  Rode a chave de ignição para a posição ON (motor desligado).
3.  Defina o seu multímetro digital (DVOM) para Tensão DC.
4.  Ligue a ponta de prova ao fio do meio (normalmente Vermelho/Azul ou Vermelho/Branco - o fio de sinal de retorno) e a uma fonte de massa (geralmente o fio Verde/Branco na cablagem do TPS, ou a massa do chassis).
5.  Com o acelerador totalmente fechado, rode o TPS até que o multímetro leia exatamente **0.50V**.
6.  Abra totalmente o acelerador (WOT) e verifique se a tensão sobe progressivamente de forma suave até **4.50V**.
7.  Aperte os parafusos de montagem.

> [!NOTE]
> O TPS pode facilmente rodar ligeiramente enquanto aperta os parafusos, alterando a calibração. Verifique sempre as leituras após o aperto final.

#### Passo 3: Calibrar Utilizando Datalogging
Se tiver um sistema de datalogging funcional (ex. Crome, Uberdata, Hondata):
1.  Ligue o seu datalogger e observe o canal da percentagem do TPS.
2.  Com o motor desligado e a chave na posição ON, verifique se o acelerador lê **0%** ao ralenti.
3.  Pressione o pedal do acelerador até ao fundo e verifique se lê **99%** ou **100%**. Se parar antes (por exemplo, perto de 90%), poderá ser necessário ajustar a folga do cabo do acelerador ou rodar o corpo do sensor.

## Notas e Cuidados

*   **Fixador de Roscas (Threadlock):** Como o TPS não requer ajustes de rotina, pode aplicar uma pequena gota de cola de roscas azul (média) nas roscas de montagem para evitar que se desapertem com a vibração do motor.
*   **Leitura Suave (Smooth Sweep):** Ao testar o TPS, observe atentamente o visor del multímetro ou o gráfico do datalogger enquanto abre e fecha lentamente o acelerador. A tensão deve subir e descer de forma suave e linear. Quaisquer saltos repentinos, quebras ou zonas mortas indicam um sensor avariado que precisa de ser substituído.

## Relacionado

*   [Sensor MAP](/cars/fueling/map-sensor)
*   [Sensor de Oxigénio](/cars/fueling/oxygen-sensor)
*   [ECU](/cars/ecu/ecu)
