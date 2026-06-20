---
summary: 'Configuração e utilização de programadores de EPROM Willem (porta paralela/LPT) para gravar chips ROM SST 27SF512 e 27SF256 para ECUs Honda.'
tags: [chipping, hardware]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: Willem
    url: /pgmfi/wiki/library/willem
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Guia do Programador de EPROM Willem

O **Programador de EPROM Willem** é um gravador de ROM com design de hardware aberto (open-hardware) popular, que tem sido um favorito económico da comunidade de tuning Honda para instalar suportes (socketing) e gravar mapas de ECU personalizados. Como é uma placa de design aberto, é comercializada sob vários nomes (tais como "Enhanced Willem", "Dual Powered Willem", etc.) e fabricada por diferentes vendedores. 

Embora seja muito económico e capaz de gravar chips ROM Honda padrão como o `27C256` (OTP), `29C256` (EEPROM) e SST `27SF256` / `27SF512` (flash), o programador depende de uma porta paralela legada (LPT) e pode ser difícil de configurar.

> [!WARNING]
> **Requisitos da Porta Paralela (LPT) e do Sistema Operativo**: 
> O programador Willem necessita de uma porta paralela física real de hardware (endereço base padrão `0x378h` ou `0x278h`) para comunicar com o PC. Cabos adaptadores de impressora simples USB para Paralelo **não funcionam** porque não suportam mapeamento direto de portas I/O. Para executar o software do Willem, deve utilizar uma motherboard com um conector LPT integrado (onboard header) ou uma placa paralela PCI/PCI-e dedicada, além de um sistema operativo Windows compatível (frequentemente exigindo versões de 32 bits ou controladores de porta legados como `UserPort` / `io.dll` para permitir o acesso direto ao hardware).

---

## Programar Chips SST 27SF512 (Flash de 512k)

O SST **27SF512** é um chip de memória flash de 512 kbit (64 Kilobytes) que é habitualmente utilizado para emular ou substituir EPROMs padrão de 256 kbit (32 Kilobytes). Como tem o dobro do tamanho de uma ROM Honda OBD0/OBD1 padrão (`32KB`), deve configurar o software para gravar o ficheiro bin na metade superior do chip, utilizando um **offset** por hardware ou software.

### Guia de Programação Passo a Passo

1. **Ligar e Inicializar**: Ligue o cabo paralelo e a fonte de alimentação (alimentação USB ou adaptador DC) à placa Willem. Certifique-se de que os controladores (drivers) da porta paralela (ex. DLPortIO) estão ativos.
2. **Configurar os DIP Switches**: Defina os DIP switches da placa de acordo com a representação visual do software para o dispositivo `SST27SF512`.
3. **Inserir o Chip**: Insira o SST 27SF512 no socket ZIF. Alinhe o chip de modo a que os Pinos 14 e 15 fiquem nas ranhuras inferiores (mais próximas do manípulo do ZIF) com o entalhe (notch) voltado para cima (afastado da alavanca).
4. **Apagar o Chip**: No software, clique no ícone **Erase** (representado por um chip com uma borracha). 
 

* *Se a operação de apagamento falhar*, verifique se o jumper de modo da placa está na posição **Erase**, conforme mostrado na captura de ecrã das configurações de hardware.
5. **Configurar o Jumper para Programação**: Altere o jumper de modo da placa da configuração de Erase para a configuração **Program/Normal**.
6. **Aplicar o Offset de 32KB**: No canto inferior direito da janela do software Willem, localize o campo de introdução **Offset (Hex)**. Altere o valor padrão de `0` para `8000` (que corresponde a `32.768` bytes em decimal). Isto desloca os dados para os `32KB` superiores do chip.
7. **Carregar e Gravar**: Carregue o seu ficheiro `.bin` compilado. Clique no ícone **Program** (ilustração de um chip completo). Quando aparecer a janela pop-up a perguntar se deseja utilizar o offset hexadecimal especificado, selecione **Yes** (Sim).
8. **Verificar**: O software irá gravar os dados e executar automaticamente um teste de verificação. Certifique-se de que ambas as operações são concluídas com sucesso com um estado de `100%`.
9. **Verificação Final**: Insira o chip no socket da sua ECU. Rode a chave de ignição para a posição RUN (motor desligado). O relé principal deve dar um estalo (click) e a luz de aviso de avaria do motor (CEL) deve apagar-se após 2 segundos. Se a CEL se mantiver acesa continuamente, o chip não foi gravado ou o offset não foi aplicado corretamente.

### Capturas de Ecrã de Configuração (27SF512)

![Configuração do Dispositivo no Software Willem](willem1_377.jpg)
*Configuração do Dispositivo no Software Willem*

![Configuração de Buffer e Offset no Software Willem](willem2_157.jpg)
*Configuração de Buffer e Offset no Software Willem*

![Configuração dos DIP Switches da Placa Willem](dip_853.jpg)
*Configuração dos DIP Switches da Placa Willem*

![Posicionamento do Chip SST 27SF512 no Socket ZIF](chip_117.jpg)
*Posicionamento do Chip SST 27SF512 no Socket ZIF*

![Posição dos Jumpers da Placa Willem para Apagar o Chip](erase_146.jpg)
*Posição dos Jumpers da Placa Willem para Apagar o Chip*

![Posição dos Jumpers da Placa Willem para Programar o Chip](program_156.jpg)
*Posição dos Jumpers da Placa Willem para Programar o Chip*

---

## Programar Chips SST `27SF256` (Flash de 256k)

O SST **`27SF256`** é um chip nativo de 256 kbit (32 Kilobytes), o que significa que corresponde perfeitamente ao tamanho padrão da ROM Honda. Não são necessários offsets de software, mas os jumpers de configuração da placa têm de ser ajustados.

### Apagar o SST `27SF256`

Ao contrário das EPROMs padrão que necessitam de luz UV para serem apagadas, o SST `27SF256` é eletricamente apagável. No entanto, jumpers específicos têm de ser reposicionados para permitir que a alta tensão de apagamento seja encaminhada corretamente:

![Configuração dos Jumpers da Placa Willem para Apagar o SST 27SF256](sst27sf256erase_184.jpg)
*Configuração dos Jumpers da Placa Willem para Apagar o SST `27SF256`*

### Gravar o SST `27SF256`

Para gravar o SST `27SF256`, volte a colocar os jumpers na posição de gravação PCB3 (não os deixe no modo Willem):

![Configuração dos Jumpers da Placa Willem para Gravar o SST 27SF256](sst27sf256_136.jpg)
*Configuração dos Jumpers da Placa Willem para Gravar o SST `27SF256`*
