---
summary: 'Como os sensores de oxigénio de banda larga diferem dos de banda estreita, integração com controladores pós-venda (aftermarket) e configurações de registo de dados.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - sensor
  - fueling
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: 'Wide Band O2'
    url: /pgmfi/wiki/library/wide-band-o2
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Sonda Lambda de Banda Larga (Wideband O2)

***O que é um sensor de oxigénio de banda larga (Wideband O2)?*** É um [Sensor de Oxigénio](/cars/fueling/oxygen-sensor) que fornece uma leitura estável numa gama muito maior do que as sondas lambda normais de 1 ou 4 fios. É útil para determinar a relação ar-combustível (AFR) na afinação de ECUs. O mercado tornou-se um pouco mais competitivo, por isso farei um breve resumo. Tradicionalmente, existiam duas opções para medidores de banda larga/lambda: a unidade da MoTec e a oferta da FJO. Estas podem custar entre 600 a 1000 dólares ou mais, por isso focar-me-ei em soluções mais baratas. O novo sensor Bosch LSU4 é uma excelente novidade para a comunidade porque é equipamento original (OEM) nalguns modelos da VW e pode ser adquirido por valores entre 30 e 60 dólares. Anteriormente, as opções eram geralmente o NGK L1H1 e o sensor Bosch UEGO mais antigo (LSM-11?).

***O que é uma saída de banda estreita (narrowband)?*** A banda estreita é o sinal que o seu sensor de oxigénio original fornece. Está na gama de 0-1 V, pelo que não tem muita resolução ou "precisão". Além disso, foi projetado para reduzir custos e apenas diz se está acima ou no ponto estequiométrico (14.7:1 A/F). Isto não é suficientemente preciso para afinação.

![NarrowbandOutputGraph.jpg](http://plxdevices.com/M-200/NarrowbandOutputGraph.jpg)

***O que é uma saída de banda larga (wideband)?*** É utilizado um elemento sensor mais complexo, que pode fornecer uma resolução mais útil de 0-5 V. Foi também concebido para ser preciso, recalibrável em tempo real, e com menos ênfase na produção de uma unidade económica em massa. Um sensor de banda larga precisa de um circuito especial e de uma fonte de alimentação para controlar as suas exigências delicadas de aquecimento. Este é o "controlador de banda larga", ou caixa controladora, que vê publicitado.

![WidebandOutputGraph.jpg](http://www.plxdevices.com/M-200/WidebandOutputGraph.jpg)

***Como posso tirar partido disto?*** Vejo duas opções principais. Instalar um casquilho (bung) soldado na sua tubagem de escape (downpipe) para a montagem de um segundo sensor de oxigénio permanente. Se planeia usar a unidade no carro a tempo inteiro, mantenha a ECU a funcionar a partir da saída de banda estreita da sonda original e faça a afinação através do sensor de banda larga dedicado e da respetiva unidade de controlo. Uma vez afinado, pode remover o sensor de banda larga e usar um tampão roscado para selar o casquilho. O segundo método é mais complexo, mas é preferível para quem usa a sonda de banda larga de forma portátil para afinar carros diferentes. Remove-se o sensor de oxigénio original e instala-se o sensor de banda larga no seu lugar. Depois, envia-se um sinal simulado de banda estreita a partir do controlador de banda larga para a ECU. (A saída de banda estreita do controlador de banda larga é apenas a informação de banda larga convertida para a escala de 0-1 V.) Para facilitar a instalação, pode usar uma cablagem de conversão/passagem OBD1-OBD1, em vez de cortar e emendar a cablagem do chassis do cliente. Teoricamente pode haver um problema aqui, porque quando terminar a afinação e colocar o carro a funcionar novamente com a sonda de banda estreita original, podem ocorrer ligeiras inconsistências. É necessária mais investigação/opiniões sobre isto. Muito bem, passemos às nossas opções económicas:

***Innovate Motorsports:*** [https://www.innovatemotorsports.com](https://www.innovatemotorsports.com)
Nova no mercado, preços/lista de funcionalidades muito competitivos. Utiliza o novo e barato sensor LSU4. Tem uma rotina de calibração do sensor (patente pendente) que nenhuma das outras empresas oferece. Ecrã LCD integrado para exibição de valores. Saídas programáveis (saída de banda estreita, saída de banda larga, o que preferir), inclui um software de registo de dados, ao qual falta apenas a leitura de RPM neste momento (prevista para breve). É um pouco grande para montagem permanente, sendo mais um dispositivo de afinador, mas pode ser facilmente ocultado e utilizar a saída de banda estreita para alimentar um manómetro A/F.

***AEM UEGO:*** [https://www.aemelectronics.com](https://www.aemelectronics.com)
Utiliza um sensor muito semelhante ao Bosch LSU4, mas o preço é artificialmente alto porque apenas a AEM o fornece. O produto carrega o nome e a reputação da AEM. Pode controlar 2 sensores de banda larga, ideal para motores V6 ou V8, ou qualquer configuração com 2 sondas lambda. Não possui ecrã LCD interno, pelo que precisa de passar as tensões de saída para um sistema de gestão de combustível independente (standalone), para a ECU, para um manómetro A/F ou para a sua configuração de registo de dados. As saídas não são programáveis por código, são pré-definidas. A escala de saída de banda larga da AEM é diferente da PLX e da Innovate: a ECU original Honda apenas consegue ler de 8.5 AFR a 13.66 AFR devido à amplitude de tensão (0.156 V = 8.5, 3.83 V = 13.66 AFR, 4.99 V = 20.5 AFR).

***PLX Devices:*** [http://www.plxdevices.com/index.htm](http://www.plxdevices.com/index.htm)
A PLX Devices aderiu à tendência e adicionou um produto compatível com o sensor LSU4: o M-250 ou M-300. Oferecem controladores com ou sem LCD, permitindo escolher a opção de preço adequada. Saídas de banda larga e banda estreita não programáveis por código. Têm também um website MUITO útil, com muita informação para ajudar na pesquisa e a compreender este tema. Obrigado PLX!

***DIY-WB:*** [http://wbo2.com/](http://wbo2.com/)
O projeto !TechEdge/DIY-WB é formado por um grupo de entusiastas muito talentosos que decidiram construir a sua própria banda larga, chocados com os preços das ofertas FJO/MoTec. Têm um produto no mercado há mais tempo do que qualquer outra empresa aqui apresentada. Disponibilizam kits que pode montar você mesmo, ou pagar para virem montados; vendem até APENAS a placa de circuito impresso para que compre os componentes por sua conta, para os entusiastas mais poupados. Focar-me-ei no !TechEdge v2.0 porque usa o sensor LSU4, enquanto a versão 1.x utiliza o sensor L1H1, que é mais caro. O 2.0 tem três entradas analógicas de registo integradas (0 a 5 V), três entradas de termopar (tipo K) e uma entrada de RPM. Adicionalmente, possui as saídas padrão de banda estreita e banda larga. Vem com um conjunto de registo e possivelmente saídas programáveis (ver informação aqui: [http://web.archive.org/web/20160420174111/http://wbo2.com:80/sw.htm](http://web.archive.org/web/20160420174111/http://wbo2.com:80/sw.htm)). A empresa também tem opções para saídas em ecrã LED. No geral, um produto muito robusto e bem pensado. Não irei recolher preços de momento. Os preços estão disponíveis nos URLs acima, exceto para a AEM. O AEM UEGO pode ser adquirido em [http://web.archive.org/web/20211208211907/http://ks-motorsports.com/](http://web.archive.org/web/20211208211907/http://ks-motorsports.com/), que recomendo consultar. No geral, estamos a falar de soluções abaixo dos 400 dólares e, se quiser montar o kit DIY-WB / !TechEdge, provavelmente gastará cerca de 250 a 300 dólares.

Aqui estão alguns links úteis:
- [Teoria da banda larga](http://www.g-speed.com/pbh/afr-o2.html)
- [Algumas notas de aplicação](http://www.plxdevices.com/appnotes.htm)
- [A perspetiva da Hondata sobre afinação com banda larga](http://hondata.com/techwidebandtuning.html)
- [LSU4 por ~US$40+Envio](https://www.parts.com/partlocator/index.cfm?action=selectCatalogYearMakeModel&make=0&siteid=213799&catalogid=1)

***Informação do Sensor Bosch LSU4/LSU4.2***
Este sensor é mais fácil de encontrar comercialmente do que o NTK e é usado em carros de produção como Porsche, Audi, VW, Subaru, Cadillac e Volvo. O sensor Bosch LSU 4.2 está marcado com os números 0 258 007 057/058 (vendido pela PLX Devices Inc.). O sensor Bosch LSU4 está marcado com os números 0 258 006 066.

***Calibração NTK L1H1***
Abaixo está uma tabela de Relação Ar/Combustível (A/F) e as respetivas tensões de saída

| **Relação A/F** | Tensão (volts) |
| :--- | :--- |
| 10.015625 | 0 |
| 10.015625 | 0.156 |
| 10.015625 | 0.312 |
| 10.015625 | 0.468 |
| 10.015625 | 0.624 |
| 10.015625 | 0.780 |
| 10.2890625 | 0.936 |
| 10.71875 | 1.092 |
| 11.109375 | 1.248 |
| 11.421875 | 1.404 |
| 11.8125 | 1.560 |
| 12.203125 | 1.716 |
| 12.59375 | 1.872 |
| 13.1015625 | 2.028 |
| 13.4921875 | 2.184 |
| 14.1171875 | 2.340 |
| 14.703125 | 2.496 |
| 15.71875 | 2.652 |
| 17.0078125 | 2.808 |
| 18.609375 | 2.964 |
| 18.9609375 | 3.120 |
| 18.9609375 | 3.276 |
| 18.9609375 | 3.432 |
| 18.9609375 | 3.588 |
| 18.9609375 | 3.744 |
| 18.9609375 | 3.900 |
| 18.9609375 | 4.056 |
| 18.9609375 | 4.212 |
| 18.9609375 | 4.368 |
| 18.9609375 | 4.524 |
| 18.9609375 | 4.680 |
| 18.9609375 | 4.836 |
| 18.9609375 | 4.992 |
