---
summary: 'Instruções passo a passo para converter uma cablagem de chassis OBD0 para funcionar com uma ECU OBD1.'
tags: [conversão, cablagem, hardware, obd0]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Kurts OBD0-OBD1'
    url: /pgmfi/wiki/library/kurts-obd0-obd1
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Kurts OBD0-OBD1

***Primeira tentativa de publicar este guia de conversão OBD1 no wiki.pgmfi.org. Algumas secções ainda precisam de revisão e encontram-se em itálico/negrito. Por favor, envie sugestões para [email protected].***

# Instalação do D16Z6 e conversão de cablagem OBD0 (88-91) para OBD1 (92-95) - Por Kurt_W

### Contribuições de ~StorminMatt e Noahk (do CRX Resource)

### Versão original de abril de 2001 revista por Lynne R

### Ligeiramente melhorada a partir de 2 de novembro de 2003

Esta conversão é feita num CRX Si de 89, embora também possa ser realizada em qualquer Civic de 4.ª geração ou CRX de 2.ª geração. Deve notar-se também que esta conversão pode ser feita usando qualquer um dos motores Honda da série D mais recentes, embora este guia em particular seja especificamente para a instalação de um D16Z6. O D16Y8 mais recente é também uma alternativa adequada ao D16Z6. Pessoalmente, não realizei um swap D16Y8, pelo que nem todos os pormenores me são conhecidos, logo não será incluída informação sobre o swap de um Y8 neste guia (nesta altura). Quaisquer referências a fontes de peças servem apenas como referência. Os autores e colaboradores não endossam necessariamente estas instituições. Lista das peças utilizadas/modificadas #Um CRX Si de 89 ligeiramente usado #D16Z6 de 93 (também conhecido como Z6) 1.6L SOHC VTEC #Cablagem parcial do motor de um D16Z6 de 93 e partes de cablagem (especificamente fichas da [ECU](/cars/ecu/ecu)) de um Civic DX de 92 (automático) #ECU [ECU](/cars/ecu/ecu) P28 de um Civic EX de 95 (manual) #Distribuidor de um Civic Si de 92

# #Injetores de combustível #4107 de anos desconhecidos (mais sobre isto adiante)

# Manual Chilton's Honda Civic/CRX de 1984-1991 e manual Haynes Honda Civic/Del Sol de 1992-1995 ou manuais de oficina Helms/Honda adequados

## Conversão de OBD0 para OBD1

Isto foi interessante; provação, sim, provação é a palavra correta. No geral, o processo demorou cerca de 15 horas. Foram gastas várias horas a analisar as instruções recebidas do ~StorminMatt para o processo, garantindo que estavam corretas (listadas abaixo). A cablagem do motor teve de ser modificada e a cablagem do tablier modificada ou construído um conversor para permitir que a [ECU](/cars/ecu/ecu) OBD1 fosse ligada à cablagem do tablier de 89. ATUALIZAÇÃO: Desde que escrevi originalmente este guia, a conversão OBD1 tornou-se muito mais popular, pelo que estão disponíveis cablagens de conversão pré-fabricadas. A maioria é fabricada artesanalmente por particulares, mas não conheço ninguém em particular que as produza.

### Conversão da Cablagem do Motor

É necessário converter a cablagem original do carro no qual o swap está a ser feito. A cablagem do motor OBD1 não encaixa na cablagem do motor OBD0 devido a fichas incompatíveis. Poderá ser possível alterar todas as fichas (removendo as fichas cinzentas da cablagem OBD1 e substituindo as brancas por estas na cablagem OBD0) e usar a cablagem OBD1 completa. Isto não foi tentado por não termos uma cablagem OBD1 completa para trabalhar.

**Nota:** Recomenda-se a remoção da cablagem do motor para facilitar a modificação. As cores dos fios serão listadas da seguinte forma: red/grn (indica fio vermelho com risca verde). Muitos fios podem ser retirados das fichas empurrando a parte frontal com uma chave de fendas pequena, por exemplo, enquanto puxa suavemente pela parte de trás do fio.

1. Resistência de Injeção: Existem duas formas de lidar com a resistência de injeção e com os injetores de combustível:
- Manter os injetores de combustível MPFI originais e a resistência de injeção. Este é o caminho mais simples. (Obrigado Noahk)
- Converter para os injetores mais recentes. Para tal, puxe o fio yel/blk da ficha verde da resistência de injeção. Este será reinstalado num espaço vago numa ficha cinzenta de 8 fios da cablagem OBD1. Esta ficha OBD1 tem 8 fios yel/blk a sair dela e tem uma tampa cinzenta. Ao remover a tampa, vê-se que tem um clipe metálico integrado que liga todos os fios yel/blk entre si.

2. Cablagem dos Injetores:
- Se mantiver os injetores MPFI originais e a resistência de injeção, não precisa de fazer nada.
- Para usar os injetores OBD1, as fichas dos injetores da cablagem OBD1 devem ser utilizadas. `Cada` ficha tem um fio de cor diferente (castanho, vermelho, azul claro e amarelo simples = injetores 1, 2, 3, 4 respetivamente) e um fio yel/blk que dela sai. O fio yel/blk de `cada` uma das fichas dos injetores liga-se de volta à ficha de 8 fios mencionada no passo #1. As fichas dos injetores OBD0 devem ser cortadas e as fichas dos injetores OBD1 soldadas. Faça corresponder as cores dos injetores entre si, pois são as mesmas em ambas as cablagens OBD0 e OBD1.

**Nota:** Na cablagem OBD0, o fio que vai da ficha do injetor para a resistência de injeção é red/blk. Não se preocupe com estes fios, pois apenas ligam a ficha do injetor OBD0 à resistência de injeção.

3. Sonda de Oxigénio (O2): Deve ser adicionada uma sonda de O2 de 4 fios. Para isso, devem ser adicionadas 3 linhas à cablagem. Uma linha vai da ficha da sonda de O2 para a ficha de 8 fios mencionada no passo #1. Este fio é yel/blk. Se não utilizou a ficha de 8 fios, ou seja, se não converteu para injetores OBD1, terá de encontrar outra fonte de alimentação para a sonda de O2. A segunda linha é uma linha grn/wht que vai da ficha da sonda de O2 para qualquer ponto do fio grn/wht na cablagem OBD0. A terceira linha é uma linha org/blk que vai para a [ECU](/cars/ecu/ecu). O último fio é branco e serve o mesmo propósito em ambos os carros OBD0 e OBD1. Este fio branco é o próprio fio da sonda de O2. Na cablagem do motor OBD0, é um fio simples e tem uma ficha bastante grande. Esta ficha deve ser cortada e o fio branco para a ficha OBD1 soldado. *Esta secção foi considerada pouco clara por alguns leitores, mas não foram recebidos comentários úteis sobre como torná-la mais clara... se alguém tiver sugestões...*

4. Re-cablagem do Distribuidor: Existem duas fichas a considerar, uma ficha de 7 fios e uma de 2 fios. Las linhas para a ficha de 7 fios do distribuidor podem ser retiradas de ambas as cablagens do motor. Retire a ficha cinzenta de 7 fios OBD1 do distribuidor da cablagem do motor OBD1 e substitua a ficha de 7 fios na cablagem OBD0 por ela. Certifique-se de fazer corresponder os fios provenientes do distribuidor com as cores correspondentes inseridas na ficha de 7 fios. Quanto à ficha de 2 fios, esta deve ser cortada da cablagem OBD0 e a ficha OBD1 emendada.

5. VTEC: Deve ser adicionado um fio à cablagem para a ativação do VTEC. Trata-se de uma ficha de 1 fio grn/yel na cablagem OBD1. Este fio deve ser passado para o interior do carro e ligado à [ECU](/cars/ecu/ecu).

6. Sensor de Pressão de Óleo do VTEC: Ficha de 2 fios, um fio é preto e o outro é blue/blk. O fio preto deve ser ligado à massa e o fio blue/blk vai para a [ECU](/cars/ecu/ecu). Isto é tudo para a conversão da cablagem do motor.

### Conversão da Cablagem do Tablier/Interior

Esta é a parte divertida. Existem duas formas de fazer isto.

**Nota:** Usar as fichas da [ECU](/cars/ecu/ecu) de um Civic de 92 (OBD1) é o ideal para esta conversão porque tem todos os fios necessários para a [ECU](/cars/ecu/ecu) do Z6. Se não conseguir encontrar as fichas da [ECU](/cars/ecu/ecu) de 92, tente obter as de um Si ou EX, caso contrário terão de ser adicionados fios adicionais. Se estas instruções forem utilizadas para uma série B OBD1, também será necessário adicionar um fio para o sensor de detonação (knock sensor) às fichas (a menos que sejam utilizadas fichas de [ECU](/cars/ecu/ecu) de um Del Sol VTEC OBD1).

1. Construir uma cablagem de conversão utilizando as fichas de [ECU](/cars/ecu/ecu) macho de um Civic de 92 ou semelhante e as fichas fêmea de uma [ECU](/cars/ecu/ecu) OBD0. Para remover as fichas da [ECU](/cars/ecu/ecu) OBD0, dessolde ou, se necessário, corte a placa da [ECU](/cars/ecu/ecu) com uma ferramenta Dremel equipada com um disco de corte. Depois de as fichas serem retiradas e limpas, os fios das fichas da [ECU](/cars/ecu/ecu) OBD1 podem ser soldados nos pinos apropriados das fichas OBD0. Veja abaixo as combinações corretas. Além de fazer corresponder os fios, 3 fios terão de ser passados para a cablagem para se ligarem às fichas OBD1. Estes fios são o fio do VTEC, o fio de pressão de óleo do VTEC e o fio da sonda de O2. Isto é mais facilmente alcançado se for utilizada uma cablagem de conversão OBD0-OBD1 pré-fabricada, como mencionado acima em "ATUALIZAÇÃO" OU
2. Cortar as fichas dos fios da [ECU](/cars/ecu/ecu) OBD0 e emendar os fios das fichas da [ECU](/cars/ecu/ecu) OBD1 aos fios da cablagem OBD0, conforme listado abaixo. Também terá de ligar os 3 fios adicionais mencionados acima no método #1. OU
3. Despinagem de todos os fios dos conectores OBD0. A maioria deles tem o mesmo tamanho que os pinos "pequenos" OBD1 e podem ser simplesmente inseridos no local correto. Os pinos OBD1 "grandes" precisarão de ser cravados ou emendados. (Nota do Dave)

Aqui estão as informações sobre a cablagem da [ECU](/cars/ecu/ecu) OBD1. Foram escritas originalmente por ~StorminMatt (obrigado Matt) do CRX Resource. Foram feitas várias adições à lista no sentido de a tornar mais útil e fácil de compreender, no entanto, a sua publicação foi mantida quase intacta porque ele explicou-a bem.

"Várias pessoas perguntaram-me como alterar as fichas da [ECU](/cars/ecu/ecu) de 1988-1991 para as fichas de 1992-1995 de forma a utilizar uma [ECU](/cars/ecu/ecu) de 1992-1995 em qualquer uma de várias aplicações (SOHC VTEC, B16A 2G, B18A/B18B de 1992+, B17A, B18C, etc.). Pensei que seria melhor fazer apenas uma publicação com esta informação em vez de ter de enviar e-mails separadamente a toda a gente. Há algumas coisas a ter em conta aqui. Pessoalmente, prefiro o sistema de numeração onde a Honda numera os pinos em linha e não o sistema em ziguezague. Mas compreendo que muitas pessoas prefiram ou estejam habituadas ao sistema em ziguezague. Por isso, para `cada` pino (em `cada` estilo de ficha), listo duas localizações para o mesmo pino. A primeira é dada numerando em linha. A segunda (entre parênteses) é dada pela numeração em ziguezague (espero que esteja correta). Caso tenha cometido algum erro na conversão E para tornar o processo de substituição das fichas mais à prova de erro, indico também a cor do fio na ficha de 1992-1995 e na ficha de 1988-1991 para os pinos indicados. Isto deverá dar-lhe uma melhor ideia se está a ligar os fios corretamente. Além disso, o primeiro conjunto de números de pinos e cores de fios são todos nas fichas de 1992-1995 e o segundo conjunto de números de pinos em parênteses retos são os das fichas de 1988-1991.

```
Ficha A (ficha 1992-1995)
A1 (A1) ----> A1 (A1) Injetor 1
brn --------> brn
A2 (A3) ----> A2 (A3) Injetor 2
red --------> red
A3 (A5) ----> A3 (A5) Injetor 3
lt. blu ----> lt. blu
A4 (A7) ----> A14 (A12) Relé Principal (Main Relay)
grn/yel ----> grn/blk
A5 (A9) ----> A5 (A11) EACV
grn/wht ----> blu/yel
A7 (A13) ---> B13 (B6) Luz de Aviso do Motor (Check Engine)
grn/org ----> grn/org
A8 (A15) ---> B2 (B3) Relé da Embraiagem do A/C
blk/red ----> yel
A11 (A21) --> B8 (B15) Sinal da Unidade de Ignição
red/grn ----> wht
A12 (A23) --> A9 (A2) Relé Principal (Main Relay)
blk --------> blk
A13 (A25) --> A6 (A13) Relé Principal (Main Relay)
yel/blk ----> yel/blk
A14 (A2) ---> A4 (A7) Injetor 4
yel --------> yel
A15 (A4) ---> (VTEC) grn/yel na cablagem do motor, à sua escolha no resto
org/wht ----> (sua escolha)
A16 (A6) ---> (Aquecedor O2S) para org/blk na cablagem do motor, à sua escolha no resto
org/blk ----> (sua escolha)
A17 (A8) ---> A15 (A14) Relé Principal (Main Relay)
grn/yel ----> grn/blk
A19 (A12) --> B12 (B4) Relé do Ventilador do Radiador
yel/grn ----> yel/grn
A21 (A16) --> B3 (B5) Alternador
wht/yel ----> wht/yel
A23 (A20) --> A11 (A6) Solenoide de Purga (Purge Control)
red --------> grn
A24 (A22) --> B9 (B17) Unidade do Ignitor
red/grn --------> wht
A25 (A24) --> A10 (A4) Massa (GND)
blk --------> blk
A26 (A26) --> A17 (A18) "Massa Múltipla"
blk/red ----> blk/red

Ficha B (ficha 1992-1995)
B1 (B1) ----> A7 (A15) Relé Principal (Main Relay)
yel/blk ----> yel/blk
B3 (B5) ----> B14 (B8) Interruptor do A/C
blu/red ----> blu/red
B5 (B9) ----> B7 (B13) Relé Principal (Main Relay)
blu/wht ----> blu/wht
B6 (B11) ---> B15 (B10) *
org --------> org
B7 (B13) ---> C2 (C3) *
org/blu ----> org/blu
B8 (B15) ---> C1 (C1) *
blu/grn ----> blu/grn
B9 (B2) ----> A16 (A16) Massa Múltipla
brn/blk ----> brn/blk
B13 (B10) --> B18 (B16) Sensor de Velocidade do Veículo (VSS)
yel/blu ----> yel/red
B14 (B12) --> B16 (B12) *
wht --------> wht
B15 (B14) --> C10 (C4) *
wht/blu ----> wht/blu
B16 (B16) --> C9 (C2) *
blu/yel ----> blu/yel

Ficha D (Ficha 1992-1995 - Não existe ficha C nas Fichas 1992-1995)
D1 (D1) ----> B1 (B1) Quatro Piscas (Hazard)
wht/blu ----> wht/grn
D2 (D3) ----> (Sensor de Detonação) Apenas motores da série B!
red/blu ----> (fio blindado à sua escolha)
D5 (D9) ----> B17 (B14) Alternador
pnk --------> blu
D6 (D11) ---> C4 (C7) Sensor de Posição da Borboleta (TPS)
red/blu(ou verde pastel) ----> red/blu
D7 (D13) ---> C11 (C6) Sensor de Temperatura do Líquido de Refrigeração (ECT)
red/wht ----> red/wht
D8 (D15) ---> C3 (C5) Temperatura do Ar de Admissão (IAT)
red/yel ----> red/yel
D9 (D17) ---> C6 (C11) Sensor MAP
wht --------> wht
D10 (D19) --> C8 (C15) Sensor MAP
yel/grn ----> yel/red
D11 (D21) --> C15 (C14) Sensor MAP
grn/blu ----> grn/wht
D12 (D2) ---> C13 (C10) Interruptor do Travão
grn/wht ----> grn/wht
D13 (D4) ---> B20 (B20) Conector de Serviço
brn --------> brn
D14 (D6) ---> (Interruptor de Pressão do VTEC) Fio blue/blk na cablagem do motor
org/blu ----> (sua escolha)
D16 (D10) --> B10 (B19) Sensor de Carga Eletrónica (ELD)
grn/red ----> grn/red
D18 (D14) --> C16 (C16) Sonda de O2
wht --------> wht
D21 (D20) --> C7 (C13) Sensor de Posição da Borboleta (TPS)
yel/wht ----> yel/wht
D22 (D22) --> C14 (C12) Massa comum para ECT/TPS/O2/etc.
grn/wht ----> grn/wht
```

Os pinos marcados com \* ligam-se aos sensores do distribuidor (ângulo da cambota, TDC e CYP) e, embora os carros de 1988-1991 e de 1992-1995 usem coletivamente as mesmas cores de fios para estes sensores (org, org/blu, wht, wht/blu, blu/grn, blu/yel), os fios de uma determinada cor NÃO se ligam necessariamente aos mesmos sensores nos carros de 1992-1995 que nos carros de 1988-1991. Por isso, se verificar o pinout da Hasport, as ligações que indiquei estarão incorretas. Contudo, é na verdade mais fácil apenas fazer corresponder as cores semelhantes. Se o fizer, lembre-se apenas de fazer corresponder as cores adequadas também na ficha do distribuidor. Por outras palavras, o fio org na cablagem do motor de 1988-1991 vai para o mesmo local na ficha do distribuidor de 1992-1995 que o fio org ia na cablagem de motor de 1992-1995. Apenas não confunda o fio branco grosso com o fio branco fino na ficha do distribuidor da cablagem do motor de 1988-1991. O fio branco grosso na cablagem de 1988-1991 vai para onde o fio yel/grn grosso ia na cablagem de 1992-1995 (na ficha do distribuidor de 1992-1995). Mas o fio branco fino na cablagem de 1988-1991 vai para onde o fio branco fino na cablagem de 1992-1995 ia. *Esta secção necessita de mais revisão para maior clareza, tratarei disso em breve... (KEW)* Para clarificar a informação sobre a cablagem do distribuidor, faça corresponder os fios de cor semelhante nas fichas do distribuidor (por exemplo: org com org) e na [ECU](/cars/ecu/ecu). Por outras palavras, o fio da mesma cor deve ir do distribuidor até à [ECU](/cars/ecu/ecu).

### Outros itens necessários diversos

Injetores de combustível: Os injetores de combustível modelo #4106 e #4107 estavam disponíveis de stock pessoal para este swap. Os injetores de combustível efetivamente utilizados foram os #4107, no entanto, não se sabe de que ano eram estes injetores (ou 93 ou 94), uma vez que estavam disponíveis injetores de ambos os anos. Os injetores #4107 foram utilizados porque funcionaram com a ECU P28 de 95 [ECU](/cars/ecu/ecu) que foi utilizada e os injetores #4106 não, embora não se saiba porque é que os #4106 não funcionaram. Deve ser feito o máximo esforço para obter injetores que correspondam à ECU P28 [ECU](/cars/ecu/ecu) a ser utilizada.
