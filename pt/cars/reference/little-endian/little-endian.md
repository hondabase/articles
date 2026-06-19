---
summary: 'Little Endian é o esquema de disposição de valores multibyte em memória utilizado por muitos processadores, incluindo os Intel x86 e os OKI 66k.'
tags: [referência]
complexity: beginner
---

# Little Endian

Little Endian é um esquema de disposição de valores multibyte em memória, utilizado por muitos processadores, incluindo os Intel x86 e os OKI 66k.

> [!IMPORTANT]
> A disposição Little Endian armazena o **byte menos significativo primeiro**.

Para valores de 16 bits, o valor real é calculado como: `Segundo Byte * 256 + Primeiro Byte`.
