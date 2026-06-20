---
summary: 'Dave diz: Bem, emprestando uma ideia de Nico-HRED/Doc usada nos 66Ks, aqui está um programa que deverá ler o conteúdo de um MCU 83C154.'
tags: [ecu, reference, tuning, rom, sensors, wiring, conversion, diagnostics, obd0]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD0 Oki83C154 Reader'
    url: /pgmfi/wiki/library/obd0-oki83c154-reader
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# OBD0 Oki83C154 Reader

Dave diz: Bem, emprestando uma ideia de Nico-HRED/Doc usada nos 66Ks, aqui está um programa que deverá ler o conteúdo de um [MCU](/cars/ecu/mcu) `83C154`. Assume que tem o [MCU](/cars/ecu/mcu) ligado a uma [EPROM](/cars/ecu/eprom) externa. O programa salta para `4100h` e depois faz o dump do conteúdo dos primeiros 16K de memória após alternar [_EA](/cars/tuning/ea) para mapear a [ROM](/cars/tuning/rom) interna em 0000-`4000h`. É necessária a utilização de uma placa de conversão série `MAX233`. Doc diz: para o hardware - só precisa de abrir a ponte (jumper) -EA e ligar a linha -EA do processador ao P1.7 do processador (porque o P1.7 é inicialmente LOW). No DOWNLOADER, configure a porta série para 4800, n,8,1. Nova funcionalidade no downloader: mostrar o dump da memória e definir a gama de memória a guardar. Adicionei isto porque as ECUs OBD1 enviam um byte de lixo pela porta série quando a [ECU](/cars/ecu/ecu) é ligada. As OBD0 não fazem isto. Portanto, primeiro dê uma vista de olhos no dump descarregado e decida o que quer guardar. Fiz o dump de uma PM5 (irei publicar nos rom dumps) - parece estranho, mas tem pelo menos uma tabela de ignição e combustível. Por isso, vocês, gurus do OBD0, podem dar uma olhadela. Acho que as tabelas são mesmo pequenas? Até breve, Doc...

| **Anexo:** | **Modificar:** | **Tamanho:** | **Data:** | **Autor:** | **Comentário:** | | :--- | :--- | :--- | :--- | :--- | :--- | | ![](/pgmfi/wiki/assets/icn/else.gif) [Read83C154\\_12mhz.bin](Read83C154_12mhz.bin) | mod | 16711 | 05 Mar 2004 - 17:49 | blundar | BIN de código para fazer dump do [MCU](/cars/ecu/mcu) | | ![](/pgmfi/wiki/assets/icn/else.gif) [read83c154\\_12mhz.asm](read83c154_12mhz.asm) | mod | 2733 | 05 Mar 2004 - 17:49 | blundar | código assembly do DASM | | ![](/pgmfi/wiki/assets/icn/exe.gif) [downloader.exe](downloader.exe) | mod | 522752 | 05 Mar 2004 - 17:49 | blundar | Aplicação Downloader Win32 | | *Library. OBD0Oki83C154Reader movido de Library. OBD0Oki83C154ReaderBlundar em 05 Mar 2004 - 17:54 por Home.blundar

* - [devolver à localização anterior](https://web.archive.org/web/http://www.pgmfi.org/twiki/bin/rename/Library/OBD0Oki83C154Reader?newweb=Library&newtopic=OBD0Oki83C154ReaderBlundar&confirm=on "Clique para mover o tópico de volta à localização anterior, com a opção de alterar referências.") | | :--- |
