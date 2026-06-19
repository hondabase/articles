---
summary: 'Dicas práticas, truques e melhores práticas para dessoldar componentes de placas de circuito impresso delicadas de ECUs.'
tags: [hardware, education]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Desoldering Tips'
    url: /pgmfi/wiki/library/desoldering-tips
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Dicas e Melhores Práticas de Dessoldagem

A dessoldagem de components em placas de circuito impresso (PCB) multicamadas de ECUs requer precisão para evitar levantar pistas de cobre ou destruir a metalização dos orifícios (through-hole plating). Abaixo encontram-se dicas e técnicas essenciais para obter resultados limpos.

## 1. Aguardar pela Liquefação Completa da Solda

A paciência é o fator mais crítico.
* **O Erro:** Aplicar sucção no momento em que a camada superior da solda parece amolecida.

* **A Forma Correta:** Aguarde alguns segundos para que o calor seja transferido por completo através do orifício da PCB até ao lado oposto da placa. A solda deve estar completamente fundida em toda a profundidade do orifício antes de aplicar a sucção. Caso contrário, deixará um bujão de solda preso a meio caminho, forçando-o a soldar novamente e a tentar de novo.

## 2. Gerir a Massa Térmica (Pinos de Massa/Ground)

A quantidade de calor necessária é diretamente proporcional ao tamanho das pistas de cobre ligadas ao pino.

* Os pinos ligados a pistas de sinal padrão fundem rapidamente.
* Os pinos ligados aos planos principais de massa/ground (como o Pino 15 em muitos circuitos integrados padrão) funcionam como dissipadores de calor massivos. Eles dissipam o calor da ponta do seu ferro de soldar rapidamente. Terá de manter a ponta do ferro nestes pinos durante um pouco mais de tempo, ou usar uma ponta ligeiramente mais larga, para que a solda derreta completamente.

## 3. A Técnica de "Balanço"

Ao lidar com componentes difíceis, balance suavemente o pino para a frente e para trás com a ponta do ferro ou com um alicate de pontas finas num ritmo lento (cerca de uma vez por segundo). Isto ajuda a quebrar a ligação mecânica entre o pino e as paredes internas do orifício metalizado à medida que a solda arrefece.

## 4. Uso Correto de Fita Dessoldadora (Malha)

A fita/malha dessoldadora é altamente eficaz para a limpeza:

* Coloque a malha limpa diretamente sobre a junta.
* Aplique a face plana da ponta do seu ferro sobre a malha, pressionando-a contra a junta.

* Assim que vir a malha absorver a solda (esta mudará de cor para prateado), levante a malha e o ferro em conjunto.
* **Atenção:** Nunca puxe a malha para fora da placa enquanto a solda estiver fria, ou poderá arrancar a pista de cobre da placa.
