---
summary: 'COMUNICAÇÕES MULTIPROCESSADOR Em aplicações onde múltiplos controladores executam conjuntamente uma tarefa, o controlador mestre deve ser capaz de comunicar seletivamente com escravos individuais.'
tags: [tuning, rom, sensors, reference]
applies_to:
  brand: Honda
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Modo Multiprocessador'
    url: /pgmfi/wiki/library/multiprocessor-mode
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Modo Multiprocessador

COMUNICAÇÕES MULTIPROCESSADOR Em aplicações onde múltiplos controladores executam conjuntamente uma tarefa, o controlador mestre deve ser capaz de comunicar seletivamente com escravos individuais. Para fazer isso, o mestre primeiro identifica o escravo (ou escravos) alvo com um byte de endereço e, em seguida, transmite um bloco de dados. Os escravos alvo devem ser capazes de identificar o seu próprio endereço antes de receberem quaisquer bytes de dados. A porta série no 8051 fornece um modo de 9 bits para facilitar a comunicação multiprocessador. O 9.º bit permite que o controlador distinga entre bytes de endereço e bytes de dados. Neste modo, é recebido ou transmitido um total de 11 bits: um bit de início (0), 8 bits de dados (LSB primeiro), um 9.º bit programável e um bit de paragem (1). Veja a figura abaixo. O 9.º bit é definido como 1 para identificar bytes de endereço e definido como 0 para bytes de dados. Um fluxo de dados típico é visto abaixo: BYTE DE ENDEREÇO / BYTE DE DADOS / BYTE DE DADOS /. .. D8 e1 D8 e0 D8 e 0 Inicialmente, o escravo é configurado para receber apenas bytes de endereço. Assim que recebe o seu próprio endereço, o escravo reconfigura-se para receber dados. Na porta série do 8051, um byte de endereço interrompe todos os escravos para uma comparação de endereços. No 83C51FA, contudo, o Reconhecimento Automático de Endereço (Automatic Address Recognition) permite que o escravo endereçado seja o único interrompido; ou seja, a comparação de endereços ocorre em hardware, não em software. Com esta funcionalidade, o controlador mestre pode estabelecer comunicação com um ou mais escravos sem que todos os escravos tenham de responder à transmissão. ![mpcomm.jpg](mpcomm.jpg)
