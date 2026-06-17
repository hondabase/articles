---
summary: 'Uma introdução prática à instalação de sockets e chipping de ECUs Honda OBD0/OBD1.'
applies_to:
  engines: [B-Series, D-Series]
  ecus: [P28, P30, PM6]
  obd: [0, 1]
complexity: advanced
tags:
  - ecu
  - chipping
  - afinação
sources:
  - name: 'pgmfi.org wiki'
    title: 'Introduction To ECU Chipping'
    url: /pgmfi/wiki/library/introduction-to-ecu-chipping
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Introdução ao Chipping de ECUs

## Introdução ao Chipping de ECUs

por David Blundell. Sinta-se à vontade para ligar para este artigo, mas fazer "mirroring" é altamente desaconselhado, pois não receberá atualizações automaticamente.

### Como tudo funciona

Com a transição dos carburadores para a injeção eletrónica, os computadores assumiram um papel importante no funcionamento correto de um motor. O nível de controlo preciso possível com uma [ECU](/cars/ecu/ecu) (Engine Control Unit - computador para gerir um motor) não só permite melhorar significativamente a economia de combustível, mas também afinar o motor a um nível que é indiscutivelmente impossível com os melhores carburadores. Muitas [ECU](/cars/ecu/ecu)s, incluindo as fabricadas pela Honda, realizam interpolação de dados, permitindo-lhes compensar de forma inteligente as condições do motor que ficam "entre" estados conhecidos, permitindo uma resposta quase continuamente variável às variações das condições do motor. Além disso, a [ECU](/cars/ecu/ecu) pode fazer pequenas correções no combustível/ponto de ignição com base no estado de vários sensores do motor. É provavelmente justo dizer que, de fábrica, a maioria dos fabricantes afina a pensar na economia de combustível, emissões e gasolina de fraca qualidade, em oposição a potência e combustível de competição. A Honda não é exceção a estas regras de afinação. A base para isto pode ser vista muito claramente ao comparar os mapas de combustível e ignição europeus/americanos com os mapas de ignição japoneses para o mesmo motor. Os japoneses têm combustível que é, em média, no mínimo cerca de 10 pontos de octanagem superior ao vendido nos EUA. A comparação das curvas de ignição JDM e USDM/EDM geralmente mostra que os mapas JDM têm vários graus a mais de avanço de ignição, refletindo a expectativa do fabricante de uma gasolina de melhor qualidade. É de questionar quanto é que os 205 cv de um 1.8L (ITR) podem ser melhorados dentro das restrições do combustível de bomba. Não surpreenderia ninguém se mais 5 a 10 cv de pico e uma quantidade considerável de binário em baixas e médias rotações pudessem ser extraídos de um ITR com HORAS num banco de ensaio (dyno) e algumas alterações ao programa da [ECU](/cars/ecu/ecu). Isto serve para mostrar que, mesmo nos motores de "performance" da Honda, são feitas suposições muito conservadoras sobre a qualidade da gasolina utilizada. Se estiver disposto a usar gasolina de alta octanagem de forma consistente, geralmente podem ser encontradas melhorias significativas de desempenho afinando o carro para o combustível de melhor qualidade. Isto traz-nos a um ponto importante. A afinação é melhor realizada num banco de ensaio que consiga simular carga (como um dyno Dynapack ou Mustang). Os Dynojets são úteis apenas para afinar uma gama muito mais estreita de condições de funcionamento, nomeadamente aceleração com borboleta totalmente aberta (WOT) ao longo da gama de rotações. Quando não há um dyno disponível, algo que dê uma medida objetiva de como o carro está a responder é uma boa segunda opção. Sensores de oxigénio de banda larga (Wideband O2) e sondas de [EGT](/cars/tuning/exhaust-gas-temp-sensor) (temperatura dos gases de escape) podem dar uma ideia do que está a acontecer. As widebands geralmente fornecem informações mais diretas sobre a relação ar-combustível (AFR), mas são geralmente ineficazes para ajustar o ponto de ignição. As sondas [EGT](/cars/tuning/exhaust-gas-temp-sensor) dizem quão quentes estão os gases que saem do motor, o que pode ser usado para deduzir muita informação. Se a relação ar-combustível for mantida relativamente constante, a maioria das alterações nas EGTs pode ser atribuída ao ajuste do ponto de ignição. As relações ar-combustível causarão alterações nas EGTs, por isso certifique-se de que tem os seus valores de AFR razoavelmente próximos do seu objetivo *antes

* de tentar usar um EGT para afinar o seu ponto de ignição. Este artigo destina-se a ser uma **breve** introdução, por isso chega de conversa. No entanto, não desespere se não tiver acesso a um dyno. Os acelerómetros medem as forças de aceleração com uma precisão bastante boa (&lt;1%). Se conseguir registar esta informação como parte do seu procedimento de Data Logging, pode fazer algumas contas conhecendo o peso do veículo e a sua relação de transmissão para obter os valores de potência e binário do carro. Novamente, este método tem uma precisão de repetição bastante boa, mas uma exatidão relativamente fraca. Os números em si não significam muito, mas se conseguir produzir melhorias significativas e consistentes, significa que afinou melhor o carro. Uma nota final sobre ferramentas de afinação - o "banco de ensaio do rabo" (butt dyno) é uma forma totalmente inadequada de determinar o desempenho do carro - a maioria das alterações que fará num programa de computador serão subtis o suficiente para que provavelmente não consiga "senti-las" com precisão. O butt dyno tem precisão quase nula - já vi muitos jovens relatarem resultados "muito diferentes" sem qualquer alteração real num chip. Além disso, o butt dyno é muito melhor a detetar aumentos rápidos de binário do que um binário consistentemente maior. Binário consistente é o que torna um carro rápido, não a rapidez com que o binário aumenta. O que isto significa concretamente é que um carro pode "parecer" mais rápido no butt dyno por ter picos bruscos de binário, mas na realidade ser mais lento do que um carro com uma banda de potência mais suave com aumentos graduais de binário. Cuidado com a maioria dos "chips" do mercado pós-venda: na maioria das vezes, estes programas limitam-se a injetar mais combustível e a aumentar consideravelmente o ponto de ignição, ao mesmo tempo que elevam os limitadores de rotação muito para lá dos níveis seguros. Os ganhos que se podem obter com a maioria dos "chips de performance" são muito limited. A afinação, e não o simples "chipping", é o que geralmente produz ganhos reais e utilizáveis. Dito isto, alterar o programa de uma [ECU](/cars/ecu/ecu) geralmente não é assim tão complicado. Primeiro, seria provavelmente sensato focarmo-nos em alguns conceitos básicos de como as [ECU](/cars/ecu/ecu)s funcionam, para que seja mais evidente onde poderíamos fazer alterações para ter um efeito positivo no desempenho. A maioria das [ECU](/cars/ecu/ecu)s parece funcionar em dois modos. Num modo, a [ECU](/cars/ecu/ecu) monitoriza o máximo de sensores possível, tentando obter a melhor economia de combustível. Este modo é normalmente designado por "closed loop" (malha fechada) porque é um sistema de feedback fechado. No outro modo, a [ECU](/cars/ecu/ecu) corre uma rotina muito mais simples que é mais frequentemente ativada com a borboleta totalmente aberta (WOT). Este modo é normalmente chamado de "open loop" (malha aberta) porque não monitoriza continuamente os sensores nem calcula correções de combustível. As condições de open loop são geralmente armazenadas na forma de uma tabela onde a [ECU](/cars/ecu/ecu) "procura" os valores de combustível e ponto de ignição utilizando um algoritmo relativamente simples. Modificar as tabelas de combustível e ponto de ignição é a forma mais básica de reafinar um carro, no entanto, convém lembrar que a [ECU](/cars/ecu/ecu) fará ajustes com base na informação que possui. Na maioria dos casos, os valores das tabelas de open loop servem como valores de base para que as rotinas de correção de combustível em closed loop os ajustem, mas é difícil alterar o comportamento exato das rotinas de ajuste. Rotinas problemáticas de correção em closed loop requerem uma compreensão e possivelmente a reescrita do código que corre na [ECU](/cars/ecu/ecu) para serem corrigidas adequadamente. Pode alterar completamente as características de funcionamento de um motor alterando as tabelas de combustível e ponto de ignição. Como exemplo, uma ECU PM6 (Civic/CRX Si 88-91) é normalmente usada para gerir um D16A6, com ~100 cv. Com pouco mais do que alterar as tabelas de combustível, ponto de ignição e o limitador de rotação, uma PM6 pode gerir um ZC DOHC, de ~135 cv, como se viesse de fábrica. Além disso, pouco mais do que alterações ainda maiores nos mapas de combustível/ignição e alterações no limitador de rotação são tudo o que é necessário para faz-la gerir um B18A/B18B ou um B20B! Praticamente o mesmo hardware de ECU gere um motor D16Z6 SOHC VTEC e um B16A2/A3 DOHC VTEC - trocar os chips permitirá que a ECU de um motor faça funcionar o outro, e vice-versa. Num outro exemplo mais extremo, um amigo meu teve recentemente sucesso ao gerir um motor de Accord de 2ª geração com um computador da GM! Como espero que tenha percebido, há uma certa dose de arte e muita habilidade/experiência envolvidas na afinação correta de um carro. Uma explicação adequada de como afinar um carro na perfeição está muito além do âmbito deste artigo e da minha competência. Por favor, tenha cuidado ao alterar as tabelas de combustível/ignição do seu motor - entenda que as alterações de ponto de ignição podem alterar completamente as características de funcionamento do motor! Tenha muito cuidado, especialmente ao fazer afinações de base - pode destruir o seu motor em segundos com um mau programa. Use ferramentas adequadas (wideband, EGT, acelerómetro, dyno) sempre que possível. Vamos agora **assumir** que já sabe quais os ajustes de combustível e ponto de ignição que precisa de fazer, independentemente de ser este o caso ou não. Com esta importante ressalva feita, as ferramentas e os métodos a partir deste ponto vão tornar-se muito mais específicos:

- Edição hexadecimal e edição de ROM raw
- Editores de ROM
 - Ghettodyne (OBD0)
 - Turboedit (OBD0)
 - BRE (Ben's ROM Editor - OBD0 VTEC)
 - Uberdata (OBD1)
 - Crome (OBD1)
- Chipping de uma ECU: hardware
 - Chips e Gravadores de ROM
 - Equipamento de soldar e dessoldar
 - Chipping de ECU OBD0
 - Chipping de ECU OBD1
 - Chipping de ECU OBD2
- Resolução de Problemas

---

#### Edição hexadecimal e edição de ROM raw

Hexadecimal é um sistema de numeração de base 16. Em vez de dígitos de 0 a 9, o hexadecimal usa dígitos de 0 a F. Portanto, A = 10, B = 11,... F = 15. Normalmente, distinguimos números hexadecimais de outros números colocando 0x à frente do número ou colocando um 'h' no final. Ou seja, 0xFE e FEh são ambos o número hexadecimal FE. As tabelas de combustível e ponto de ignição estão armazenadas no meio do código que corre na [ECU](/cars/ecu/ecu). Distingui-las do código geralmente não é ASSIM tão difícil porque parecem diferentes dos dados pseudo-aleatórios que correm no computador. Um editor hexadecimal permitir-lhe-á manipular os dados raw na [ECU](/cars/ecu/ecu). O [WinHex](http://www.x-ways.net/winhex/index-m.html) é um editor hexadecimal shareware de qualidade disponível em www.download.com. Pode querer obter alguns utilitários de checksum em www.keil.com, pois são geralmente úteis. No WinHex: ![winhex.gif](winhex.gif)Então, encontrou as tabelas de combustível e ponto de ignição no programa da sua [ECU](/cars/ecu/ecu), edite à vontade. Como interpreta tudo isto? Bem, primeiro deve saber os endereços. Cada byte tem o seu próprio endereço referenciado pela coluna mais à esquerda (a coluna de "offset") e a linha superior. Como exemplo, olhe para o canto inferior direito da imagem acima. Note o byte que tem 6f como valor. Siga a linha correspondente até à coluna de offset e verá 3ef0. Depois, siga a coluna do 6f até ao F na linha superior. Junte esses valores e terá o endereço do byte 6f: 0x3eff. E agora? Estes dados são a representação binária do código de máquina real que corre no processador da ECU e dos dados da ROM que a [ECU](/cars/ecu/ecu) utiliza. Para descobrir o que faz, deve usar um desassemblador para converter o código/dados binários em instruções de código de máquina que sejam mais legíveis por humanos. A maioria das [ECU](/cars/ecu/ecu)s tem uma rotina de Check Sum - os deuses do checksum devem ser apaziguados após quaisquer alterações à ROM, caso contrário o carro não funcionará corretamente. Levaria muito tempo a afinar um carro se todos tivessem apenas editores hexadecimais à sua disposição. Em muitos casos, estão disponíveis editores de ROM para ajudar no processo de afinação.

---

#### Editores de ROM

Lembre-se, tudo o que pode fazer com um editor de ROM também pode ser feito à mão com um editor hexadecimal. Embora a maioria dos Editores de ROM seja específica para uma ou mais [ECU](/cars/ecu/ecu)s, a maioria é visualmente bastante semelhante - "Compreender Mapas" tem muitas imagens e explicações mais práticas sobre o ajuste de tabelas de combustível e ponto de ignição baseado em editores. A maioria dos conceitos aplicar-se-á a todo e qualquer editor.

---

##### Ghettodyne (OBD0)

O Ghettodyne (disponível em [http://web.archive.org/web/20110128180504/http://ghettodyne.com/](http://web.archive.org/web/20110128180504/http://ghettodyne.com/)) é um editor de ROM gratuito que foi o primeiro a suportar a [ECU](/cars/ecu/ecu) PM6 (CRX/Civic Si 88-91). **Já não está a ser desenvolvido ativamente.** Para ter uma ideia de como é o Ghettodyne: ![ghettodyne_small.jpg](ghettodyne_small.jpg)

---

##### Turboedit (OBD0)

O [TurboEdit](http://web.archive.org/web/20220701161603/https://turboedit.org/) substituiu em grande parte o Ghettodyne como o editor de ROM OBD0 desenvolvido de forma mais ativa. Suporta ROMs baseadas na base de código PM6 e PM7 neste momento. A comunicação próxima entre a [Team OBD0](/pgmfi/wiki/home/team-obd0) e Jason Parker, autor do TE, garante o suporte rápido aos recursos mais recentes. Como pode ver, a interface é muito semelhante aos editores anteriores: ![TE2_SS.jpg](TE2_SS.jpg)- [Fórum Turboedit no PGMFI](/pgmfi/forum/forum.php?id=39) - principalmente editor
- [Fórum de Desenvolvimento 8XC154 no PGMFI](/pgmfi/forum/forum.php?id=7) - novas ROMs e código

---

##### BRE (Ben's ROM Editor - OBD0 VTEC)

O BRE é indiscutivelmente um dos melhores editores para [ECU](/cars/ecu/ecu)s OBD0 VTEC, como as PR3 e PW0. Corre em Windows. Esperamos que o Ben passe por aqui e adicione mais informações sobre o mesmo.
- [Fórum BRE no PGMFI](/pgmfi/forum/forum.php?id=36)
- [Fórum de desenvolvimento OBD0 VTEC no PGMFI](/pgmfi/forum/forum.php?id=14)

---

##### Uberdata (OBD1)

O Uberdata foi o primeiro editor de ROM disponível publicamente para Civics/Integras OBD1, escrito por Blake Warner (Uberteg). Utiliza principalmente o código P72 e P75, mas foi adaptado para gerir quase qualquer motor Honda. Tem suporte sólido para sobrealimentação (boost), suporte para o Transtronics Romulator e adicionou recentemente suporte para scripting em assembly inline. Corre em Windows.
- [Fórum Uberdata no PGMFI](/pgmfi/forum/forum.php?id=27)
- [O Lar do Uberdata](http://www.ecimulti.org/uberdata)
- [Fórum de Desenvolvimento OBD1 no PGMFI](/pgmfi/forum/forum.php?id=8)

---

##### Crome (OBD1)

O Crome é o primeiro editor de ROM OBD1 programável por scripts, escrito por John Cui. Os recursos principais são projetados para o código JDM P30 "203", mas tem suporte para muitas outras ROMs em menor grau. A nova versão do Crome (março de 2004) suporta a solução de Programação em Tempo Real (RTP) do PGMFI e melhorou o código de boost em comparação com as versões anteriores. Também possui uma nova interface de plugins que permite front-ends baseados em HTML para scripts.
- [Fórum Crome no PGMFI](/pgmfi/forum/forum.php?id=35)
- [Fórum de Desenvolvimento OBD1 no PGMFI](/pgmfi/forum/forum.php?id=8)

---

#### Chipping de uma ECU: hardware

##### Chips e Gravadores de ROM

Neste ponto, assumiremos (independentemente de ser realmente verdade ou não) que criou com sucesso uma nova imagem de ROM e quer colocá-la numa [ECU](/cars/ecu/ecu). O próximo passo para a reprogramação é pegar na imagem eletrónica que criou e gravá-la numa EPROM (Erasable Programmable Read Only Memory). As EPROMs para uso automóvel têm geralmente 128K, 256K ou 512k de tamanho. Quase todos os Hondas de 88-95 utilizam uma EPROM 27 `C256`. Existem muitos tipos de Chips para ECUs que pode utilizar. Preste atenção à velocidade do chip e se o seu Gravador de ROM o consegue programar. Os gravadores de ROM são os dispositivos utilizados para programar chips. Não importa muito qual o modelo que adquire, desde que consiga programar Chips para ECUs. A entrada na Wiki de Gravadores de ROM tem uma lista de alguns tipos comuns de gravadores utilizados para programação de [ECU](/cars/ecu/ecu) e, em alguns casos, tem links para análises e preços. Não importa QUAL programador possui; o que importa é ser capaz de programar os chips certos.

##### Equipamento de soldar e dessoldar

Comprei uma Estação de Soldar e Dessoldar Xytronics com controlo de temperatura por menos de 400$ com portes incluídos da Howard Electronics Inc. Ferramentas de dessoldar profissionais com fontes de vácuo integradas podem ser facilmente obtidas no eBay ou noutros comerciantes - o equipamento Pace e Metcal está sempre no eBay. Falei com muitas pessoas que compraram equipamento profissional por menos de 100$ e que funcionou bem para elas. Se mexer em muitas [ECU](/cars/ecu/ecu)s, uma Estação de Dessoldar de qualidade será uma das suas ferramentas favoritas pelo tempo e sofrimento que poupa. No lado mais barato/DIY, existem várias outras ferramentas que funcionam adequadamente. Um ferro de dessoldar barato funcionará bastante bem, especialmente com a ponta certa e algumas pequenas modificações. Muitas vezes, uma ferramenta de dessoldar existente pode ser modificada para torná-la mais eficaz. A fita de dessoldar (malha) pode ser muito eficaz quando usada corretamente, e pode até ser superior a uma Estação de Dessoldar em alguns casos. Um Ferro de Soldar de qualidade é outra ferramenta pela qual se agradecerá por ter comprado sempre que a utilizar. Pontas pequenas e menos potência facilitarão a sua vida. O controlo de temperatura é um bom recurso, embora de forma alguma obrigatório. Tive muita sorte com os ferros azuis baratos da Rat Shack de 12-15W com ficha de 3 pinos em caso de aperto. "Aprender a Soldar" e "Dicas para Dessoldar" contêm muitas boas dicas para quem está a começar, mas não há realmente substituto para a prática. Trabalhar em algumas [ECU](/cars/ecu/ecu)s/placas de circuito sacrificáveis antes de mexer numa [ECU](/cars/ecu/ecu) que precisa de ir para o seu veículo é provavelmente uma excelente ideia. Tal como na soldadura tradicional (de metal), o segredo é sentir-se confortável com o ferro, a solda e o espaço de trabalho que tem! Estraguei cerca de metade da primeira dúzia de [ECU](/cars/ecu/ecu)s que fiz. A maioria foram apenas soldaduras frias ou fracas fáceis de corrigir, embora tenha queimado duas PR3s por não as dessoldar completamente e arrancar as pistas e pads da placa. Reparar uma aventura de soldadura destrutiva como essa pode ser muito stressante e difícil. Depois de comprar a minha Estação de Dessoldar, queimei aproximadamente 3 [ECU](/cars/ecu/ecu)s em 200 (e uma dessas ainda acho que foi culpa de um alternador/regulador de tensão avariado...). Parte disto deveu-se certamente à prática, mas ter as ferramentas certas fez uma **grande** diferença.

---

##### Chipping de ECU OBD0

Se tem uma [ECU](/cars/ecu/ecu) OBD0, fazer o chipping da [ECU](/cars/ecu/ecu) pode não ser simples. Quase TODAS as [ECU](/cars/ecu/ecu)s PM6, PM7, PR4 e PP5 (com catalisador) de 90-91 tinham EPROMs externas, sendo fácil alterar o programa nas mesmas. Quase todas as [ECU](/cars/ecu/ecu)s PG7, PM6, PM7 de 88-89 e PM8 de 88-91 não tinham EPROM externa. É possível fazer o chipping destas [ECU](/cars/ecu/ecu)s, mas requer consideravelmente mais trabalho e está além do âmbito deste artigo. Consulte "Chipping de ECU 88-89" para mais detalhes. A seguinte [ECU](/cars/ecu/ecu) é uma PM7 que não possui uma ROM externa: ![trickyPM7small.jpg](trickyPM7small.jpg)Se tiver mais sorte e tiver uma [ECU](/cars/ecu/ecu) com EPROM externa de fábrica, a sua [ECU](/cars/ecu/ecu) assemelhar-se-á mais a esta: ![PM6tochip_small.jpg](PM6tochip_small.jpg)Uma [ECU](/cars/ecu/ecu) OBD0 com uma EPROM externa é muito simples de modificar. Primeiro, corte todos os 28 pinos com uma lâmina de barbear ou uma faca multiusos. TENHA CUIDADO PARA NÃO ESCORREGAR, POIS PODE DANIFICAR PERMANENTEMENTE A PLACA DE CIRCUITO. Não é absolutamente necessário fazer isto antes de dessoldar, mas remover o chip tornará tudo muito mais fácil, particularmente se não tiver uma boa estação de dessoldar. Assim que a ROM original estiver dessoldada e removida e conseguir ver através dos orifícios na placa de circuito, adicione um socket para EPROM e depois coloque a nova ROM que criou no socket.

---

##### Chipping de ECU OBD1

Agora, com a sua nova EPROM pronta, abra a caixa da sua [ECU](/cars/ecu/ecu). Todas as [ECU](/cars/ecu/ecu)s de 92-95 fabricadas pela Honda eram capazes de aceitar EPROMs externas, mesmo que não viessem com uma de fábrica. Todas as [ECU](/cars/ecu/ecu)s de 92-95 utilizam o mesmo procedimento para chipping. Os iniciantes devem ter cuidado com as [ECU](/cars/ecu/ecu)s japonesas (JDM), pois utilizam componentes de montagem em superfície (SMD) que são marginalmente mais difíceis de trabalhar do que as [ECU](/cars/ecu/ecu)s americanas/europeias. Consulte aqui para Chipping de ECU JDM P30. A secção da ECU P28 de um Civic Si 93 de exemplo que é importante para o chipping está contornada a vermelho na seguinte imagem: (A Honda foi simpática e também a contornou com uma linha tracejada branca para si na placa) ![P28chipping_small.jpg](P28chipping_small.jpg)Primeiro, deve dessoldar os componentes serigrafados a branco na placa de circuito. Assim que todos os pads estiverem dessoldados e conseguir ver através dos orifícios para os componentes na secção vermelha acima, precisa de começar a soldar os componentes. Não são usados componentes bizarros - tudo deve ser facilmente obtido na sua loja de eletrónica local ou distribuidores online. A Honda foi simpática o suficiente para identificar na placa onde tudo vai. Coloque o chip `74HC373` na placa onde indicado e solde-o na posição. `R54` deve ser preenchido com uma resistência de 1k a 1.2k (o valor exato não importa). `C51` e `C52` são condensadores cerâmicos de disco de 0.1µf (12V ou superior funcionará perfeitamente). Coloque um socket de 28 pinos para a ROM onde está marcado 27256. (Já agora, gaste um pouco mais de dinheiro e compre sockets de pinos torneados de qualidade muito superior em vez dos tipos baratos de lâmina metálica dobrada.) Assim que o socket estiver no lugar, coloque a ROM que programou anteriormente. Finalmente, ligue `J1` com um pequeno fio para ativar a ROM externa. Não são necessárias outras alterações além de cortar `J1` para restaurar a [ECU](/cars/ecu/ecu) ao seu estado original. Aqui pode ver uma ECU P28 com o chipping feito. A pessoa que fez a modificação usou um socket para o `74HC373`, bem como para a ROM, e usou um jumper real em vez de apenas ligar `J1` com um fio. No entanto, dá-lhe uma ideia de como deve ficar quando terminar: ![P28done_small.jpg](P28done_small.jpg)

---

##### Chipping de ECU OBD2

Se tem uma [ECU](/cars/ecu/ecu) OBD2, terá de esperar ou comprar equipamento comercial Tech Tom. É possível remover o MCU 66K e substituí-lo por outro OTP 66P507 ou FLASH 66Q589 (conforme o caso), mas isto está longe de ser simples. Sabe-se muito pouco sobre o código OBD2. Consulte "Chipping OBD2 por Doc".

---

#### Resolução de Problemas

Neste ponto, deverá ter uma [ECU](/cars/ecu/ecu) funcional com um novo programa. Se obtiver um LED vermelho aceso fixo numa [ECU](/cars/ecu/ecu) OBD0 ou uma luz de aviso do motor (CEL) contínua num carro OBD1 e o carro funcionar pessimamente, com um limitador de rotação muito baixo e um ralenti instável, provavelmente tem uma má ligação. Se a mesma coisa acontecer 30 a 45 segundos após ligar o carro, provavelmente esqueceu-se de apaziguar os deuses do checksum. Se o carro funcionar de forma estranha, tente colocar um programa original para verificar se as alterações de combustível/ponto de ignição que fez não foram prejudiciais.

## Conclusão

Espero que, neste ponto, tenha aprendido um pouco sobre as [ECU](/cars/ecu/ecu)s, como funcionam e avariam, e como modificá-las. Se tiver mais interesse, consulte o resto da Wiki ou Leituras Adicionais. A [ECU](/cars/ecu/ecu) é apenas uma ferramenta que permite a entrega precisa de combustível e ponto de ignição - saber como modificar a própria [ECU](/cars/ecu/ecu) é apenas metade da batalha para ter um carro bem afinado. Dedique tempo e orçamente dinheiro para as ferramentas certas para afinar o carro, não apenas fazer o chipping da [ECU](/cars/ecu/ecu).
