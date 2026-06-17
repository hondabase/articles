---
summary: 'Autor: doc 07-10-03 15:21 Fui eu? Ok, numa ROM 203 ou 209, podes alterar a posição 6010 (hex) de 00 para FF para contornar a verificação de VSS na rotina do VTEC.'
applies_to:
  obd: [0, 1, 2]
  ecus: [P30]
complexity: advanced
tags:
  - tuning
  - rom
  - sensores
  - referência
  - diagnóstico
  - ecu
sources:
  - name: 'pgmfi.org wiki'
    title: 'Disable Vtec VSS Check P30 203'
    url: /pgmfi/wiki/library/disable-vtec-vss-check-p30-203
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Desativar Verificação de VSS do VTEC P30 203

Autor: doc 07-10-03 15:21 Fui eu? Ok, numa ROM 203 ou 209, podes alterar a posição 6010 (hex) de 00 para FF para contornar a verificação de [VSS](/cars/sensors/vss) na rotina do VTEC. Se utilizares outra ROM, terás de procurar a localização correta. Eis uma breve instrução de como eu procuraria: Primeiro precisamos de uma desassemblagem (disassembly) da ROM desejada. Escolhe o teu desassemblador favorito e cria o disasm. Procura pela rotina do VTEC. Normalmente procuro por "22.1"; com o desassemblador do a1k0n tens de procurar por "`22h`.1" (não confundir com *OFF* 22.1) e parar quando encontrar uma rotina que se pareça com a seguinte (os endereços e offsets podem ser diferentes, mas o RB 22.1 e o RB 22.0 são iguais em todas as ROMs!):

- 11B9- `C5` 22 09 : RB 22.1 ; Reset Bit Port1.1 VTEC
- 11BC- CB 24 : SJ 11E2 ; desativar VTEC

---

- 11BE- C5 22 19 : SB 22.1 ; Set Bit Port1.1
- 11C1- C5 E9 C0 32 : CMPB E9, #32
- 11C5- CA 1B : JLT 11E2
- 11C7- C5 C1 C0 44 : CMPB C1, #44
- 11CB- CD 15 : JGE 11E2

---

- 11CD- 90 9D 10 60 : LCB A, 6010 ; usar [VSS](/cars/sensors/vss)
- 11D1- CE 03 : JNE 11D6
- 11D3- D8 28 0C : JBR off 28.0, 11E2 ; velocidade suficiente para VTEC?
- 11D6- DB 16 03 : JBR off 16.3, 11DC
- 11D9- ED 11 03 : JBS off 11.5, 11DF
- 11DC- E9 28 0B : JBS off 28.1, 11EA
- 11DF- E9 1F 21 : JBS off 1F.1, 1203

---

- 11E2- C5 22 08 : RB 22.0 ; }
- 11E5- C4 1F 0A : RB off 1F.2 ; } desativar VTEC
- 11E8- CB 29 : SJ 1213 ; }

---

Para ativar o VTEC sem nos importarmos com o sensor de velocidade, estamos interessados nas seguintes linhas:
- 11CD: LCB A,6010 ; Aqui o conteúdo da [ROM](/cars/rom/rom) no endereço 6010 é lido para A (configuração em código / hardcoded).
- 11D1: JNE 11D6 ; Se o conteúdo da [ROM](/cars/rom/rom) não for 00, salta para 11D6.
- 11D3: JBR off 28.0, 11E2 ; Se off 28.0=0, salta para 11E2 (o bit off 28.0 é definido numa rotina de verificação de [VSS](/cars/sensors/vss)).

Agora podes decidir como queres modificar (patch) a tua ROM. Altera o endereço da ROM 6010 (ou o que encontrares na tua ROM) de 00 para FF, salta a verificação do [VSS](/cars/sensors/vss) (11CD: J 11D6), ou outra opção qualquer (ex: 11D3: NOP, NOP, NOP)... Espero que isto ajude. Doc
