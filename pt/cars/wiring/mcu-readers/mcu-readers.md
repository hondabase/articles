---
summary: 'Todos os leitores de MCU descritos aqui tiram partido de uma falha de design dos MCUs OKI (e a falha de design está presente em todos os MCUs que vimos até à data).'
applies_to:
  obd: [0, 1, 2]
complexity: advanced
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
  - wiring
  - conversion
  - diagnostics
sources:
  - name: 'pgmfi.org wiki'
    title: 'Mcu Readers'
    url: /pgmfi/wiki/library/mcu-readers
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Mcu Readers

Todos os leitores de [MCU](/cars/rom/mcu) descritos aqui tiram partido de uma falha de design dos [MCU](/cars/rom/mcu)s OKI (e essa falha de design está presente em todos os [MCU](/cars/rom/mcu)s que vimos até à data). Os [MCU](/cars/rom/mcu)s podem utilizar tanto a [ROM](/cars/rom/rom) interna como a [ROM](/cars/rom/rom) externa para armazenamento da memória de programa, e um sinal GND ou +5V no [_EA](/cars/rom/ea) (EA prime - normalmente tem uma linha sobre o EA) é utilizado para controlar se é selecionada a memória de programa interna ou externa. *Os [MCU](/cars/rom/mcu)s OKI não fazem o [Latch](/cars/rom/latch) do estado do pino [_EA](/cars/rom/ea) no arranque - através de um truque engenhoso, a memória de código interna pode ser desmascarada após o [MCU](/cars/rom/mcu) ter começado a executar código. Todos os dumpers de [ROM](/cars/rom/rom) que tiram partido desta falha funcionam assim:

- Ligar manualmente um pino de I/O ao pino [_EA](/cars/rom/ea) do [MCU](/cars/rom/mcu). Utilizar um resistor pull-up/pull-down se necessário.
- Utilizar uma [ROM](/cars/rom/rom) que seja maior do que a [ROM](/cars/rom/rom) interna do [MCU](/cars/rom/mcu). Garantir que todas as linhas de endereço estão ligadas conforme necessário.
- Inicializar a porta série do [MCU](/cars/rom/mcu) para comunicação com o PC
- Saltar para cima da área de [ROM](/cars/rom/rom) mascarada (32k para `66207`, 48k para `66507`,...)
- Inverter o estado do [_EA](/cars/rom/ea) usando o pino de I/O
- Entrar num ciclo de atraso (delay loop) suficientemente longo para permitir que a [ROM](/cars/rom/rom) interna seja novamente mascarada na memória
- Copiar o conteúdo da [ROM](/cars/rom/rom) para fora através da porta série

Existem vários designs que foram testados:
- [Leitor OBD0 Oki83 C154](/cars/wiring/obd0-oki83c154-reader) - Adaptação de Blundar
- [Leitor OBD1 Oki66207-DIP64](/cars/wiring/obd1-oki66207-reader-dip64) - Design original `66207` do Doc para chips de encapsulamento DIP
- [Leitor OBD1 Oki66207-PLCC68](/cars/wiring/obd1-oki66207-reader-plcc68) - Adaptação do design de Doc por John de sol para 66207s SMT do mercado japonês ([JDM](/cars/sensors/jdm))
- [Leitor OBD2 Oki66507 Nico](/cars/wiring/obd2-oki66507-reader-nico) - Leitor original de Nico para o `66507`
- Leitor OBD2 Oki66507 Didier - Design revisto de Didier para um leitor de `66507`

Um leitor para outros chips exigiria o ajuste do encapsulamento físico da placa e do código para a velocidade do relógio (clock speed) e tamanho da [ROM](/cars/rom/rom).
