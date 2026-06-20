---
summary: 'FAQ arquivado sobre configuração e afinação para o antigo editor de ROM Honda OBD1 UberData.'
tags: [tuning, software]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Uber Data FAQ'
    url: /pgmfi/wiki/library/uber-data-faq
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# FAQ de afinação do UberData

O UberData é um editor antigo de ROM Honda OBD1. Este artigo preserva o seu FAQ arquivado sobre configuração e afinação, embora identifique os seus valores de exemplo como orientação histórica e não como uma calibração pronta a utilizar.

> [!WARNING]
> As configurações de exemplo neste FAQ arquivado não constituem um mapa seguro para todos os motores. Verifique a compatibilidade da ROM, utilize instrumentação adequada e faça a afinação sob condições controladas.

## Que hardware é exigido pelo guia arquivado?

O FAQ original especifica uma ECU Honda OBD1 de Civic ou Integra de 1992-1995 e lista estas peças para a instalação do suporte (socketing):

- Uma resistência de 1/4 W, 1 kohm
- Dois condensadores de disco cerâmico de 0,1 uF
- Um trinco de endereços (address latch) `74HC373`
- Um suporte (socket) de ROM de 28 pinos
- Uma ROM de 28 pinos compatível, como uma `27C256`
- Um programador de ROM

Apresenta a seguinte sequência de instalação do suporte:

1. Dessolde os furos dos componentes na placa.
2. Solde um suporte de 28 pinos no espaço vazio da ROM.
3. Solde o chip `74HC373`.
4. Solde uma resistência em `R54`; a fonte indica que isto não é necessário numa ECU P72 GS-R do mercado americano (USDM).
5. Solde condensadores de 0,1 uF em `C51` e `C52`.
6. Instale o jumper `J1`.
7. Insira a ROM na orientação correta.

A fonte observa que valores para `R54` entre 1 kohm e 10 kohm foram reportados como funcionais, e que o valor de 1 kohm funcionou melhor com alguns emuladores de ROM.

> [!WARNING]
> Instalar uma EPROM ou EEPROM ao contrário pode sobreaquecê-la e danificá-la quando a alimentação é ligada. Se surgir um novo erro após a instalação do suporte, teste com um ficheiro bin original (stock) verificado e inspecione a soldadura. O guia arquivado indica que cortar `J1` repõe o código original de fábrica da ECU.

Para um guia de hardware mais abrangente, consulte a [Introdução à alteração (chipping) de ECUs](/cars/tuning/introduction-to-ecu-chipping).

## Qual o ficheiro bin de base sugerido pelo FAQ arquivado?

| Motor descrito na fonte | Base sugerida |
| :--- | :--- |
| B18A/B18B | `Stock LS/Int274.bin` |
| B18C, incluindo Type R | `Stock GSR/Int273.bin` |
| D-Series sem VTEC | `P06-Erm Baseline.bin` |
| D-Series com VTEC | `P28-Erm Baseline.bin` |

Estes são exemplos antigos do UberData. Confirme se a base corresponde ao código da ECU, hardware, injetores, sensores e motor antes de a utilizar.

## O que significam os valores do mapa?

O FAQ arquivado descreve a tabela do UberData da seguinte forma:

- O eixo Y representa a rotação do motor em RPM.
- O eixo X representa a carga do motor derivada do sensor MAP.
- As colunas de vácuo são exibidas em polegadas de mercúrio (inHg).
- As colunas de pressão (boost) são exibidas em psi.
- Valores mais altos no mapa de combustível indicam maior quantidade de combustível injetado.
- Os valores do mapa de ignição representam os graus de avanço antes do ponto morto superior (APMS / BTDC).

A fonte refere também que os injetores começam a atingir o seu limite máximo por volta de um valor de combustível exibido de `800`. Esta afirmação é específica do programa e, por si só, não estabelece o ciclo de trabalho (duty cycle) dos injetores.

## Como é que o FAQ arquivado preenche as colunas de pressão (boost)?

A fonte refere que uma ROM original não preenche automaticamente a secção de pressão (boost) dos mapas de combustível e ignição. Apresenta estes exemplos de cálculo do UberData:

- Defina a **Boost Average Efficiency** (Eficiência Média sob Pressão) para `120%`, e depois aplique para gerar os valores de combustível.
- Defina o **Boost Ignition Retard** (Atraso de Ignição sob Pressão) para `1.0` grau por psi, e depois aplique para gerar os valores de ignição.

O FAQ descreve a Boost Average Efficiency como uma estimativa da alteração de densidade causada pela compressão e aquecimento do ar de admissão. Descreve o Boost Ignition Retard como a quantidade de ponto de ignição retirada por cada psi.

> [!WARNING]
> Estes são exemplos de software arquivados, não configurações seguras universais. Os valores necessários de combustível e ignição dependem do motor, combustível, taxa de compressão, temperatura de admissão, pressão (boost) e outras condições.

## Como é que o FAQ arquivado define os limites de rotação e o VTEC?

- Abra o separador **Rev Limits**.
- Defina o **Fuel Cut** (Corte de Combustível) para o limite de rotação pretendido.
- Defina o **Fuel Resume** (Retoma de Combustível) cerca de 100 RPM abaixo do limite de corte.
- Defina os valores de RPM para ligar e desligar o VTEC no mesmo separador.
- Aplique as alterações.

Os limites corretos e o ponto de ativação do VTEC devem ser estabelecidos especificamente para o motor e calibração em questão.

## O que é o Full Throttle Launch?

A fonte descreve o Full Throttle Launch (controlo de arranque ou Launch Control) como um limite de rotação mais baixo utilizado abaixo de uma velocidade configurada do veículo. O **Fuel Cut** representa a rotação de arranque (Launch RPM), e o **Disable MPH** representa a velocidade a partir da qual o limitador de arranque deixa de ser aplicado.

Refere também o atraso do ponto de ignição e a adição de combustível na rotação de arranque para gerar pressão de turbo (build boost). Trata-se de uma orientação antiga e agressiva de afinação, que requer uma calibração cuidadosa.

## Como é que o FAQ arquivado ajusta o ralenti?

A fonte refere que os limites de velocidade de ralenti se alteram no separador **Misc**. Descreve também um ajuste da frequência da válvula IACV:

- Mova para a esquerda para um problema de ralenti baixo.
- Mova para a direita para um problema de ralenti alto.

Sugere avançar ligeiramente a ignição em torno de um alvo de ralenti elevado. Verifique o resultado no motor e código da ECU em vez de aplicar o conselho cegamente.

## O que é o enriquecimento por TPS?

O FAQ descreve o enriquecimento por TPS (TPS enrichment) como o combustível adicional injetado quando a borboleta de admissão abre rapidamente. Utiliza este exemplo aproximado de escala para injetores maiores do que a medida de fábrica de 240 cc/min:

```text
starting_percent = (240 / new_injector_size) * 100
```

A fonte sugere adicionar 5% a 10% ao resultado e indica aproximadamente 65% para injetores de 450 cc/min.

> [!NOTE]
> Este exemplo aproximado não tem em conta o tempo de atraso (dead time) dos injetores, pressão de combustível, compensação de voltagem ou o comportamento não linear em tempos de abertura curtos.

## O que é o enriquecimento no arranque a frio?

A fonte descreve o enriquecimento no arranque a frio (cold-crank enrichment) como o combustível adicionado durante o arranque a frio. Refere que injetores maiores podem causar arranques excessivamente ricos e hesitação do motor, mas assinala que a versão do UberData discutida no FAQ ainda não suportava este ajuste.

## Como é que o FAQ arquivado redimensiona um mapa de combustível?

A fonte sugere selecionar todo o mapa de combustível e aplicar este multiplicador aproximado:

```text
multiplier_percent = (240 / new_injector_size) 

* 100
```

Sugere depois adicionar 5% a 10% porque os injetores maiores não se comportam proporcionalmente em tempos de abertura muito curtos (low pulse widths). Considere isto apenas como um método inicial histórico e valide o resultado com dados medidos (sensores).

## Relacionado

- [Introdução à afinação de ECUs Honda](/cars/fueling/ecu-tuning)
- [Compreender mapas de combustível e ignição](/cars/fueling/understanding-maps)
- [Dimensionamento de injetores](/cars/fueling/injector-sizing)
