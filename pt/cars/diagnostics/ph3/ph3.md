---
summary: 'A ECU OBD0 B20A do Accord 88-89 utiliza um distribuidor com Avanço Eletrónico (Electronic Advance). Possui uma ROM 27C256 Externa e é baseada no chip oki 80C154. Esta ECU é muito semelhante à ECU PK2 do Prelude 88-91.'
applies_to:
  obd: [0, 1, 2]
  brand: Honda
complexity: advanced
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: PH3
    url: /pgmfi/wiki/library/ph3
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# PH3

A [ECU](/cars/ecu/ecu) OBD-0 B20A do Accord 88-89 utiliza um distribuidor de Avanço Eletrónico (Electronic Advance). Tem uma [ROM](/cars/rom/rom) `27C256` externa e é baseada no chip OKI `80C154`.
Esta [ECU](/cars/ecu/ecu) é muito semelhante à [ECU](/cars/ecu/ecu) PK2 do Prelude 88-91. No entanto, tem o segundo sensor de O2 desativado através de BR8.

O B20A do Accord 86-87 OBD-0 é baseado no OKI 80C514, mas tem uma ROM 27C128.
Não possui um processador de salvaguarda (backup processor), mas parece utilizar 2 processadores OKI em alternativa.
Esta [ECU](/cars/ecu/ecu) tem 2 LEDs de diagnóstico. Note que as [ECU](/cars/ecu/ecu)s PH3 e PK2 mais recentes partilham quase a mesma placa, sendo 99% semelhantes, observando-se apenas ligeiras diferenças entre elas.
São tão semelhantes que até ao momento podem inclusivamente partilhar o mesmo programa.

---

Publiquei o grande plano das Opções (Options Close-up) para as [ECU](/cars/ecu/ecu)s PH3-0732 e PH3-0632 do Accord B20A 88-89. A 0732 é supostamente de um carro automático e a 0632 de um manual. Não sei se estas opções estão relacionadas com o tipo de transmissão ou com emissões. A [ECU](/cars/ecu/ecu) PK2 manual tem a mesma configuração de opções que esta [ECU](/cars/ecu/ecu) Automática, por isso ainda não tenho a certeza do que fazem. Existe também um grande plano do jumper BR8. Este jumper parece ser o que desativa a entrada do sensor de O2 B na placa da PH3. Está ligado diretamente ao pino do Sensor. A PK2 partilha quase as mesmas Placas que a PH3, mas tem este jumper vazio/em branco (ver secção da [ECU](/cars/ecu/ecu) PK2). Carotman | **Anexo:** | **Modificar:** | **Tamanho:** | **Data:** | **Quem:** | **Comentário:** | | :--- | :--- | :--- | :--- | :--- | :--- | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [ph3\\_0732.jpg](ph3_0732.jpg) | mod | 212615 | 30 Jan 2006 - 07:01 | carotman | ECU PH3 Accord B20A 88-89 | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [ph3\\_043.jpg](ph3_043.jpg) | mod | 341522 | 30 Jan 2006 - 07:08 | carotman | ECU PH3 Accord B20A 86-87 | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [ph3-0632\\_manual\\_options.jpg](ph3-0632_manual_options.jpg) | mod | 1056389 | 07 Apr 2006 - 02:44 | carotman | ECU Manual PH3-0632 (Grande plano de Opções) | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [ph3-0632\\_manual.jpg](ph3-0632_manual.jpg) | mod | 1054856 | 07 Apr 2006 - 02:45 | carotman | ECU Accord PH3-0632 (Manual) | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [ph3-0732\\_auto\\_options.jpg](ph3-0732_auto_options.jpg) | mod | 1059425 | 07 Apr 2006 - 02:46 | carotman | ECU Automática PH3-0732 (Grande plano de Opções) | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [ph3-0732\\_auto.jpg](ph3-0732_auto.jpg) | mod | 1082686 | 07 Apr 2006 - 02:49 | carotman | ECU Automática PH3-0732 | | ![](/pgmfi/wiki/assets/icn/bmp.gif) [BR8-PH3.jpg](BR8-PH3.jpg) | mod | 1061228 | 07 Apr 2006 - 03:03 | carotman | Jumper BR8 que parece anular a entrada B do sensor de O2 |
