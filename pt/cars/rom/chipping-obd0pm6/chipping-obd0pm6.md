---
summary: 'Guia de hardware passo a passo para alterar (chipping) a ECU PM6 OBD0 (Civic/CRX Si 1988–1991) para aceitar EPROMs externas e mapas personalizados.'
applies_to:
  obd: [0]
complexity: advanced
tags:
  - ecu
  - chipping
  - hardware
sources:
  - name: 'pgmfi.org wiki'
    title: 'Chipping OBD0PM6'
    url: /pgmfi/wiki/library/chipping-obd0pm6
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Alterar (Chipping) a ECU PM6 OBD0 (Civic/CRX Si 1988–1991)

A ECU PM6 OBD0 é a unidade de controlo do motor de fábrica para os Honda Civic Si e CRX Si de 1988–1991 (equipados com o motor D16A6 SOHC). Alterar esta ECU permite a afinação personalizada dos mapas de combustível e ignição utilizando programas de edição como o TurboEdit. 

No entanto, a dificuldade do processo de modificação depende bastante do ano do modelo da sua ECU.

---

## Passo 1: Identificar a Versão da sua ECU

Antes de iniciar qualquer trabalho de soldadura, abra a tampa da ECU e identifique se tem uma placa de modelo antigo (early-model) ou modelo recente (late-model).

### Modelo Recente (1990–1991) com EPROM Externa
A maioria das ECUs PM6, PM7, PR4 e PP5 de 1990–1991 foram construídas com um chip ROM externo e passível de ser dessoldado. Estas placas são simples de modificar porque as pistas de memória já estão direcionadas para a localização de um chip discreto.

![Late-Model OBD0 ECU with factory external ROM](PM6tochip_small.jpg)
*ECU OBD0 de modelo recente com um chip ROM de fábrica passível de ser dessoldado.*

### Modelo Antigo (1988–1989) com ROM Interna
A maioria das ECUs PG7, PM6, PM7 e PM8 de 1988–1989 funciona com um microcontrolador com memória interna. Falta-lhes um chip EPROM externo separado. Alterar estas placas antigas requer soldadura complexa para adicionar trincos lógicos (latches) em falta e redirecionar as linhas de endereço do microcontrolador (MCU).

![Early-Model OBD0 ECU lacking external ROM](trickyPM7small.jpg)
*Esquema de placa de modelo antigo sem um chip de memória externa separado.*

> [!NOTE]
> Se tiver uma ECU de modelo antigo de 1988–1989, consulte o guia especializado de [Alteração de ECUs OBD0 antigas](/cars/rom/chipping-an88-89ecu) para obter instruções sobre como adicionar o hardware necessário.

---

## Passo 2: Dessoldar e Instalação de Socket (ECUs de Modelo Recente)

Para as ECUs de 1990–1991 com uma ROM externa de fábrica, o processo de alteração envolve a substituição do chip permanente por um suporte (socket) reutilizável.

### Materiais Necessários
*   Suporte (socket) de circuito integrado de 28 pinos de perfil baixo
*   Fita dessoldadora (solder wick) ou uma bomba de dessoldar de qualidade
*   Solda eletrónica com núcleo de resina (recomenda-se solda com chumbo 60/40 pela facilidade de utilização)
*   X-ato ou lâmina afiada
*   EPROM compatível programada (ex: SST `27SF256`)

### Procedimento

1.  **Remover a ROM de Fábrica:** 
    Utilizando um x-ato afiado ou uma lâmina, corte cuidadosamente os 28 pinos do circuito integrado de fábrica perto do corpo de plástico do chip. 
    
    > **Atenção:**
    > Não aplique demasiada força para baixo. Uma lâmina que escorregue pode facilmente cortar as pistas de cobre delicadas na placa de circuito, danificando permanentemente a ECU.

2.  **Limpar os Furos da Placa (Through-Holes):** 
    Assim que o corpo do chip for removido, aqueça `cada` perna de pino restante no lado da soldadura da placa e puxe-a para fora usando uma pinça. Use fita dessoldadora ou uma bomba de dessoldar para limpar a solda de fábrica de todos os 28 furos. Os furos têm de ficar completamente desimpedidos para que o novo suporte possa entrar sem esforço.

3.  **Instalar o Suporte de Circuito Integrado:** 
    Insira um suporte de circuito integrado padrão de 28 pinos na placa, garantindo que a ranhura (notch) no suporte coincide com a marca de ranhura impressa na placa de circuito da ECU. Solde os 28 pinos a partir do lado inferior da placa. Inspecione o seu trabalho com uma lupa para garantir que não há soldaduras frias ou pontes de solda.

4.  **Inserir a EPROM:** 
    Insira o seu chip EPROM SST `27SF256` personalizado ou equivalente no suporte, certificando-se de que a ranhura do chip coincide com a ranhura do suporte.
