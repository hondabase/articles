---
summary: 'Mapas de ROM: Uma área para colaborar em todos os endereços de memória encontrados nas ROMs. Mapas de ROM para ECUs OBD1 Civic e Integra, Localizações de Memória, Recursos de Programação, Outros...'
applies_to:
  obd: [0, 1]
  brand: Acura/Honda
complexity: advanced
tags:
  - ecu
  - referência
  - tuning
  - rom
  - sensores
  - cablagem
  - conversão
  - diagnóstico
sources:
  - name: 'pgmfi.org wiki'
    title: 'Rom Maps'
    url: /pgmfi/wiki/library/rom-maps
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Mapas de ROM

## Mapas de ROM

Uma área para colaborar em todos os endereços de memória encontrados nas [ROM](/cars/rom/rom)s - Mapas de ROM
    - ECUs OBD1 Civic e Integra
        - Localizações de Memória
        - Recursos de Programação
    - Outros OBD1
        - Localizações de Memória
    - ECUs OBD0 VTEC
        - Localizações de Memória
    - OBD0 Injeção Multiponto (Multi-Point Fuel-Injected)
        - Localizações de Memória
        - Recursos de Programação
    - Recursos Externos

### ECUs [OBD](/cars/wiring/obd)1 Civic e Integra

*As [ECUs OBD1 Civic Integra](/cars/diagnostics/obd1-civic-integra-ec-us) partilham muitas características*#### Localizações de Memória

- [P28](/cars/sensors/p28) - [ROM](/cars/rom/rom)s baseadas no [USDM](/cars/sensors/usdm) 304 P28 (Civic D16Z6 [SOHC](/cars/sensors/sohc) VTEC 92-95)
- [P30](/cars/sensors/p30) - [ROM](/cars/rom/rom)s baseadas no [JDM](/cars/sensors/jdm) 203 P30 (Civic B16A [DOHC](/cars/sensors/dohc) VTEC)
- [P72](/cars/sensors/p72) - [ROM](/cars/rom/rom)s baseadas no [USDM](/cars/sensors/usdm) 273 P72 (Integra B18C1-3 [DOHC](/cars/sensors/dohc) VTEC)
- [Uber P72](/cars/rom/uber-p72) - [ROM](/cars/rom/rom)s baseadas no código [Uber Data ERM](/cars/rom/uber-data-erm) do Blake
- [Hi Res P72](/cars/rom/hi-res-p72) - [ROM](/cars/rom/rom)s baseadas no código personalizado de alta resolução [P72](/cars/sensors/p72) de John Cui

#### Recursos de Programação

- [ASM662](/cars/diagnostics/asm662) - pode ser usado para compilar (assemble) e descompilar (disassemble) estas [ROM](/cars/rom/rom)s.
- [Fórmulas de Conversão OBD1](/cars/wiring/obd1-conversion-formulae) - podem ser usadas para converter valores encontrados nestas [ROM](/cars/rom/rom)s para valores do mundo real.
- [Compatibilidade de Código OBD1](/cars/wiring/obd1-code-compatibility) - descreve as várias formas como podes correr código numa [ECU](/cars/ecu/ecu) diferente daquela a que se destinava.
- Algumas [Rotinas de Assembler 66k](/cars/sensors/66k-assembler-routines) - foram comentadas, e podes consultar as comentadas [Rotinas Civ Teg OBD1](/cars/rom/obd1-civ-teg-routines).
- [Automático ou Manual](/cars/diagnostics/auto-or-manual) - Existe uma interação entre hardware e software para determinar o comportamento da transmissão.

### Outros [OBD](/cars/wiring/obd)1

*Tudo o resto sobre [OBD](/cars/wiring/obd)1 - normalmente [MCU](/cars/rom/mcu)s baseados em `66207`*#### Localizações de Memória

- [P13](/cars/sensors/p13) - O H22 [JDM](/cars/sensors/jdm)/USDM (Prelude [DOHC](/cars/sensors/dohc) VTEC 92-95).

### ECUs [OBD](/cars/wiring/obd)0 VTEC

*As [ECUs OBD0 VTEC](/cars/diagnostics/obd0-vtec-ec-us) partilham muitas características*#### Localizações de Memória

- [PW0](/cars/sensors/pw0) - [ROM](/cars/rom/rom)s baseadas no PW0 [JDM](/cars/sensors/jdm) (CRX/Civic EF8/9 B16A 89-91), incluindo também algumas localizações do PW0 Europeu.
- [PR3](/cars/sensors/pr3) - [ROM](/cars/rom/rom)s baseadas no PR3 [JDM](/cars/sensors/jdm) (Integra XSi B16A 89-91)
- [ASM662](/cars/diagnostics/asm662) - pode ser usado para compilar e descompilar estas [ROM](/cars/rom/rom)s.
- Rotinas VTEC OBD0 - ainda não foram escritas.

### [OBD](/cars/wiring/obd)0 Injeção Multiponto (Multi-Point Fuel-Injected)

*As [ECUs OBD0 MPFI](/cars/diagnostics/obd0mpfi) partilham muitas características*#### Localizações de Memória

- [91 PM6](/cars/diagnostics/91pm6) - [ROM](/cars/rom/rom)s baseadas no PM6 de 91 (CRX/Civic Si [USDM](/cars/sensors/usdm) com [SOHC](/cars/sensors/sohc) D16A6)
- 91 PR4_PA - [ROM](/cars/rom/rom)s baseadas no PR4 [USDM](/cars/sensors/usdm) de 90-91 com sensor PA interno
- 90 PR4_no_PA - [ROM](/cars/rom/rom)s baseadas no PR4 [USDM](/cars/sensors/usdm) de 90-91 com sensor PA externo
- [91 PM7](/cars/sensors/91pm7) - Embora seja muito semelhante ao PM6 de 91, o George Ricketts e outros têm feito muito desenvolvimento com o PM7

#### Recursos de Programação

- [Localizações de RAM OBD0 PM6 PM7](/cars/rom/obd0pm6pm7ram-locations) - o código do PM6 e PM7 parece armazenar valores importantes em localizações de [RAM](/cars/reference/ram) muito semelhantes.
- [Fórmula de Conversão OBD0](/cars/wiring/obd0-conversion-formula) - pode ser usada para converter valores encontrados nestas [ROM](/cars/rom/rom)s para valores do mundo real.
- [Compatibilidade de Código OBD0](/cars/diagnostics/obd0-code-compatibility) - detalha que código pode ser trocado entre quais [ECU](/cars/ecu/ecu)s.
- Rotinas MPFI OBD0 - são frequentemente partilhadas entre [ECU](/cars/ecu/ecu)s.
- [Intel8051](/cars/rom/intel8051) - assembler/disassemblers de Intel 8051 podem ser usados com estas [ROM](/cars/rom/rom)s.

### Recursos Externos

- Uma página web com algumas das localizações de [ROM](/cars/rom/rom) e fórmulas está disponível [aqui](http://web.archive.org/web/20120411164611/http://ef-honda.com:80/ben/locations.html).
