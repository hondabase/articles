---
summary: 'Procedimento preliminar arquivado de instalação para ligar o Easy-RTP v1.0 a ECUs OBD1.'
tags: [rtp, ecu, hardware, chipping]
applies_to:
  ecus: [P28, P30]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Easy Rtp Install'
    url: /pgmfi/wiki/library/easy-rtp-install
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Instalação do Easy-RTP v1.0 OBD1

Estas instruções arquivadas descrevem a instalação de uma placa Easy-RTP v1.0 concluída numa ECU OBD1 P28, interrompendo o circuito de write-enable da CPU e ligando a placa RTP aos sinais de endereço e de escrita necessários.

> [!WARNING]
> A fonte rotula explicitamente estas instruções como preliminares e pede aos leitores para as confirmarem. O procedimento corta uma pista da placa da ECU e requer soldadura direta aos pinos do circuito integrado (IC). Verifique todos os sinais e pinos em relação à ECU de destino antes de ligar a alimentação.

Construa o módulo primeiro usando o [guia de montagem do Easy-RTP v1.0](/cars/rom/easy-rtp-v10). A fonte assume que as placas OBD1 são semelhantes, mas apenas mostra uma instalação numa P28 e lista separadamente pinos diferentes para uma P30-900 JDM de montagem em superfície (surface-mount).

## Ligação removível

A instalação interrompe o sinal de `write-enable` (`WE`) do MCU. A fonte utiliza uma ficha removível entre a ECU e a placa RTP, para que uma pequena ficha de jumper possa ligar novamente o circuito original quando a placa RTP for removida.

Use fio de secção fina (small-gauge) porque os pontos de soldadura são pequenos. A fonte sugere fio de wire-wrap e assinala que um conector em ângulo reto (right-angle header) na placa RTP deixaria mais folga para a caixa da ECU.

![Fichas removíveis e pista cortada do Easy-RTP](rtp1.jpg)
*Foto arquivada das ligações removíveis; a pista cortada é visível em segundo plano.*

## Procedimento de instalação na P28

1. Localize e corte a pista de `WE` do MCU mostrada na imagem marcada arquivada.

 ![Localização do corte da pista de write-enable da ECU OBD1](doc_RTP_OBD1_Cut_here.jpg)
 *Imagem arquivada marcando o corte da pista de write-enable.*

2. Ligue o fio `A15` da placa RTP ao Pino 16 do MCU. A fonte refere que esta linha de endereço do MCU não é usada para outros fins e serve para endereçar a imagem da ROM gravável.
3. Ligue o lado do MCU da pista de `WE` cortada, Pino 25 do MCU, ao `WE in` na placa RTP. A fonte recomenda estanhar tanto o pino do IC como o fio antes de soldar.

 ![Ligações do Easy-RTP A15 e do write-enable do lado do MCU](rtp2.jpg)
 *Foto arquivada das ligações de A15 e de WE do lado do MCU.*

4. Ligue o outro lado do circuito de write-enable cortado ao Pino 38 do M82C55A. A fonte refere que isto permite à placa RTP ativar as escritas na NVSRAM apenas quando A15 está em nível lógico alto (high).

 ![Ligação do Easy-RTP no Pino 38 do M82C55A](rtp3.jpg)
 *Foto arquivada da ligação ao lado oposto do circuito cortado.*

5. Inspecione todas as ligações e confirme que a pista cortada está isolada antes de testar.

 ![Instalação concluída do Easy-RTP](rtp4.jpg)
 *Foto arquivada da instalação concluída.*

## Nota sobre os pinos JDM de montagem em superfície

A fonte indica estes pinos alternativos para uma P30-900 JDM e refere que muito provavelmente se aplicam a outras ECUs JDM. Essa compatibilidade mais alargada não foi confirmada.

| Sinal | Pino do dispositivo de montagem em superfície | Pino do dispositivo DIP usado acima |
| --- | ---: | ---: |
| A15 no M66207 | 17 | 16 |
| WE/WR no M66207 | 27 | 25 |
| WE/WR no 82C55 | 40 | 38 |

## Restaurar o caminho original do write-enable

A fonte encaminha as duas metades do circuito de write-enable cortado para as ligações 1 e 3 da placa RTP. Quando o módulo RTP está ausente, a ficha simuladora (dummy plug) proposta simplesmente junta esses dois fios para que uma ROM padrão possa ser usada.

> [!WARNING]
> Confirme a numeração e a continuidade dos conectores na instalação real. Um jumper incorretamente ligado pode ligar sinais não relacionados ou deixar o caminho original de write-enable aberto.

## Ligação para Datalogging

Após a instalação do hardware RTP, a página arquivada refere que é necessário um conversor RS232-para-TTL para a comunicação entre a ECU e o PC. Consulte a [visão geral de datalogging de ECUs Honda](/cars/diagnostics/data-logging) e o [guia de comunicação série](/cars/tuning/serial-communication) para o contexto histórico da interface.

## Relacionado

- [Guia de construção e instalação DIY do Easy-RTP v1.0](/cars/rom/easy-rtp-v10)
- [Visão geral de datalogging de ECUs Honda](/cars/diagnostics/data-logging)
- [Comunicação série OBD1](/cars/tuning/serial-communication)
