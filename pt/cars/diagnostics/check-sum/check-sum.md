---
summary: 'Um Checksum é uma forma muito básica de verificação de erros. É calculado somando os valores de uma ROM, sem qualquer tipo de verificação de transporte (carry) ou estouro (overflow).'
applies_to:
  obd: [0, 1]
  brand: Honda
complexity: beginner
tags:
  - hardware
  - education
  - ecu
  - tuning
  - rom
  - sensors
  - reference
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: 'Check Sum'
    url: /pgmfi/wiki/library/check-sum
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Check Sum

Um Checksum (soma de verificação) é uma forma muito básica de verificação de erros. É calculado somando os valores de uma [ROM](/cars/rom/rom), sem qualquer tipo de verificação de transporte (carry) ou estouro (overflow). Os checksums podem variar em tamanho — checksums de 8 bits, 16 bits e 32 bits são todos comuns. As [ECU](/cars/ecu/ecu)s Honda [OBD0](/cars/rom/obd0) e [OBD1](/cars/wiring/obd1) utilizam exclusivamente checksums de 8 bits, ou seja, checksums de 0 a 255 em decimal (00-FF em hexadecimal). Existe um programa chamado [check8](http://www.keil.com/download/files/check8.zip) (também disponível em anexo nesta página) que consegue calcular checksums de 8 bits. Pode atualizar a ROM para que o checksum permaneça 00 mesmo após editá-la. Eis como fazer (utilizando o [Win Hex](/cars/rom/win-hex) neste exemplo, embora possa utilizar o programa disponibilizado abaixo, mas apenas para encontrar o checksum, não para editar a [ROM](/cars/rom/rom)): Abra o [Win Hex](/cars/rom/win-hex) e selecione o Menu Tools (Ferramentas) -> Calculate Hash (Calcular Hash) (Selecione 8 bits). Aponte o número apresentado. Este é o checksum atual. Abra a Calculadora do Windows (Iniciar -> Executar -> Calc e prima enter). Ver -> Científica. Selecione o Modo Hex (ou prima F5). Faça o seguinte: FF - checksum_atual (FF - AB, por exemplo). O número resultante deve ser escrito numa posição de memória, mais perto do fim (fim do ficheiro/ROM), onde não exista código e onde o valor FF já esteja presente. Exemplo: (FF - AB = 54) imaginemos que vou à posição de memória 7FFF e o valor é FF. Substituo FF por 54. Se não tiver um endereço com um valor FF livre, mas sim outro valor (digamos 00), use 00 na calculadora em alternativa (00 - AB) e substitua o 00 livre pelo resultado.

| **Anexo:** | **Modificar:** | **Tamanho:** | **Data:** | **Quem:** | **Comentário:** | | :--- | :--- | :--- | :--- | :--- | :--- | | ![](/pgmfi/wiki/assets/icn/exe.gif) [Check8.exe](Check8.exe) | mod | 10308 | 05 Mar 2004 - 18:29 | blundar | Utilitário de checksum de 8 bits da Keil |
