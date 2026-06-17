---
summary: 'Guia de software para descarregar, instalar e aplicar o plugin Add Extra Features no editor de ROM OBD1 Crome para ativar o launch control e tabelas de boost.'
applies_to:
  obd: [1]
complexity: intermediate
tags:
  - tuning
  - rom
  - software
sources:
  - name: 'pgmfi.org wiki'
    title: 'Howto Add Extra Features In Crome'
    url: /pgmfi/wiki/library/howto-add-extra-features-in-crome
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Como Instalar o Plugin "Add Extra Features" no Crome

O Crome é uma suite popular de edição e afinação (tuning) de ROMs para ECUs Honda OBD1. Embora o software base suporte tabelas padrão de combustível e ignição, funcionalidades avançadas—como launch control, passagens de caixa com aceleração total (flat foot shift) e escalamento de boost—devem ser adicionadas através de plugins externos. 

O plugin **Add Extra Features** (`addextrafeatures.cpf`) é um dos pacotes mais comuns utilizados para aplicar patches a ROMs padrão com estas opções.

---

## Passo 1: Colocar o Ficheiro do Plugin no Diretório do Crome

Os plugins do Crome utilizam a extensão de ficheiro `.cpf`. Para serem reconhecidos pelo software, estes ficheiros devem residir na pasta local de plugins do Crome.

1. Descarregue o pacote `addextrafeatures.zip` a partir de um arquivo autorizado de afinação Honda.
2. Extraia o conteúdo do ficheiro ZIP.
3. Copie o ficheiro `addextrafeatures.cpf` e cole-o no diretório de plugins da instalação do Crome. Por padrão, este encontra-se em:
 `C:\Program Files (x86)\Crome\Plugins\` (em sistemas Windows de 64 bits)
 
> [!NOTE]
> Historicamente, os arquivos legados de plugins do Crome eram protegidos por palavra-passe para evitar corrupção. Se solicitado durante a extração, utilize a palavra-passe padrão de instalação do Crome.

---

## Passo 2: Registar o Plugin no Crome

Assim que o ficheiro estiver no diretório, deve registá-lo na interface de definições do Crome:

1. Inicie o **Crome**.
2. No menu superior, navegue para **Plugins** -> **Install New Plugin...**
3. Na janela do explorador de ficheiros que aparece, navegue para o diretório `Plugins` do Crome.
4. Selecione **`addextrafeatures.cpf`** e clique em **Open**.
5. Verifique se o plugin aparece na lista de plugins ativos.

---

## Passo 3: Aplicar o Patch ao seu ROM BIN

Após o registo, deve aplicar os patches do plugin ao ficheiro ROM específico que está a editar.

1. Abra o ficheiro OBD1 `.bin` pretendido no Crome (normalmente uma ROM P28 ou P30 original).
2. Navegue para **Plugins** -> **Enhancements** -> **Add Extra Features**.
3. Surgirá um diálogo do assistente. Clique em **Next** para executar o script de injeção de código.
4. Assim que o processo de aplicação do patch terminar, os novos parâmetros serão adicionados à ROM.
5. Para configurar os novos parâmetros adicionados (como limites de RPM do launch control ou pressões de corte de boost), vá ao menu **Options** ou aceda aos separadores de tabelas relevantes no Crome.
