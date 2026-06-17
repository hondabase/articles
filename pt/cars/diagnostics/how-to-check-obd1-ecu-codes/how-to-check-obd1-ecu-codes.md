---
sources:
  - name: 'pgmfi.org wiki'
    title: 'Checking Error Codes'
    url: /pgmfi/wiki/library/checking-error-codes
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Como Verificar os Códigos da ECU OBD1

![jumper de serviço](servicejumper.jpg)

## Localização

Em quase todos os Hondas de 1988 a 2000, no lado do passageiro do seu veículo, sob o tablier e por baixo do porta-luvas, encontrará uma cobertura verde acima da zona dos pés (kickpanel) que aloja um conector azul com dois fios ligados a ele. **Este conector é referido no manual de serviço como o conector *SCS*.**

## Procedimento

O que terá de fazer é colocar a ignição na posição desligada (OFF) e, utilizando um pedaço de fio descarnado ou um clipe de papel, ligar as duas extremidades abertas do conector azul. Assim que o fizer, rode a chave para a posição *IGN* (segunda posição) e observe a luz *CEL*. Ela irá acender-se numa série de piscadelas.

### Contar as piscadelas

Irá notar que haverá piscadelas LONGAS e piscadelas CURTAS. Todos os códigos de erro da *ECU* terão dois dígitos.
Em todos os casos, uma piscadela longa representa o dígito 10, bastando somar as piscadelas longas para o determinar. Uma piscadela curta representa o dígito 1, bastando somar as piscadelas curtas. Some a quantidade de 10s e de 1s para obter o número do código de erro.

ex. `LONGA-LONGA-LONGA-CURTA-CURTA-CURTA-CURTA-PAUSA`

...representa o código de erro: **34**

3 piscadelas LONGAS seguidas de 4 curtas, e depois uma pausa longa. Se esse for o único código que a *ECU* está a emitir, o código irá simplesmente repetir-se até retirar a chave. Se, no entanto, houver mais do que um código de erro da *ECU*, verá uma série diferente de piscadelas seguida de uma pausa longa. Assim que todos os códigos da *ECU* tiverem sido apresentados, estes continuarão a ciclar até retirar a chave.

ex. `LONGA-LONGA-CURTA-PAUSA-LONGA-LONGA-LONGA-LONGA-CURTA-CURTA-CURTA-PAUSA`

...representa os códigos de erro: **21 e 43**

Uma vez determinados os códigos, pode simplesmente remover o clipe de papel ou o fio do conector e colocá-lo novamente no alojamento verde.

## Resolver o problema

Agora que tem os códigos de erro, pode prosseguir com a resolução do problema.
Pode encontrar mais informações na secção "Códigos de Erro".
