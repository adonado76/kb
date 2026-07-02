---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "ApptioOne Precisão"
breadcrumb:
  - "TBM Studio"
  - "Administração"
source_path: "studio/new-uc/admin/apptio-one-precision.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ApptioOne Precisão

Apptio utiliza a especificação [IEEE 754](https://en.wikipedia.org/wiki/IEEE_754 "(Abre em uma nova guia ou janela)") para números [de ponto flutuante de precisão dupla](https://en.wikipedia.org/wiki/Double-precision_floating-point_format "(Abre em uma nova guia ou janela)") para representar valores numéricos.

Esta norma oferece aproximadamente 17 a log10(N ) dígitos de precisão (onde N é o número de valores somados) para a maioria das operações, e apenas 15 dígitos de precisão para certas outras operações. Assim, embora Apptio armazene e exiba números com mais de 15 dígitos, esses números podem variar entre versões ou entre cálculos realizados na mesma versão/configuração/dados.

Quando os números são arredondados, o Apptio utiliza a regra de desempate [que consiste](https://en.wikipedia.org/wiki/Rounding#Rounding_half_away_from_zero "(Abre em uma nova guia ou janela)") em arredondar para o número mais próximo do zero ( a.k.a. "arredondamento comercial").

Quando o ` Apptio ` soma valores, ele utiliza o [algoritmo de soma de Kahan](https://en.wikipedia.org/wiki/Kahan_summation_algorithm "(Abre em uma nova guia ou janela)") para fornecer, de forma eficiente, a soma mais precisa possível.

É importante observar também que a função ` Apptio ` adiciona um valor de ajuste ( 0.00000001 ) a todos os números exibidos por meio das funções `Round()` ou ` NumberFormat( ()`. Isso é feito para controlar o arredondamento de números de ponto flutuante.

Os números apresentados em Apptio são precisos até ao menor dos seguintes valores:

- 15 dígitos significativos (dígitos antes e depois da vírgula decimal) ou
- 7 casas decimais (dígitos após a vírgula)

Apptio Por padrão, exibe números com 3 casas decimais.
