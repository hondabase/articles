---
summary: 'A Honda utiliza um interruptor high side de 5 pinos em muitas das suas ECUs OBD1 e OBD2 para controlar solenoides, como os de transmissão automática e solenoides VTEC.'
applies_to:
  obd: [1, 2]
  brand: Honda
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
sources:
  - name: 'pgmfi.org wiki'
    title: '515X High Side Switch'
    url: /pgmfi/wiki/library/515x-high-side-switch
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Interruptor High Side 515X

A Honda utiliza um interruptor high side de 5 pinos em muitas das suas [ECU](/cars/ecu/ecu)s [OBD1](/cars/wiring/obd1) e [OBD2](/cars/wiring/obd2) para controlar solenoides, tais como os de transmissão automática e solenoides VTEC. A Allegro / Sanken é o fabricante original (OEM) desta peça. Sabe-se que as seguintes peças funcionam: SK-5050S (original - geralmente em placas 1720)
 SK-5151S (versão de corrente mais elevada do 5050 - geralmente em placas 11F0/1980)
 SK-5154S (versão de corrente mais elevada do 5151 - geralmente em placas [OBD2](/cars/wiring/obd2))
 SI-5151S (alteração de referência da SK-5151S)
 SI-5154S (alteração de referência da SK-5154S)
 SI-5151SG (alteração de referência da SI-5151S)
 SI-5154SG (alteração de referência da SI-5154S)
 Estas peças são frequentemente bastante difíceis de obter, devido ao facto de a Allegro não vender menos de 500 unidades a $1.50 cada e de poucos distribuidores de eletrónica as terem em stock. Procure por compras conjuntas (groupbuys) periódicas no fórum. Existem [relatos]() de uma peça da [International Rectifier]() que serve de substituta. Novo link do fórum: [Substituição para SI-5151S](/pgmfi/forum/topic.php?id=181) (Por favor, inicie sessão para ver as imagens no fórum) Edite isto se souber mais. Testei um par de ir6220 numa P13 que se sabia estar boa. Funcionou perfeitamente! Aceda a [http://web.archive.org/web/20260612163410/https://www.digikey.com/](http://web.archive.org/web/20260612163410/https://www.digikey.com/) e escreva IR6220-ND na pesquisa de peças, custam $4.63/unidade. Tudo o que precisa de fazer é mover a perna #3 para a posição #5 na placa e mover o pino #5 para a posição #3 na placa. É realmente fácil de fazer... basta usar manga termoretrátil ou isolamento na perna 3 para evitar o contacto entre pernas... consulte este post para ver uma imagem: [https://web.archive.org/web/http://forum.pgmfi.org/viewtopic.php?t=181](/pgmfi/forum/topic.php?id=181) uma imagem vale mais do que mil palavras ![dsc00595.jpg](dsc00595.jpg) (Essa seria a substituição real para a ir6220: IPS521) termos de pesquisa: SK5050 SK5151 SK-5050 SK-5151
