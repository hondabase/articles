---
summary: 'Especificação técnica do protocolo customizado de datalogging e programação em tempo real (RTP) de alta velocidade, baseado em fluxo (stream), para ECUs Honda.'
applies_to:
  obd: [1]
complexity: advanced
tags:
  - datalogging
  - serial
  - protocol
sources:
  - name: 'pgmfi.org wiki'
    title: 'Proposed Datalogging Protocol'
    url: /pgmfi/wiki/library/proposed-datalogging-protocol
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Protocolo de Datalogging & RTP Proposto

Este documento define a especificação para um protocolo de comunicação serial customizado e baseado em fluxo (stream), projetado para substituir os manipuladores de interrupção serial legados (polled) nas ECUs Honda OBD0 e OBD1.

O protocolo visa fornecer uma ligação multiplataforma de alta eficiência que suporta tanto datalogging de alta velocidade como emulação de Programação em Tempo Real (RTP).

## Princípios de Design Fundamentais

1. **Transmissão Contínua (Non-Polling)**: Em vez de o PC solicitar constantemente (polling) dados, a ECU envia continuamente pacotes padrão de datalogging em alta velocidade. Isto minimiza a latência serial e o processamento (overhead) da CPU na ECU.
2. **Polling Sob Demanda**: Enquanto a telemetria principal dos sensores é transmitida continuamente, o PC pode injetar pacotes de comandos curtos para consultar localizações de memória arbitrárias ou registos da ROM.
3. **Consulta do Espaço de Memória**: Suporta a leitura de qualquer localização dentro do espaço de endereçamento de 16 bits (RAM e ROM).
4. **Validação de Dados**: Utiliza verificação de checksum e verificação de complemento (`CPL`) em operações de escrita para garantir a integridade da comunicação antes de escrever na memória de emulação (RTP).
5. **Escrita em Bloco (Bulk Writing)**: Suporta um modo de escrita em bloco com interrupções bloqueadas para reflash rápido da ROM.

---

## Fluxo de Trabalho Técnico para Programação em Tempo Real (RTP)

Para garantir que falhas seriais aleatórias não escrevam valores corrompidos nas tabelas do motor em funcionamento, é utilizada uma sequência de escrita com validação em duas etapas:

1. **Transferência de Dados**: O PC envia a carga útil (1 ou 2 bytes) para a ECU usando um pacote `Byte Write` (`0x10`) ou `Word Write` (`0x11`).
2. **Buffer na ECU**: A ECU armazena os dados num buffer de memória temporário ("byte storage" ou "word storage") e envia de volta para o PC um pacote de resposta `Destination Request` (`0xA0` / `0xA1`) contendo os dados recebidos.
3. **Verificação**: O PC recebe a solicitação de destino e verifica se os dados ecoados correspondem ao que foi enviado.
4. **Execução**:
   * Se estiverem corretos, o PC envia um pacote `Destination` (`0x20` / `0x21` / `0x22` / `0x23`) especificando o endereço de memória de destino final.
   * Ao receber o pacote de destino, a ECU move os dados do buffer para o endereço de destino final no espaço RAM/ROM.
   * Se a verificação falhar, o PC descarta o buffer e reinicia a partir do Passo 1.

---

## Pacotes de Comando PC para ECU

Os pacotes enviados do PC para a ECU consistem em 5 bytes. Um byte de checksum é calculado como a soma de 8 bits dos bytes de endereço ou dados.

| Nome do Comando | Byte 1 (ID) | Byte 2 | Byte 3 | Byte 4 | Byte 5 | Função e Comportamento da Resposta |
| :--- | :---: | :---: | :---: | :---: | :---: | :--- |
| **Byte RAM Read** | `0x02` | `Addr (Hi)` | `Addr (Lo)` | `CS` | `0x02` | Lê um byte da RAM. Responde com o pacote `0x82`. |
| **Word RAM Read** | `0x03` | `Addr (Hi)` | `Addr (Lo)` | `CS` | `0x03` | Lê um word da RAM. Responde com o pacote `0x83`. |
| **Byte ROM Read** | `0x04` | `Addr (Hi)` | `Addr (Lo)` | `CS` | `0x04` | Lê um byte da ROM. Responde com o pacote `0x84`. |
| **Word ROM Read** | `0x05` | `Addr (Hi)` | `Addr (Lo)` | `CS` | `0x05` | Lê um word da ROM. Responde com o pacote `0x85`. |
| **Byte Write** | `0x10` | `Data` | `CPL Data` | `CS` | `0x10` | Envia um byte da RAM para o armazenamento temporário. Responde com `0xA0`. |
| **Word Write** | `0x11` | `Data 1` | `Data 2` | `CS` | `0x11` | Envia um word da RAM para o armazenamento temporário. Responde com `0xA1`. |
| **8-bit RAM Dest** | `0x20` | `Addr` | `Addr` | `CS` | `0x20` | Escreve o byte em buffer num endereço RAM de 8 bits. |
| **16-bit RAM Dest** | `0x21` | `Addr (Hi)` | `Addr (Lo)` | `CS` | `0x21` | Escreve o byte em buffer num endereço RAM de 16 bits. |
| **16-bit ROM Dest** | `0x22` | `Addr (Hi)` | `Addr (Lo)` | `CS` | `0x22` | Escreve o byte em buffer num endereço ROM de 16 bits (RTP). |
| **16-bit ROM Word Dest** | `0x23` | `Addr (Hi)` | `Addr (Lo)` | `CS` | `0x23` | Escreve o word em buffer num endereço ROM de 16 bits (RTP). |
| **Bulk Write Address** | `0x80` | `Addr (Hi)` | `Addr (Lo)` | `0x00` | `0x80` | Define o ponteiro de dados e bloqueia a ECU na interrupção serial. |
| **Bulk Write Start** | `0x81` | `Length` | `Data...` | - | - | Escreve `Length` bytes na ROM a partir do ponteiro de dados. |

*Nota: `CS` é o byte de checksum de 8 bits, e `CPL` é o complemento bit a bit (~).*

---

## Pacotes de Resposta ECU para PC

Os pacotes de resposta da ECU têm 5 bytes de comprimento, com o primeiro byte a atuar como o identificador do tipo de pacote.

| Tipo de Pacote | Byte 1 (ID) | Byte 2 | Byte 3 | Byte 4 | Byte 5 | Descrição / Payload |
| :--- | :---: | :---: | :---: | :---: | :---: | :--- |
| **Continuous Telemetry** | `0x01`–`0x7F` | `Data 1` | `Data 2` | `Data 3` | `CS` | Valores dos sensores transmitidos em tempo real. |
| **Bulk Write Addr Reply** | `0x80` | `Addr (Hi)` | `Addr (Lo)` | `0x00` | `0x00` | Confirma o endereço de destino para escrita em bloco. |
| **Bulk Write Verification** | `0x81` | `CS` | `0x00` | `0x00` | `0x00` | Confirma a integridade do bloco escrito em bloco. |
| **Read RAM Byte Reply** | `0x82` | `Data` | `CPL Data` | `Data` | `CS` | Retorna o valor de 8 bits solicitado da RAM. |
| **Read RAM Word Reply** | `0x83` | `Data 1` | `Data 2` | `CS (D1)` | `CS (D2)` | Retorna o valor de 16 bits solicitado da RAM. |
| **Read ROM Byte Reply** | `0x84` | `Data` | `CPL Data` | `Data` | `CS` | Retorna o valor de 8 bits solicitado da ROM. |
| **Read ROM Word Reply** | `0x85` | `Data 1` | `Data 2` | `CS (D1)` | `CS (D2)` | Retorna o valor de 16 bits solicitado da ROM. |
| **Byte Dest Request** | `0xA0` | `Data` | `CPL Data` | `CS` | `Data` | Confirma que o byte está no buffer, aguardando destino. |
| **Word Dest Request** | `0xA1` | `Data 1` | `Data 2` | `CS (D1)` | `CS (D2)` | Confirma que o word está no buffer, aguardando destino. |
| **Negative Ack (NAK)** | `0xFF` | `0x00` | `0xFF` | `0x00` | `0xFF` | Enviado se for recebido um pacote inválido ou corrompido. |
