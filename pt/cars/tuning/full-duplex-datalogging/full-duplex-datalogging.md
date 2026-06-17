---
summary: 'Explica a diferença entre comunicação série half-duplex e full-duplex em ECUs Honda OBD1 e por que razão a remoção do jumper J12 ativa o datalogging via PC.'
applies_to:
  obd: [1]
complexity: intermediate
tags:
  - datalogging
  - hardware
sources:
  - name: 'pgmfi.org wiki'
    title: 'Full Duplex Datalogging'
    url: /pgmfi/wiki/library/full-duplex-datalogging
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Datalogging Full-Duplex e o Jumper `J12`

Para fazer datalogging de uma ECU Honda OBD1 utilizando uma suite de afinação (tuning suite) baseada em PC (como o Crome, Hondata ou Neptune), deve configurar a interface de comunicação série da ECU para funcionar em modo **full-duplex**. Por definição, a ECU de fábrica está configurada para funcionamento em **half-duplex**.

Esta configuração é controlada por um jumper de solda físico na placa da ECU designado por **`J12`**.

---

## 1. Half-Duplex vs. Full-Duplex

O modo de comunicação dita a forma como os dados viajam entre a ECU e a sua ferramenta de diagnóstico:

* **Half-Duplex (J12 Fechado):** Neste modo, as linhas de transmissão (TX) e receção (RX) partilham um único caminho de sinal bidirecional. Apenas um dispositivo pode transmitir dados de cada vez. A ECU Honda de fábrica utiliza este modo para comunicar com as ferramentas de diagnóstico do concessionário (como o antigo Honda HDS) utilizando um protocolo mestre-escravo onde a ferramenta solicita dados e a ECU responde.

* **Full-Duplex (J12 Aberto):** Neste modo, as linhas de transmissão (TX) e receção (RX) são completamente separadas. Tanto a ECU como o PC podem enviar e receber dados simultaneamente através de cabos dedicados (utilizando o conector CN2).

---

## 2. Por que razão o Jumper `J12` Deve Ser Removido

Se tentar fazer datalogging com um PC enquanto o jumper **`J12`** ainda estiver fechado:

1. As linhas físicas RX e TX da ECU permanecem interligadas.
2. Quando o seu software de registo (datalogging) envia um byte de comando para a ECU, esse exato sinal é instantaneamente refletido de volta para o cabo recetor do PC.
3. O software de registo recebe o seu próprio comando como se fosse uma resposta de dados da ECU.
4. Esta incompatibilidade confunde a memória intermédia (buffer) de comunicação série, resultando em atraso de leitura (lag), dados corrompidos ou falhas completas de comunicação.

---

## 3. Como Ativar o Modo Full-Duplex

Para converter a ECU para funcionamento em full-duplex:

1. Localize o jumper **`J12`** na placa de circuito principal da ECU. Nas ECUs OBD1 padrão de Civics e Integras, esta é uma pequena ponte de solda de duas pistas localizada perto do MCU principal.
2. Utilize malha dessoldadora ou um ferro de soldar para remover a ponte de solda entre as duas pistas. Alternativamente, se for um jumper de fio, corte cuidadosamente o fio com um alicate de corte.
3. Certifique-se de que as duas pistas estão completamente separadas e que não resta nenhuma ponte de solda.

Assim que `J12` estiver aberto, a interface de comunicação série funcionará em modo full-duplex. Isto permite que o PC comunique de forma limpa com a ECU através dos pinos do conector **`CN2`** (utilizando linhas TX e RX separadas) sem refletir os dados de volta para o buffer de receção do PC.
