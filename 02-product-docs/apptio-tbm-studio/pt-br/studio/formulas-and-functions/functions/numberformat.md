---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "NumberFormat função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/numberformat.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# NumberFormat função

Formata um valor numérico em um rótulo (string) usando padrões personalizados para números positivos e negativos, durações ou formatação de tamanho de dados. Essa função foi projetada para uso em colunas do tipo Label.

## Sintaxe

`NumberFormat(number, pattern, [options])`

## Parâmetros

- número: O valor numérico a ser formatado. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário
- padrão: Uma cadeia de caracteres que especifica o formato para números positivos e, opcionalmente, para números negativos separados por um ponto e vírgula (por exemplo, "#,###.#;(#,###.#)"). Opcional
- opções: Argumentos nomeados opcionais que controlam o comportamento de formatação adicional. As opções compatíveis incluem:
  - `compact`: Aplicar formatação abreviada (consulte a seção Referência de notação compacta abaixo para ver os valores suportados)
  - `negSymbol`: Use `dash`, `parens`, `none`, ou `default` para saber como os números negativos são exibidos
  - `posColor`, `negColor`: Define as cores da fonte usando códigos hexadecimais HTML (por exemplo, `#FF0000`)
  - `posBold`, `negBold`: Aplicar estilo em negrito (`true`, `false`)
  - `posItalic`, `negItalic`: Aplicar o estilo itálico (`true`, `false`)
  - `posUnderline`, `negUnderline`: Aplicar estilo de sublinhado (`true`, `false`)
  - `posPrefix`, `negPrefix`: Adicionar HTML/texto antes do número
  - `posSuffix`, `negSuffix`: Adicionar HTML/texto após o número Opcional

## Comportamento

- Converte uma entrada numérica em uma string formatada de acordo com o(s) padrão(ões) fornecido(s).
- Suporta arredondamento, símbolos de moeda, porcentagens, notação exponencial e abreviações de byte/bit.
- Pode converter durações (em segundos) em cadeias de caracteres formatadas como "2 horas, 2 minutos".
- Fornece formatação binária para tamanhos de dados usando códigos como XA, XK, etc.
- Aplica o arredondamento Half-Up: valores terminados em 1-4 arredondados para baixo, 5-9 arredondados para cima.
- Quando nenhum padrão é fornecido, os números são arredondados para números inteiros e exibidos com vírgulas.

## Exemplos

`NumberFormat({Revenue}, "$#,##0.00")`: Formata a coluna {Revenue} como moeda com duas casas decimais, por exemplo, "$1, 234.56 ".

`NumberFormat(7322, "s")`: Converte 7322 segundos em uma string de duração formatada: "2 horas, 2 minutos e 2 segundos".

`NumberFormat(922, "MB")`: Formata 922 MB em uma string legível por humanos, como " 0.9 GB".

`NumberFormat(Percent, "00%")`: Formata uma porcentagem com dois dígitos, por exemplo, 0.42 torna-se "42%".

`NumberFormat($_, "#,###.#B", compact="XA")`: Formata um valor de dados usando abreviação binária, por exemplo, " 1.0 GB".

`NumberFormat(-62619000.185, "#,###.#B;(#,###.##)")`: Formata o número negativo -62.619, 000.185 usando o padrão positivo `#,###.#B` e o padrão negativo `(#,###.##)`, resultando em `(62,619,000.19)`.

`NumberFormat({NetIncome}, "$#,##0.00", compact="M", negColor="#FF0000",
posBold=true)`: Formata a coluna {NetIncome} como moeda em milhões. Os números negativos aparecem em vermelho e os números positivos estão em negrito.

## Notas

- Use essa função somente em colunas do tipo Rótulo ou na fórmula de formato de novas colunas de métricas/relatórios.
- A formatação é ignorada em colunas numéricas.
- Se nem o padrão nem negativePattern forem fornecidos, os valores serão arredondados para o número inteiro mais próximo com separador de milhares.
- Quando a formatação incluir HTML, verifique se as tags de prefixo/sufixo estão equilibradas e válidas.

## Referência de notação compacta

As tabelas a seguir mostram os valores de notação compacta compatíveis. Nas tabelas, a coluna Código mostra os valores que você pode colocar após o parâmetro opcional compact=. A coluna Pattern for Charts (Padrão para gráficos) mostra as adições que você pode colocar no final do padrão de formato.

## Notações de taquigrafia padrão

Há suporte para as seguintes notações abreviadas padrão. Os símbolos exibidos para cada formato abreviado padrão são específicos de cada localidade e podem ser reconfigurados na caixa de diálogo de configurações do projeto. Assim, por exemplo, essa função de formato de número usaria todas as notações abreviadas padrão:

=NumberFormat($\_, “#.#”, compacto=A)

| Código | Padrão para gráficos | Descrição | Exemplo |
| --- | --- | --- | --- |
| K | {@K} | Isso sempre resumirá os números em termos de "milhares" | 100.000 é exibido como 100K |
| M | {@M} | Isso sempre resumirá os números em termos de "milhões" | 10.000.000 é exibido como 10M |
| B | {@B} | Isso sempre resumirá os números em termos de "bilhões" | 10.000.000.000 é exibido como 10B |
| T | {@T} | Isso sempre resumirá os números em termos de "trilhões" | 10.000.000.000.000 é exibido como 10T |
| A | {@A} | Isso resumirá os números usando todas as notações padrão. Para um determinado número, será usada a notação de ordem de magnitude mais alta possível, de modo que o número exibido seja maior ou igual a 1.0. Ou seja, {@A} exibirá 964.999 como 9.65K e não como 0.96M, pois 0.96 é menor que 1.0. Em caso de dúvida, esse costuma ser o melhor formato abreviado a ser usado. | Todos os exemplos acima são verdadeiros. |

## Notações de taquigrafia binária

Também há suporte para as seguintes notações binárias abreviadas:

Quando você usa abreviações binárias, na maioria das vezes está resumindo um número de bytes. Nesse caso, use isso como sua declaração NumberFormat :

=NumberFormat($\_, “#,###.#B”, compacto=“XA”)

Da mesma forma, para exibi-lo em um gráfico, digite isso como o formato do número do gráfico: #, ###.#B{@Xa }

| Código | Padrão para gráficos | Descrição | Exemplo |
| --- | --- | --- | --- |
| XK | {@XK} | Isso sempre resumirá os números em termos de "milhares binários" (dividir por 1024). | 1025 é exibido como 1k |
| XM | {@XM} | Isso sempre resumirá os números em termos de "milhões binários" (divida por 1024^2). | 1048577 é exibido como 1M |
| XG | {@XG} | Isso sempre resumirá os números em termos de "bilhões binários" (divida por 1024^3). | 1.073.741.825 é exibido como 1G |
| XT | {@XT} | Isso sempre resumirá os números em termos de "trilhões binários" (divida por 1024^4). | 1.099.511.627.777 é exibido como 1T |
| XP | {@XP} | Isso sempre resumirá os números em termos de "quadrilhões binários" (divida por 1024^5). | 1.125.899.906.842.625 é exibido como 1P |
| XE | {@XE} | Isso sempre resumirá os números em termos de "quintilhões binários" (divida por 1024^6). | 1.152.921.504.606.846.977 é exibido como 1e |
| XA | {@XA} | Isso resumirá os números usando todas as notações binárias. Para um determinado número, será usada a notação de ordem de magnitude mais alta possível, de modo que o número exibido seja maior ou igual a 1.0. Em caso de dúvida, esse costuma ser o melhor formato abreviado a ser usado. | Todos os exemplos acima são verdadeiros. |

## Tipo de retorno

Sequência
