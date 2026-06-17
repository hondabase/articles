---
summary: 'Um guia para escolher e utilizar gravadores de EPROM/Flash ROM para programar chips de memória 27C256 e SST 27SF256 em ECUs Honda.'
applies_to:
  obd: [0, 1, 2]
complexity: intermediate
tags:
  - hardware
  - reference
sources:
  - name: 'pgmfi.org wiki'
    title: 'Rom Burner'
    url: /pgmfi/wiki/library/rom-burner
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Guia de Gravadores de EPROM e Flash ROM

Um gravador de ROM (também conhecido como programador de dispositivos) é uma ferramenta eletrónica utilizada para gravar ficheiros de calibração binários compilados (`.bin`) a partir de um computador para chips de memória. Estes chips são depois inseridos no suporte de CI (IC socket) de uma ECU modificada para executar mapas personalizados. 

Como as ECUs Honda OBD0 and OBD1 requerem 32 KB de espaço de programa, é essencial selecionar um gravador que suporte chips de memória de 256 quilobits (256k).

---

## 1. Tipos de Chips Suportados

Embora muitos chips partilhem o encapsulamento DIP-28, os seus procedimentos de gravação e apagamento variam:

* **27C256 (EPROM):** Erasable Programmable Read-Only Memory (Memória Apenas de Leitura Programável e Apagável). Estes são normalmente programáveis uma única vez (OTP), a menos que utilize chips com janela, que requerem um apagador ultravioleta (UV) dedicado para limpar antes de regravar.

* **SST 27SF256 (Flash EPROM):** Muitos preparadores (tuners) preferem este chip. Pode ser apagado eletricamente e regravado em segundos pelo software do gravador, eliminando a necessidade de luz UV.

* **AT29C256 (EEPROM):** Electrically Erasable PROM. Semelhante ao chip flash SST, mas com algoritmos de temporização e tensões de gravação diferentes.

---

## 2. Opções de Hardware de Programador

Abaixo está uma comparação de gravadores commumente utilizados para afinação (tuning) de ECUs Honda:

| Modelo do Programador | Interface | Estado | Notas |
| :--- | :---: | :--- | :--- |
| **XGecu TL866 / T48 (MiniPro)** | USB | **Padrão Moderno** | O programador de eleição atual para entusiastas de DIY. Barato, ativamente suportado e programa chips SST `27SF256` e `27C256` rapidamente. |
| **Moates BURN1 / BURN2** | USB | **Legado / Usado** | Programadores USB personalizados desenhados pela Moates especificamente para afinação automóvel. Funcionam nativamente com chips SST `27SF256` e integram-se diretamente com software como o Crome. |
| **Willem Programmer** | Paralela (LPT) / USB | **Legado / DIY** | Placa de estilo open-source muito económica. Versões paralelas mais antigas requerem uma porta paralela de hardware real (LPT1) e falharão com adaptadores de impressora USB para paralelo. |
| **Pocket Programmer 2** | Paralela | **Legado** | Historicamente incluído com pacotes Hondata mais antigos; requer uma porta paralela. |
| **Batronix USB Programmer** | USB | **Profissional** | Gravador profissional de alta qualidade com engenharia alemã e excelente suporte de software. |
| **Xeltek SuperPro / EE Tools** | USB | **Profissional** | Programadores profissionais de gama alta; fiáveis, mas geralmente caros para entusiastas de um único veículo. |

---

## 3. Dicas de Programação

* **Selecione o Perfil de Chip Correto:** Selecione sempre o fabricante e o prefixo do modelo exatos do seu chip (por exemplo, `SST27SF256` em vez de um `27C256` genérico) no software do seu gravador. Aplicar a tensão de programação (Vpp) errada pode danificar permanentemente o chip.

* **Verifique após a Gravação:** Ative a função "Verify" (Verificar) no software do seu gravador. Isto compara o conteúdo gravado no chip byte a byte com o ficheiro BIN original no seu computador para garantir que não ocorreram erros de gravação.
