---
summary: 'Em primeiro lugar, gostaria de agradecer novamente ao NicoHRED pela informação que publicou no fórum geral sobre a "66P507 Readout".'
applies_to:
  obd: [1]
complexity: advanced
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - wiring
  - conversion
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD1 Oki66207 Reader-DIP64'
    url: /pgmfi/wiki/library/obd1-oki66207-reader-dip64
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Leitor OBD1 Oki66207-DIP64

Em primeiro lugar, gostaria de agradecer novamente ao Nico-HRED pela informação que publicou no fórum geral sobre a "Leitura da `66P507`" (66P507 Readout). Adaptei a ideia e simplifiquei-a, para que qualquer um de nós possa agora ler o conteúdo da sua `66207`. O meu leitor é um pouco diferente do que ele publicou. Preciso de uma [ECU](/cars/ecu/ecu) com uma `66207`, uma 27C512 (EPROM), uma resistência de 1 k, dois fios e um conversor RS232<->TTL. A maioria de vós já terá isto; caso contrário, as peças são comuns e baratas. Precisamos de modificar um pouco a [ECU](/cars/ecu/ecu) para termos um bom leitor de `66207`, aqui fica uma breve descrição:

- Se a sua [ECU](/cars/ecu/ecu) não for "chippada" (com socket), precisa de adicionar o `74HC373`, o socket da EPROM e a resistência de 1kOhm (`R54`).
- Ligue um fio do pino 16 (A15) do `66207` ao pino 1 (A15) da EPROM.

BUT DON'T PUT THE PIN 1 OF THE [EPROM](/cars/rom/eprom) IN THE SOCKET! JUST CONNECT THE WIRE TO IT. - Ligue um fio do pino 19 (P2.2) do `66207` ao pino 27 (-EA) do `66207`.
- Remova o jumper `J1` e substitua-o por uma resistência de 1kOhm.
- Insira a EPROM 27C512, gravada com o meu programa "ROMREADER".
- Ligue o seu PC à [ECU](/cars/ecu/ecu) através de um conversor RS232<->TTL (consulte [Data Logging](/cars/diagnostics/data-logging) para mais informações).

Vamos ler uma `66207`:
- Desligue a sua [ECU](/cars/ecu/ecu), ou deixe-a desligada.
- Inicie o programa no PC: DOWNLOADER
- Se a indicação do endereço (Address display) não for 0000, clique em RESET.
- Ligue a sua [ECU](/cars/ecu/ecu)
- Após cerca de 1 segundo, deverá ver o contador de endereços a correr.
- Após quase um minuto (nunca cronometrei), o contador de endereços deverá mostrar 8001.
- Agora clique em SAVE para guardar a sua ROM.

Se algo não funcionar, repita o procedimento, mas não se esqueça de clicar em RESET. Divirta-se com o seu próprio leitor de `66207`. Doc 
<figure>
    <img src="66207_romreader.jpg" alt="">
</figure>
