---
summary: 'Autor: xtensive Data: 010403 20:47 Ok, aqui está o que descobri: Toda essa área são tabelas de dados. A rotina que chama o valor de ralenti é @279A para a pm6.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - tuning
  - rom
  - sensors
  - reference
  - diagnostics
  - ecu
sources:
  - name: 'pgmfi.org wiki'
    title: '91PM6 Target Idle'
    url: /pgmfi/wiki/library/91pm6-target-idle
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Ralenti Alvo da 91PM6

Autor: xtensive Data: 01-04-03 20:47 Ok, aqui está o que descobri: Toda essa área são tabelas de dados. A rotina que chama o valor de ralenti (idle) é @279A para a pm6. O ralenti de fábrica está definido para 768, pelo que consigo perceber. Procura o valor em 398F. Existem 6 definições de ralenti ali... sabem qual delas é escolhida para diferentes circunstâncias? ELD, etc., presumo eu? George, podes responder a uma pergunta rápida? (Este é código da pm6, mas deve ser próximo do da pm7) A rotina que chama este valor move o valor em x3995 para o ponteiro de dados, depois verifica se o bit `26h`.2 está definido. Se estiver, ignora o passo seguinte e continua pelo código. Se não estiver definido, move o valor em x398f para o ponteiro de dados e continua. A minha pergunta é porquê? O valor em x3995 é exatamente o mesmo que em 398f. Estranho? Mike

---

Autor: George Data: 01-04-03 23:51 Existem bastantes instâncias disto no código, pois parece que o código da PM6 foi derivado do da PM7. Se olharem para as tabelas da PM7, verão que há uma ligeira diferença — o meu palpite é que, quando reutilizaram o código da PM7, não se deram ao trabalho de remover essa secção, optando por deixar ambas as tabelas iguais. Outro exemplo deste tipo de situação está no limitador de velocidade — o código para implementar o limitador de velocidade ainda está no código da PM6, apenas foi configurado para uma velocidade extremamente elevada.
