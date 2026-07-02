---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "ApptioOne Precisão"
breadcrumb: []
source_path: "studio/getting_started_with_tbm_studio/apptio-one-precision.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ApptioOne Precisão

Apptio usa a [https://en.wikipedia.org/wiki/IEEE\_754](https://en.wikipedia.org/wiki/IEEE_754 "(Abre em uma nova guia ou janela)") especificação para [https://en.wikipedia.org/wiki/Double-precision\_floating-point\_format](https://en.wikipedia.org/wiki/Double-precision_floating-point_format "(Abre em uma nova guia ou janela)") números para representar valores numéricos.

Esse padrão fornece cerca de 17 - log10(N ) dígitos de precisão (em que N é o número de valores somados) para a maioria das operações e 15 dígitos de precisão para outras operações. Embora o site Apptio retenha e exiba números com mais de 15 dígitos, esses números podem mudar entre compilações ou cálculos na mesma compilação, configuração ou dados.

Quando os números são arredondados, o site Apptio usa a regra de arredondamento [da metade para igualar](https://en.wikipedia.org/wiki/Rounding#Round_half_to_even "(Abre em uma nova guia ou janela)") o desempate (também conhecida como "bankers rounding"), que é o padrão para o IEEE 754.

Quando o Apptio soma valores, ele usa o [algoritmo Kahan Summation](https://en.wikipedia.org/wiki/Kahan_summation_algorithm "(Abre em uma nova guia ou janela)") para fornecer com eficiência a soma mais precisa possível.

Observe que o site Apptio adiciona um valor de fudge ( 0.00000001 ) a todos os números exibidos como Round() ou NumberFormat( ), para controlar o arredondamento de números de ponto flutuante.

Dessa forma, os números em Apptio são precisos até o menor valor:

- 15 dígitos significativos (dígitos antes e depois do ponto decimal) ou
- 7 casas decimais (dígitos após o ponto decimal)

Apptio exibe, por padrão, números com 3 casas decimais.

## Informações adicionais

Consulte a documentação de ajuda do site Apptio sobre [Sobre ponderação e números negativos](../model_studio/about-weighting-and-negative-numbers.html "aplica-se a: TBM Studio 11.8.3.1 e posterior; TBM Studio 12.0 e posterior. O objetivo de uma ponderação é alocar o número de origem onde a soma é a mesma no destino.").
