---
summary: 'Análise técnica do modo de depuração de diagnóstico e interruptores de byte de configuração de ROM na ECU Honda P72 OBD1.'
tags: [ecu, diagnósticos, rom]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'Modo de Depuração (Debug) da P72'
    url: /pgmfi/wiki/library/p72-debug-mode
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Modo de Depuração (Debug) da ECU OBD1 P72 e Interruptores de Configuração de ROM

A ECU OBD1 P72 (que gere o motor B18C1 no Acura Integra GS-R) contém um segmento integrado de diagnóstico e depuração (debug) no seu código ROM. Muito parecido com a base de código da P30 (Civic/del Sol DOHC VTEC), o software da P72 possui um interruptor de depuração mestre (master debug switch) que pode anular as rotinas padrão de verificação de sensores e alterar o comportamento de diagnóstico.

Ao modificar o byte de depuração mestre na ROM, os programadores podem alterar a forma como a ECU processa códigos de erro, desvios (bypasses) de sensores e telemetria de comunicação.

---

## 1. O Interruptor de Depuração Mestre (`0x547E`)

O ponto de entrada para o modo de depuração é controlado por um interruptor de um único byte localizado no endereço ROM **`0x547E`**. 

* **Valor = `0x00` (Depuração Desativada):** A ECU executa as verificações padrão do motor, diagnósticos de sensores e avaliações de código.

* **Valor > `0x00` (Depuração Ativada):** A ECU ativa ramos lógicos alternativos, anulando várias subrotinas padrão de verificação de sensores.

---

## 2. Análise de Assembly (Conjunto de Instruções OKI 66k)

O bloco de assembly seguinte da ROM da P72 mostra como a ECU avalia a flag de depuração para carregar definições alternativas:

```assembly
; 1. Carrega o byte de depuração mestre para o Registo 0
53A7- LCB A, 0547eh ; Carrega o Code Byte de 0x547E para o Acumulador A
53AB- STB A, r0 ; Armazena o Byte do Acumulador A no Registo 0 (r0)

; 2. Procura o ponteiro de configuração de memória
53AC- MOV DP, #003d3h ; Move o Data Pointer para 0x03D3
53AF- LB A, [[[DP]]] ; Carrega o Byte do endereço apontado para A
53B0- STB A, r2 ; Armazena o Byte no Registo 2 (r2)

; 3. Se a depuração mestre estiver desativada (r0 == 0), salta para label_53ba
53B1- CMPB r0, #000h ; Compara o byte em r0 com 0x00
53B4- JEQ label_53ba ; Salta se for igual para label_53ba

; 4. Se a depuração estiver ativada, carrega o interruptor de depuração secundário
53B6- LCB A, 0547fh ; Carrega o Code Byte de 0x547F para A

; 5. Processa flags de RAM interna
label_53ba: 
53BA- SLLB A ; Shift Left Logical Byte (coloca o MSB na flag Carry)
53BB- MB off(00216h).3, C ; Move o bit Carry (C) para o bit 3 do offset de RAM 0x0216

53BE- LCB A, 05475h ; Carrega o Code Byte de 0x5475 para A
53C2- SLLB A ; Shift Left Logical Byte
53C3- MB off(002eeh).3, C ; Move o bit Carry para o bit 3 do offset de RAM 0x02EE

; 6. Avalia r0 novamente para carregar o interruptor de depuração terciário
53C6- CMPB r0, #000h ; Compara r0 com 0x00
53C9- JEQ label_53d2 ; Salta se for igual para label_53d2
53CB- LCB A, 05480h ; Carrega o Code Byte de 0x5480 para A
53CF- SLLB A ; Shift Left Logical Byte
53D0- SJ label_53dc ; Short Jump (salto curto) para label_53dc
```

### Fluxo de Execução:

1. A ECU verifica o interruptor de depuração mestre em `0x547E`.
2. Se o interruptor de depuração for `0x00`, a execução salta diretamente para `label_53ba`, ignorando a pesquisa secundária em `0x547F` e a pesquisa terciária em `0x5480`.
3. Se o interruptor de depuração for diferente de zero, a ECU processa flags de configuração adicionais em `0x547F` e `0x5480`, guardando o seu estado como flags binárias (bitwise) nos offsets de endereço de RAM `0x0216` e `0x02EE`.

---

## 3. Interruptores de Byte de Configuração Vizinhos

O bloco de memória ROM do endereço **`0x5470`** ao **`0x548F`** funciona como uma tabela de configuração contendo flags de interruptores de um único byte. Estas flags determinam se subsistemas de software específicos estão ativos:

* **Verificações do Solenoide de VTEC:** Ativa ou desativa os ciclos de diagnóstico que verificam a continuidade do solenoide de VTEC.

* **Verificação de VSS para VTEC:** Ativa ou desativa a verificação de requisito de velocidade mínima para ativação do VTEC.

* **Verificações do Sensor de Detonação (Knock Sensor):** Alterna a avaliação dos sinais da placa secundária do sensor de detonação.

* **Diagnósticos do Sensor de Oxigénio (Sonda Lambda):** Alterna os diagnósticos do circuito de aquecimento da sonda lambda.

Quando o modo de depuração mestre (`0x547E`) está ativo, estes interruptores individuais são ignorados ou anulados pela rotina de depuração mestre, permitindo testes de diagnóstico de ROMs personalizadas em motores onde faltam estas entradas físicas.
