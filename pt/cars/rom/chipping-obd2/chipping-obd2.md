---
summary: 'Guia de hardware para chipping de ECUs Honda OBD2 através da substituição do processador OKI 66507 por um microcontrolador OTP 66P507 programado utilizando um adaptador PLCC84 personalizado.'
applies_to:
  obd: [2]
complexity: advanced
tags:
  - ecu
  - chipping
  - hardware
sources:
  - name: 'pgmfi.org wiki'
    title: 'Chipping OBD2'
    url: /pgmfi/wiki/library/chipping-obd2
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Chipping de ECUs Honda OBD2 (OKI `66507` / `66P507`)

Um equívoco comum é que as ECUs Honda OBD2 não podem ser modificadas (chipped). Embora seja significativamente mais complexo e dispendioso do que fazer chipping em placas OBD0 ou OBD1, é inteiramente possível. 

Ao contrário das ECUs mais antigas que utilizam chips de memória externa ou possuem pistas de soldadura dedicadas para uma EPROM externa, as ECUs Honda OBD2 armazenam o seu código de funcionamento diretamente dentro da ROM interna do microcontrolador principal — tipicamente um processador SMT da série OKI `66507`. A modificação requer a substituição total deste microcontrolador.

---

## 1. Modificação de Hardware e Soldadura SMT

Como o microcontrolador de fábrica é um dispositivo de montagem em superfície (SMD) num invólucro PLCC84, as bombas dessoldadoras padrão não são suficientes.

### Procedimento de Chipping Recomendado:

1. **Remover o Processador OEM:** Dessolde o processador OKI 66507 de fábrica da placa. Recomenda-se vivamente a utilização de uma estação de retrabalho de ar quente para aquecer uniformemente todos os 84 pinos sem levantar as delicadas pistas de cobre na PCB multicamada.
2. **Limpar as Pistas (Pads):** Limpe todas as pistas de soldadura na PCB utilizando malha dessoldadora e fluxo (fluxo de solda), garantindo uma superfície completamente plana.
3. **Instalar um Socket:** Solde um socket de montagem em superfície PLCC84 na placa. Isto permitirá trocar facilmente os microcontroladores programados mais tarde.
4. **Inserir o Processador Modificado:** Insira um OKI 66P507 pré-programado (a versão OTP, ou One-Time Programmable, do MCU) no socket.

![ECU Spoon P73 mostrando a localização do microcontrolador SMT](spoon_p73_top.jpg)
*Vista superior de uma ECU OBD2 P73 modificada pela Spoon com o MCU principal destacado.*

---

## 2. Programação do OKI `66P507`

Como o OKI `66P507` é um microcontrolador OTP (One-Time Programmable), só pode ser programado uma vez. Deve escrever a imagem ROM correta logo na primeira tentativa.

Para gravar dados utilizando um programador de EPROM padrão (como um Willem ou dispositivo semelhante), deve utilizar uma placa adaptadora de programação personalizada. Este adaptador mapeia a pinagem PLCC84 do chip OKI para o layout DIP28 padrão de uma EPROM 27C512.

![Placa adaptadora de programação 66P507](66P507_progadaptorsized.jpg)
*Um adaptador de programador personalizado concebido para montar um microcontrolador PLCC84 OKI para programação.*

### Passos de Programação:

1. Ligue o adaptador personalizado ao seu programador de EPROM.
2. Coloque um MCU OKI `66P507` virgem no socket PLCC no topo do adaptador.
3. Configure o software de programação para ter como alvo uma EPROM **27C512** padrão.
4. Restrinja o intervalo de endereços de destino de **`$0000` a `$BFFF`** (representando o código ROM de 48KB).
5. Defina a tensão de programação (Vpp) para **12.5V** e selecione um algoritmo de programação padrão e lento para evitar erros.
6. Certifique-se de que o jumper de configuração do adaptador está na posição **"D"** (Data - Dados).
7. Inicie o ciclo de programação.

### Proteção de Leitura Opcional (Proteção Contra Cópia)

Para bloquear o microcontrolador e evitar que seja lido ou clonado:
1. Após gravar os dados com sucesso, mova o jumper do adaptador para a posição **"S"** (Security - Segurança).
2. Escreva o valor **`$00`** no endereço **`$0000`**. Isto queima o fusível de segurança interno no chip OKI.
 
> [!WARNING]
> Execute este passo de segurança apenas *após

* gravar os dados da ROM principal. Se gravar no endereço de segurança primeiro, o MCU bloqueará imediatamente, tornando-o permanentemente não programável e inutilizável.

---

## 3. Esquema do Adaptador de Programação

Para construtores avançados que desejem construir o seu próprio adaptador de programação, o esquema abaixo mapeia as ligações entre o socket PLCC84 do MCU e a interface do programador DIP28:

[![Esquema do adaptador de programação DIY para 66P507](66p507prog_cheap. GIF)](66p507prog_cheap. GIF)
*Clique no esquema para ampliar.*
