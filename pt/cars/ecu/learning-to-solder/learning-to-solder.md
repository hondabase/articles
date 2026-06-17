---
summary: 'Um guia prático para principiantes sobre técnicas de soldadura eletrónica, seleção de ferramentas, gestão térmica e segurança ao modificar placas de ECU Honda.'
applies_to:
  obd: [0, 1, 2]
complexity: beginner
tags:
  - hardware
  - education
sources:
  - name: 'pgmfi.org wiki'
    title: 'Aprender a Soldar'
    url: /pgmfi/wiki/library/learning-to-solder
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Guia de Soldadura para Modificações de ECU

Fazer chipping, socketing ou a conversão de uma ECU Honda requer soldadura manual precisa e de alta qualidade. Como as placas de circuito impresso (PCBs) da ECU são multicamada e contêm pistas de cobre delicadas, más técnicas de soldadura podem facilmente sobreaquecer componentes, criar pontes entre pinos ou levantar pistas (pads) da placa, destruindo permanentemente a ECU.

Este guia descreve as ferramentas essenciais, a escolha de componentes e as melhores práticas para a soldadura eletrónica.

---

## 1. Seleção de Ferramentas e Materiais

Escolher o equipamento certo faz uma diferença significativa na qualidade das suas juntas de solda.

### Ferro de Soldar
Evite ferros de soldar baratos e não ajustáveis (de ligar diretamente à tomada), pois aquecem demasiado e podem queimar as pistas.
*   **Recomendado:** Utilize uma estação de soldadura com controlo de temperatura (como uma unidade Hakko ou Weller). 
*   **Definição de Temperatura:** Ajuste o ferro entre **320°C e 370°C** (600°F a 700°F).
*   **Seleção da Ponta:** Utilize uma ponta tipo cinzel média ou uma ponta biselada. Estas formas têm maior área de superfície do que uma ponta cónica (tipo lápis), transferindo o calor para as pistas (pads) da placa muito mais rapidamente.

### Tipo e Tamanho de Solda
*   **Liga:** Solda com núcleo de resina (rosin-core) **60/40 (Estanho/Chumbo)** ou **63/37** é altamente recomendada para trabalhos de eletrónica amadora. A solda sem chumbo tem um ponto de fusão mais elevado e não flui tão facilmente, aumentando o risco de juntas de solda frias.
*   **Diâmetro:** Utilize um fio de solda fino, idealmente entre **0,6 mm e 0,8 mm** (0,024" a 0,031") de diâmetro. O fio de solda espesso facilita a aplicação de solda em excesso, resultando em pontes de solda.

### Fluxo
O fluxo limpa os óxidos metálicos das pistas (pads) e pinos, permitindo que a solda flua e adira corretamente. Utilize uma caneta de fluxo externa à base de resina ou do tipo "no-clean" para preparar as pistas antes de soldar.

---

## 2. Melhores Práticas para Soldar

Uma boa junta de solda é formada ao aquecer os metais a serem unidos e ao permitir que a solda derreta contra eles — e não ao derreter a solda diretamente na ponta do ferro.

1.  **Aqueça a junta primeiro:** 
    Coloque a face plana da ponta do ferro de forma a fazer contacto simultâneo com o pino do componente e com a pista de cobre (pad) na PCB. Segure-o nessa posição durante 1 a 2 segundos para aquecer ambas as superfícies.
2.  **Aplique a solda no lado oposto ao ferro:** 
    Toque com o fio de solda no lado oposto da junta do pino e da pista, não diretamente na ponta del ferro. O calor das peças metálicas deve derreter a solda, puxando-a para dentro do orifício de passagem.
3.  **Controle a alimentação da solda:** 
    Introduza o fio de solda lentamente. Pare assim que a solda flua ao redor de todo o pino e preencha o orifício.
4.  **Retire a solda e depois o ferro:** 
    Afaste primeiro o fio de solda e depois levante a ponta do ferro verticalmente para fora da junta.
5.  **Deixe arrefecer naturalmente:** 
    Não sopre para a junta para a arrefecer. Mover o componente enquanto a solda está a solidificar cria uma "junta de solda fria", fraca e granulada, que acabará por falhar.

---

## 3. Avaliar o seu Trabalho

Uma junta de solda correta deve parecer um cone côncavo e brilhante (ou a forma de um vulcão) ao redor do pino. 

*   **Bolas de Solda:** Se a junta parecer uma bola redonda e cinzenta baça, ou há solda em excesso ou os metais não foram suficientemente aquecidos (junta fria). Reaqueça a junta, aplique fluxo fresco e utilize uma bomba de dessoldar para remover o excesso.
*   **Pistas Levantadas:** Se aplicar calor por muito tempo (normalmente mais do que 4-5 segundos), a cola de suporte da pista de cobre irá vaporizar, levantando a pista da PCB. Mantenha o tempo de contacto curto.

---

## 4. Pratique Primeiro
A soldadura é uma competência mecânica que requer memória muscular. Antes de trabalhar numa ECU funcional, consiga um dispositivo eletrónico antigo e avariado (como um leitor de CD ou uma motherboard de computador) e pratique dessoldar e soldar componentes até conseguir fazer juntas limpas e brilhantes de forma consistente.
