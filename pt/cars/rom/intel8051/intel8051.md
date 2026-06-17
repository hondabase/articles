---
summary: 'Para tudo o que queira saber e um excelente tutorial, aceda a http://www.8052.com Qualquer montador (assembler) de 8051 funcionará bem para programação.'
applies_to:
  obd: [0, 1, 2]
complexity: advanced
tags:
  - hardware
  - education
  - tuning
  - rom
  - sensors
  - reference
sources:
  - name: 'pgmfi.org wiki'
    title: Intel8051
    url: /pgmfi/wiki/library/intel8051
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Intel 8051

Para tudo o que queira saber e um excelente tutorial, aceda a [http://www.8052.com](http://www.8052.com). Qualquer montador (assembler) de 8051 funcionará bem para programação. O Sysrad51, disponível [aqui](http://www.systronix.com/RAD51/RAD51.exe), parece ser popular. Tenha cuidado ao remontar (reassembling) um ficheiro após efetuar alterações... O Sysrad parece ter alguns bugs estranhos a este respeito. O [Batronix](http://www.batronix.com) [Prog Studio](/cars/electronics/prog-studio) também parece ser bastante popular. O [ASEM-51](http://plit.de/asem-51/download.htm) parece interessante. Tem alguns IDEs complementares, o [MIDE](http://www.opcube.com/home.html) e o [4Flash](http://web.archive.org/web/20090609052822/http://www.reinerjansen.de:80/4flash/). O ambiente de desenvolvimento preferido do Blundar é agora MIDE+ASEM-51. Nota: certifique-se de que tem dois pontos ":" após todas as etiquetas (labels) - o ASEM51 é muito mais exigente do que o SYSRAD. Dave Blundell modificou o [d51](http://www.8052.com/users/disasm/) para suportar a utilização não padrão da OKI de [A5](/cars/diagnostics/a5) criando o [Pgmfi D51](/cars/rom/pgmfi-d51). Chris Favreau compilou alguns binários para Windows do mesmo. Pode descarregar o código fonte e os binários para Linux/Windows [aqui](/cars/rom/pgmfi-d51). Este parece ser um simulador de [8051 interessante](http://home.t-online.de/home/Jens.Altmann/jsim-e.htm) Alguns recursos de 8051:

- [Guia de referência compacto](http://web.archive.org/web/20090518051420/http://myhome.naver.com:80/zxcv0070/chip/8051data%20book.htm)
- [Outra referência compacta](8051ref.pdf)
- [jEdit](http://jedit.org) - o jEdit 4.2pre8 e superior inclui uma definição de Modo de Edição com realce de sintaxe MCS51 para edição de assembly 8051

| **Anexo:** | **Modificar:** | **Tamanho:** | **Data:** | **Quem:** | **Comentário:** |
| :--- | :--- | :--- | :--- | :--- | :--- |
| ![](/pgmfi/wiki/assets/icn/exe.gif) [RAD51.exe](RAD51.exe) | mod | 5891853 | 20 Jul 2004 - 04:21 | blundar | Cópia do Sysrad51 localmente em 18/07/04 |
