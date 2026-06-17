---
summary: 'Guia avançado para construir um leitor de hardware para extrair dados da ROM Interna de processadores PLCC68 Oki 66207 encontrados em ECUs Honda OBD1.'
tags: [hardware, education, ecu, tuning, rom, sensors, reference, wiring, conversion]
applies_to:
  obd: [1]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD1 Oki66207 Reader-PLCC68'
    url: /pgmfi/wiki/library/obd1-oki66207-reader-plcc68
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD1 Oki66207 Reader-PLCC68

Após fazer a modificação do Doc para ler a ROM de origem de uma ECU P30 australiana com o `66207` numa configuração DIP de 64 pinos, comecei a pensar que em algum lugar da web tinha visto uma [ECU](/cars/ecu/ecu) [JDM](/cars/sensors/jdm) com o socket para a ROM externa vazio, sem o `74HC373`. Tenho em minha posse uma P30 [JDM](/cars/sensors/jdm) com Eprom externa e perguntei-me se conseguiria ler esta [ECU](/cars/ecu/ecu) usando o [método do Doc](/cars/wiring/obd1-oki66207-reader-dip64). Depois de converter tudo para funcionar com o `66207` numa configuração PLCC de 68 pinos, consegui ler o conteúdo da [MCU](/cars/rom/mcu) da mesma forma que se faria na ECU DIP de 64 pinos. De qualquer forma, para fazer isto basta seguir o [método do Doc](/cars/wiring/obd1-oki66207-reader-dip64), MAS precisa de alterar algumas coisas: Citação: ([método do Doc](/cars/wiring/obd1-oki66207-reader-dip64) com alterações) Precisamos de modificar um pouco a [ECU](/cars/ecu/ecu) para termos um bom leitor de `66207`, eis uma breve descrição:

- Se a sua [ECU](/cars/ecu/ecu) não estiver alterada (chipped), precisa de adicionar o `74HC373`, o socket da [EPROM](/cars/rom/eprom) e a resistência de 1k Ohm (`R54`).
- Ligue um fio do pino 17 (A15) do `66207` ao Pino 1 (A15) da Eprom. NÃO COLOQUE O PINO 1 DA [EPROM](/cars/rom/eprom) NO SOCKET! LIGUE APENAS O FIO DIRETAMENTE A ELE.
- Ligue um fio do Pino 21 (P2.2) do `66207` ao Pino 29 (-EA) do `66207`.
- Corte a pista na [PCB](/cars/wiring/pcb) a partir do pino 29 (ver foto `66207`-1.bmp) e substitua-a por uma resistência de 1k Ohm.
- Coloque a Eprom 27C512, programada com o meu programa "ROMREADER".
- Ligue o seu PC através de um conversor RS232<->TTL à [ECU](/cars/ecu/ecu) (consulte mais informações na secção de datalogging).

Vamos ler um `66207`:
- Desligue a sua [ECU](/cars/ecu/ecu), ou deixe-a desligada.
- Inicie o programa no PC: DOWNLOADER
- se a indicação de Endereço (Address) não for 0000, clique em RESET.
- Ligue a sua [ECU](/cars/ecu/ecu)
- Após cerca de 1 segundo, deverá ver o contador de endereços a correr
- após quase um minuto (nunca o parei), o contador de endereços deverá mostrar 8001
- agora clique em SAVE para guardar a sua ROM.

Se algo não funcionar, repita o procedimento mas não se esqueça de clicar em RESET. Divirta-se com o seu próprio leitor de `66207`. Doc. É tudo. Não se esqueça de soldar a pista que cortou quando terminar para ativar a ROM externa. - Imagem em alta resolução da configuração geral: 
 ![DSC02697.JPG](DSC02697.JPG)

| **Anexo:** | **Modificar:** | **Tamanho:** | **Data:** | **Quem:** | **Comentário:** |
| :--- | :--- | :--- | :--- | :--- | :--- |
| ![](/pgmfi/wiki/assets/icn/zip.gif) [66207plcc.zip](66207plcc.zip) | mod | 174118 | 05 Mar 2004 - 18:05 | blundar | Imagens das modificações necessárias |
| ![](/pgmfi/wiki/assets/icn/bmp.gif) [DSC02697.JPG](DSC02697.JPG) | mod | 1838687 | 08 Jun 2006 - 00:20 | synoptic | Alta resolução da configuração geral |
