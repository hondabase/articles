---
summary: 'Uma folha de referência abrangente de mapeamento de memória da RAM interna, flags de bits e registadores XRAM para as ECUs Honda OBD0 PM6 e PM7.'
tags: [reference, obd0]
complexity: advanced
sources:
  - name: 'pgmfi.org wiki'
    title: 'OBD0PM6PM7RAM Locations'
    url: /pgmfi/wiki/library/obd0pm6pm7ram-locations
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Endereços das Localizações de RAM OBD0 PM6 & PM7

Esta folha de referência descreve os espaços de endereços mapeados em memória interna das ECUs Honda OBD0 **PM6** (USDM 1988–1991 Civic/CRX Si) e **PM7** (JDM DOHC ZC). 

Estas ECUs utilizam microcontroladores derivados do 8051, que particionam a memória em RAM interna, espaços endereçáveis por bit e RAM externa (XRAM). Este mapeamento é fundamental para a engenharia reversa de mapas de combustível/ignição, escrita de código de registo de dados (datalogging) personalizado ou modificação de rotinas de ROM de fábrica.

---

## Localizações de RAM Interna de 8-Bits (Bytes)

Abaixo encontram-se os principais registadores de 8 bits localizados no espaço primário de RAM interna:

| Endereço | Parâmetro / Nome Curto | Notas & Funções |
| :---: | :--- | :--- |
| **`0x2C.1`** | MAP High CEL | Flag de bit; definido como 1 se a leitura do sensor MAP exceder os parâmetros seguros. |
| **`0x30`** | ECT Complement | Complemento bit a bit de `0x31h` (verifica a integridade do sinal do ECT). |
| **`0x31`** | ECT | Leitura do sensor de Temperatura do Líquido de Refrigeração do Motor (ECT) (espelha `XRAM 0x1004h`). |
| **`0x32`** | IAT | Leitura do sensor de Temperatura do Ar de Admissão (IAT) (espelha `XRAM 0x1005h`). |
| **`0x33`** | IAT Complement | Complemento bit a bit de `0x32h` (verifica a integridade do sinal do IAT). |
| **`0x34`** | BARO | Pressão Barométrica (sensor PA na placa). |
| **`0x36`** | MAP | Leitura do sensor de Pressão Absoluta do Coletor (MAP). |
| **`0x37`** | MAP Complement | Complemento bit a bit de `0x36h`. |
| **`0x38`** | MAP

* | Valor de MAP bloqueado/armazenado (atualizado quando o bit `0x79.4` é definido). |
| **`0x39`** | TPS | Leitura do Sensor de Posição da Borboleta (TPS). |
| **`0x3A`** | TPS (Backup) | Leitura secundária ou filtrada de TPS. |
| **`0x3B`** | RPM (8-bit) | Cálculo simplificado de rotação do motor a 8 bits. |
| **`0x3D`** | RPM Low Byte | Byte de baixa leitura do registador do coprocessador OKI 6260 `0x2004h`. |
| **`0x3E`** | RPM High Byte / Status | Byte de alta leitura do coprocessador OKI 6260. |
| **`0x47`** | Limit RPM Low | Byte de baixa de RPM usado para verificações de limite de rotação (copiado de `0x3Dh`). |
| **`0x48`** | Limit RPM High | Byte de alta de RPM usado para verificações de limite de rotação (copiado de `0x3Eh`). |
| **`0x49`** | Prev RPM Low | Byte de baixa histórico da rotação do motor (ciclo anterior). |
| **`0x50`** | Prev RPM High | Byte de alta histórico da rotação do motor (ciclo anterior). |
| **`0x51`** | Delta RPM Low | Taxa de variação de RPM (byte de baixa). Calculada como `0x47` - `0x49`. |
| **`0x52`** | Delta RPM High | Taxa de variação de RPM. O bit `0x17h` indica o sinal (1 = negativo). |
| **`0x53`** | VSS High | Byte de alta do contador do Sensor de Velocidade do Veículo (VSS) de 16 bits. |
| **`0x54`** | VSS Low | Byte de baixa do contador do Sensor de Velocidade do Veículo (VSS) de 16 bits. |
| **`0x5C`** | 6260 Port 1 Data | Carregado no registador OKI 6260 `0x2001h` se o bit `0x52h` estiver definido. |
| **`0x5D`** | 6260 Port 2 Data | Carregado no registador OKI 6260 `0x2002h` se o bit `0x52h` estiver definido. |
| **`0x5E`** | 6260 Port 1 Data | Carregado no registador OKI 6260 `0x2001h` se o bit `0x53h` estiver definido. |
| **`0x5F`** | 6260 Port 2 Data | Carregado no registador OKI 6260 `0x2002h` se o bit `0x53h` estiver definido. |
| **`0x60`** | 6260 Port 1 Data | Carregado no registador OKI 6260 `0x2001h` se o bit `0x54h` estiver definido. |
| **`0x61`** | 6260 Port 2 Data | Carregado no registador OKI 6260 `0x2002h` se o bit `0x54h` estiver definido. |
| **`0x6A`** | Fuel Trim Add | Ajuste primário de compensação de combustível a curto prazo (fuel trim). |
| **`0x6C`** | VSS (8-bit) | Valor simplificado de velocidade do veículo a 8 bits. |
| **`0x6F`** | O2 Fuel Bias | Fator de correção de combustível em circuito fechado (closed-loop) baseado no sensor de O2 (sonda lambda). |
| **`0x70`** | O2 Fuel Bias (Filtered)| Fator de combustível em circuito fechado suavizado/integrado. |
| **`0xA2`** | Fuel Mult Low | Multiplicador do byte de baixa usado para ajustar a largura de pulso do injetor de combustível. |
| **`0xA3`** | Fuel Mult High | Multiplicador do byte de alta usado para ajustar a largura de pulso do injetor de combustível. |

---

## Flags de Bit de RAM Interna (Endereçáveis por Bit)

Abaixo estão localizados os bits lógicos e de diagnóstico críticos no espaço de RAM interna endereçável por bit:

| Endereço do Bit | Nome da Flag | Nota Técnica / Limiar |
| :---: | :--- | :--- |
| **`0x60h`** | MAP CEL Flag | Definido como 1 quando a pressão do coletor está fora dos limites normais de funcionamento. |
| **`0x17h`** | RPM Delta Sign | Bit de sinal para aceleração do motor (0 = a acelerar, 1 = a desacelerar). |
| **`0x2Eh`** | RPM Limit Safe | Definido como 1 quando a rotação atual do motor está abaixo do limite de rotação ativo. |
| **`0x57.0`** | Ignition Coil 1 | Indicador de disparo para a fase 1 da bobina de ignição. |
| **`0x57.1`** | Ignition Coil 2 | Indicador de disparo para a fase 2 da bobina de ignição. |
| **`0x71.1`** | Idle Threshold | Definido como 1 se a rotação estiver entre ~890 e ~950 RPM (zona de ralenti alvo). |
| **`0x71.2`** | VTEC RPM Cross | Definido como 1 se a rotação exceder ~5.400 a ~5.600 RPM. |
| **`0x71.3`** | Decel Vacuum | Definido como 1 se o MAP for de vácuo elevado (~9.3 a ~8.7 in Hg / carga baixa). |
| **`0x71.4`** | Medium Vacuum | Definido como 1 se o MAP for de vácuo médio (~6.0 a ~5.0 in Hg). |
| **`0x79.4`** | Mid-RPM threshold | Definido como 1 se a rotação for ~3400 a ~3650 RPM. Utiliza o MAP bloqueado `0x38h` se definido. |
| **`0x79.6`** | Low Load Threshold | Definido como 1 se o MAP for ~6.0 a ~4.0 in Hg. |
| **`0x7A.4`** | High Load Threshold| Definido como 1 se o MAP for ~8.1 a ~6.0 in Hg. |

---

## Localizações de RAM Externa (XRAM)

Estes endereços existem no chip de RAM estática externa (geralmente um chip SRAM 5128 padrão mapeado através do comando `MOVX`):

| Endereço XRAM | Parâmetro / Nome Curto | Notas & Funções |
| :---: | :--- | :--- |
| **`0x012h`** | VSS High Buffer | Retém temporariamente o byte de alta de VSS lido do coprocessador OKI 6260. |
| **`0x013h`** | VSS Low Buffer | Retém temporariamente o byte de baixa de VSS lido do coprocessador OKI 6260. |
| **`0x032.2`** | Cranking Speed Flag | Definido como 1 se a rotação do motor estiver na faixa de arranque (~540 a ~630 RPM). |
| **`0x032.3`** | High Load Fuel Cut | Definido como 1 se a pressão do MAP for extremamente alta (~2.5 a ~1.0 in Hg). |
| **`0x07Dh`** | ADC Destination PTR | Ponteiro de endereço que especifica onde o byte bruto do ADC de `0x4001h` é escrito. |
| **`0x0A1h`** | Checksum Accumulator| Retém a contagem de checksum em execução durante as rotinas de verificação da ROM. |
| **`0x0A2h`** | Checksum Pointer | Retém o próximo byte de endereço de alta (DPH) durante os ciclos de checksum da ROM. |
