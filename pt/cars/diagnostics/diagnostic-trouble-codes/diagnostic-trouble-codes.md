---
summary: 'Guia completo para obter e interpretar códigos de erro de diagnóstico (DTC). Saiba como diagnosticar códigos de erro OBD0, OBD1 e OBD2 em veículos Honda e Acura.'
tags: [diagnósticos, obd, resolução-de-problemas, códigos-de-motor, códigos-tcu]
applies_to:
  models: [civic, crx, del-sol, integra, prelude, accord, s2000, nsx]
  chassis: [ef, eg, ek, da, dc2, bb, cb-cd, ap1, ap2, na1-na2]
complexity: beginner
sources:
  - name: 'pgmfi.org wiki'
    title: 'Honda Error Codes'
    url: /pgmfi/wiki/library/honda-error-codes
  - name: 'pgmfi.org wiki'
    title: 'Checking Error Codes'
    url: /pgmfi/wiki/library/checking-error-codes
---

# Obtenção e Referência de Códigos de Erro de Diagnóstico (DTC)

Quando um sensor ou sistema de um motor Honda apresenta uma falha, a Unidade de Controlo do Motor (ECU) acende a luz de verificação do motor (Check Engine Light - CEL / MIL) no painel de instrumentos e armazena um código de erro de diagnóstico (DTC) na sua memória.

Este guia explica como obter estes códigos e fornece uma referência unificada para erros de motor e transmissão.

---

## Como Obter Códigos de Diagnóstico

O método para obter os códigos depende da geração OBD do seu veículo.

### Sistemas OBD0 (1988–1991)

As ECUs OBD0 apresentam os códigos através de um LED montado diretamente na placa de circuito da ECU:
1.  Roda a chave de ignição para a posição ON.
2.  Localiza a ECU (normalmente sob a carpete ou banco do lado do passageiro).
3.  Observa o LED vermelho através da janela circular na caixa metálica da ECU.
4.  **Contagem:** Conta as piscadelas do LED vermelho. Um código 9 é representado por 9 piscadelas rápidas.

### Sistemas OBD1 (1992–1995)

Os sistemas OBD1 fazem piscar a luz de Check Engine (CEL) no painel de instrumentos quando o conector de serviço é jumpeado.

![jumper de serviço](servicejumper.jpg)

1.  **Localize o Conector SCS:** No lado do passageiro, sob o porta-luvas, encontre uma cobertura verde que aloja um conector azul de 2 pinos.
2.  **Jumpeie o Conector:** Com a ignição em OFF, ligue os dois pinos usando um clipe de papel ou um fio.
3.  **Leia a CEL:** Roda a chave para a posição **IGN** (não ligue o motor). A CEL começará a piscar.
4.  **Interprete as Piscadelas:**
    *   **Piscadelas longas (1,0 seg):** Dígito das dezenas (ex: 2 longas = 20).
    *   **Piscadelas curtas (0,5 seg):** Dígito das unidades (ex: 1 curta = 1).
    *   **Exemplo:** `LONGA-LONGA-CURTA-PAUSA` é o Código 21 (Solenoide VTEC).

### Sistemas OBD2 (1996–2001)

Os sistemas OBD2 utilizam um conector DLC (Data Link Connector) padrão de 16 pinos sob o tablier no lado do condutor.
*   **Obtenção:** Requer uma ferramenta de diagnóstico (scanner) ou leitor de códigos OBD2.
*   **Códigos:** Utiliza códigos alfanuméricos (ex: `P0420`), embora muitos Hondas OBD2 ainda suportem o método de "piscadelas" através do conector SCS para códigos básicos de motor.

---

## Referência Unificada de Códigos de Diagnóstico

Utilize a ferramenta abaixo para pesquisar códigos de motor (ECU) e transmissão (TCU).

::: widget error-codes :::

---

## Próximos Passos na Resolução de Problemas

1.  **Limpar a Memória:** Remova o fusível **BACK UP** (7.5A) na caixa de fusíveis do motor por 30 segundos.
2.  **Confirmar a Falha:** Conduza o veículo. Se a CEL voltar, a falha é "persistente" e requer reparação.
3.  **Verificar a Cablagem Primeiro:** A maioria dos códigos de "sensor" é causada por cablagem desgastada ou conectores soltos, especialmente em cablagens antigas.
4.  **Verificar o VSS:** Se tiver o Código 17 (VSS), o VTEC não irá ativar e o velocímetro poderá estar parado ou errático.

### Recursos Externos
- [Referência Técnica Hybrid Garage](http://web.archive.org/web/20250705085711/http://www.hybridgarage.com/tech/codes.html)
- [Procedimentos de Diagnóstico Honda-Tech](http://web.archive.org/web/20060818072131/http://honda-tech.com:80/zerothread?id=1171263)
