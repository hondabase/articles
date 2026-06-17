---
summary: 'Guia de modificação de hardware para adicionar controlo VTEC de 1 fio a ECUs OBD0 Honda através do preenchimento de circuitos não utilizados de solenoides de transmissão automática.'
applies_to:
  brand: Honda
  obd: [0]
complexity: advanced
tags:
  - ecu
  - hardware
  - chipping
sources:
  - name: 'pgmfi.org wiki'
    title: 'Hardware For One Wire Vtec'
    url: /pgmfi/wiki/library/hardware-for-one-wire-vtec
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Adicionar Controlo VTEC de 1 Fio a ECUs OBD0 (PM6)

A ECU OBD0 PM6 de fábrica para transmissão manual (do Civic/CRX Si de 1988–1991) não possui circuitos de controlo VTEC. No entanto, como a Honda utilizou o mesmo layout de PCB tanto para ECUs de transmissão manual como automática, as placas manuais contêm ranhuras não preenchidas destinadas ao controlo dos solenoides de bloqueio (lockup) da transmissão automática.

Ao preencher estes circuitos não utilizados com resistências, transístores e díodos específicos, pode criar um canal de saída de alta corrente. As bases de código de ROM personalizadas (como o TurboEdit) podem então usar este canal para acionar um solenoide VTEC. Isto é vulgarmente designado como **modificação VTEC de 1 Fio** porque aciona o solenoide VTEC diretamente, enquanto o sensor de pressão do VTEC é ignorado no software.

---

## 1. Componentes Necessários

Muitas destas peças são difíceis de encontrar em catálogos normais de componentes eletrónicos. No entanto, podem ser facilmente reaproveitadas a partir de uma ECU OBD0 PM5 barata e comum (encontrada nos modelos Civic DX/LX):

| Localização | Tipo de Componente | Valor / Especificação | Notas & Referências |
| :---: | :--- | :--- | :--- |
| **Q42** | Transístor de Potência | 2SD1594 (NEC D1594) | Encapsulamento SOT-89 ou TO-220; reaproveitar de PM5/PM6 automática. |
| **Q16** | Transístor NPN | 2SC945 (C945) | NPN padrão; pode usar NTE85. |
| **Q28** | Matriz de Díodos | NIL3Z | Reaproveitar de ECUs PM5. |
| **IC17** | CI Driver | 8055P | Chip driver de lado baixo (low-side); reaproveitar de PM5/PM6 automática. |
| **C77** | Condensador Cerâmico | `0.01 uF` | Condensador de filtragem de disco padrão. |
| **R62** | Resistência | 10k $\Omega$, 1/8W | Resistência pull-down. |
| **R64** | Resistência | 51k $\Omega$, 1/8W | Resistência de gate. |
| **R66** | Resistência | 10k $\Omega$, 1/8W | Resistência de gate. |
| **R69** | Resistência | 110 $\Omega$, 1/4W | Resistência limitadora de corrente. |
| **R70** | Resistência | 1k $\Omega$, 1/8W | Resistência limitadora de corrente. |
| **D17** | Díodo Retificador | 1N4004 (ou 1N1004) | Díodo de proteção contra retorno (flyback). |
| **D26** | Díodo Zener | ~68V | Díodo de supressão de picos de tensão (tensão transiente). |
| **BR10** | Ponte | Fio de ponte (0 $\Omega$) | Ligação por ponte de solda. |
| **BR3** | Ponte | Fio de ponte (0 $\Omega$) | Opcional; depende da revisão da placa. |

---

## 2. Instalação Passo a Passo

1.  **Preparar a Placa:** 
    Abra a caixa da ECU e localize os footprints não preenchidos no lado direito da PCB correspondentes aos IDs de componentes listados acima. Use malha de dessoldar para limpar a solda de fábrica dos orifícios (through-holes).
2.  **Soldar Componentes Passivos e Díodos:** 
    Instale as resistências (`R62`, `R64`, `R66`, `R69`, `R70`), o condensador `C77` e os díodos `D17` e `D26`. Preste atenção às bandas de polaridade dos díodos.
3.  **Instalar Transístores e o CI Driver:** 
    Solde os transístores `Q42`, `Q16`, `Q28` e o CI driver `IC17`. Certifique-se de que a orientação dos mesmos corresponde aos contornos serigrafados na PCB.
4.  **Instalar a Ponte BR10:** 
    Solde um fio de cobre condutor rígido entre os contactos em **`BR10`**.
    
    > **Nota:** Dependendo da revisão específica da sua placa, poderá também necessitar de instalar uma ponte em **`BR3`**. Compare o layout da sua placa com o de uma placa de fábrica PS9 ou PM6 automática para verificar se o caminho da pista o exige.

---

## 3. Encaminhamento do Pino de Saída

Uma vez instalado o hardware, o novo canal de saída é encaminhado diretamente para a pinagem do conector da ECU. Sob a disposição de cablagem padrão de uma PM6:

*   O canal de saída ativa o pino **`A8`** (que normalmente é a saída do solenoide de bloqueio da transmissão automática em cablagens de caixa automática). 
*   Para cablar o VTEC, passe um único fio desde o seu solenoide VTEC no compartimento do motor através da parede corta-fogo (firewall) e ligue-o diretamente na posição **`A8`** da ficha da cablagem da ECU.
