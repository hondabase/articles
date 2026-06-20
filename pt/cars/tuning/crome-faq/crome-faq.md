---
summary: 'Perguntas frequentes sobre o Crome, um software popular de edição e afinação de ROMs para ECUs OBD1 da Honda.'
tags: [tuning, software]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Crome FAQ'
    url: /pgmfi/wiki/library/crome-faq
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# FAQ de Afinação de ROMs com Crome

O Crome é uma suite de software de edição e afinação de ROMs popular e económica, concebida para Unidades de Controlo do Motor (ECUs) OBD1 da Honda. Permite aos entusiastas modificar tabelas de combustível, mapas de ponto de ignição e configurar funcionalidades avançadas em ECUs preparadas com suporte (socketed). Esta FAQ aborda questões comuns de configuração, requisitos de hardware e dicas de resolução de problemas para a afinação com Crome.

## Perguntas Gerais

### Porque é que o Crome está protegido por palavra-passe?

O Crome é um software gratuito tornado possível pelo trabalho árduo de muitos contribuidores. Para garantir que os utilizadores têm conhecimento da origem do software e dos seus contribuidores, o criador (John Cui) protegeu o instalador com palavra-passe.

### Como encontro a palavra-passe do instalador do Crome?

A palavra-passe é fácil de encontrar com uma pequena pesquisa. Encontrá-la serve como um exercício básico para os iniciantes aprenderem mais sobre o ecossistema Crome e demonstrarem apreço pelos anos de desenvolvimento por trás dele.

## Requisitos de Hardware

### Que hardware é necessário para começar a afinar com o Crome?

Para começar a fazer afinação e datalogging com o Crome, necessitará do seguinte hardware:

- **Portátil para Afinação:** Um computador com Windows (idealmente com um processador e RAM razoáveis). Um portátil lento irá criar um estrangulamento nos tempos de resposta do datalogging.
- **Sensor de Oxigénio de Banda Larga (Wideband O2):** Um sensor de oxigénio de banda larga com uma tensão de saída analógica linear (ex: Innovate, PLX ou TechEdge) é crítico se quiser fazer datalogging de relações ar-combustível através da ECU.
- **Gravador de Chips EEPROM:** Um programador de hardware (como o Moates BURN1/BURN2 ou um programador Willem) para gravar ficheiros nos seus chips de ROM. Note que os programadores Willem normalmente requerem uma porta paralela (LPT), algo que a maioria dos portáteis modernos não possui.
- **Emulador de Hardware (Opcional):** Um emulador como o Moates Ostrich permite a afinação em tempo real (RTT), carregando mapas diretamente para a ECU sem necessidade de gravar chips constantemente.
- **Cabo de Datalogging:** Um cabo adaptador de série USB para TTL para ligar o conector de datalogging de 4 pinos da ECU (`CN2`) ao portátil. A Moates e outros fornecedores de afinação disponibilizam cabos USB plug-and-play.
- **Kit para Modificação da ECU (Chipping Kit):** Para preparar uma ECU OBD1 com suporte, precisa de:
 - Suporte DIP torneado de 28 pinos
 - Suporte ZIF de 28 pinos
 - Conector de datalogging `CN2` de 4 pinos
 - Dois condensadores de disco cerâmicos de 0.1µF
 - Resistência de 1k Ohm
 - Chip latch `74HC373`

Para obter um guia passo a passo sobre a instalação de opções de hardware, consulte o [guia sobre como adicionar funcionalidades adicionais no Crome](/cars/tuning/howto-add-extra-features-in-crome).

## Compatibilidade de ROM e Configuração de Plugins

### Com qual ROM original devo começar para os plugins de ITB ou Boost (Sobrealimentação)?

Deve começar com uma ROM original JDM P30 "203" ou qualquer ROM dela derivada (como uma ROM original JDM P08 "237").

### Onde posso descarregar ficheiros de ROM originais da Honda?

Pode encontrar ROMs originais e definições na [biblioteca de Códigos de Definição de ECU](/cars/ecu/ecu-definition-codes).

### Porque é que a minha ECU mostra a luz avisadora do motor (CEL) continuamente acesa após editar uma ROM original?

Se obtiver uma Check Engine Light (CEL) continuamente acesa após gravar uma nova ROM, verifique se:
1. Removeu a rotina de verificação de integridade (checksum) da ROM no Crome.
2. Desativou quaisquer funcionalidades de hardware que não estejam fisicamente presentes na sua ECU (como o sensor de detonação, corte de purga, sensor barométrico ou circuito de teste de injetores).

### O datalogging falha após instalar o plugin de datalogging. O que devo verificar?

Certifique-se de que desativou a rotina de checksum na sua ROM e que selecionou a porta COM correta nas definições do Crome.

### Porque é que a taxa de amostragem do meu datalogging é muito lenta?

A velocidade de datalogging é altamente dependente das capacidades do hardware do seu PC e da qualidade do cabo de série RS232 para TTL. Consulte o [guia de resolução de problemas de comunicação série](/cars/tuning/serial-communication) para obter mais informações.

### Os plugins do Crome não funcionam com a minha ROM P28. O que devo fazer?

A maioria dos plugins do Crome é desenvolvida para suportar a base de código JDM P30. Se estiver a afinar uma ECU P28, exporte as suas tabelas da sua ROM P28 e importe-as para uma ROM original JDM P30 (203):
1. Abra a sua ROM P28 no Crome.
2. Vá a **File > Export Tables** e guarde o ficheiro de tabela.
3. Abra uma ROM original JDM P30 (203) como um novo ficheiro.
4. Vá a **File > Import Tables** e importe o ficheiro de tabela P28 que guardou.
5. Desative o sensor de detonação (knock sensor) e o limitador de velocidade no menu de opções (uma vez que as ECUs USDM P28 não possuem circuitos para o sensor de detonação).
6. Guarde e grave esta nova ROM P30 no seu chip.

Como alternativa, pode utilizar o código "237" da JDM P08 (SOHC VTEC D15B), que é uma versão de árvore de cames simples (SOHC) do código P30. Pode descarregar esta ROM na [biblioteca de Códigos de Definição de ECU](/cars/ecu/ecu-definition-codes).

### Porque é que não consigo editar determinados cabeçalhos de mapas no Crome?

No Crome, não pode editar os cabeçalhos de coluna para a primeira e última colunas, nem os cabeçalhos de linha para a primeira e última linhas numa ROM. Tentar fazê-lo causará erros imprevisíveis de dimensionamento dos mapas.

## Programação de Chips EEPROM

### Como programo ou leio uma EEPROM utilizando o Moates BURN1 no Crome?

1. Vá a **Settings** e selecione **Ostrich/BURN1** como o seu hardware de Real-Time Tuning (RTP).
2. O Crome deteta automaticamente se um Ostrich ou um BURN1 está ligado.
3. Para gravar uma ROM, ligue o BURN1 e clique em **Put**.
4. Para ler um chip, clique em **Get**.

### Como especifico o tipo de chip (por exemplo, 27SF512) para o Moates BURN1?

Selecione **Ostrich/BURN1** como o seu hardware RTP sob **Settings**. Irá aparecer uma caixa de seleção no lado direito do ecrã permitindo-lhe selecionar chips 27SF512.
