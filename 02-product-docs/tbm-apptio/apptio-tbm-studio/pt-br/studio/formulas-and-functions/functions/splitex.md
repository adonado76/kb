---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "SplitEx função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/splitex.html"
images:
  - "resources/images/studio_images/studioimages/studio_splitex-function_separate-row.png"
  - "resources/images/studio_images/studioimages/studio_splitex_formulas.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# SplitEx função

Divide uma cadeia de caracteres em uma coluna em várias linhas com base em um ou mais caracteres delimitadores. Cada segmento da divisão se torna uma linha separada no conjunto de dados transformado. Se uma coluna em seus dados contiver vários valores separados por um caractere, como uma vírgula, e você quiser gerar uma linha separada para cada valor, use a função SplitEx. Por exemplo, suponha que você tenha a tabela mostrada abaixo:

![amostra ex f dividida](../../../resources/images/studio_images/studioimages/studio_splitex_state%20and%20city.png)

Você deseja gerar uma linha separada para cada cidade, conforme mostrado abaixo:

![amostra ex f dividida](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_splitex-function_separate-row.png)

Insira a fórmula mostrada abaixo para a coluna **City** :

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_splitex_formulas.png)

![amostra ex f dividida]()

## Sintaxe

`Split(column,delimiter)`

## Parâmetros

*coluna* : A coluna em uma tabela a ser dividida.

*delimitador* : Um ou mais caracteres usados para dividir a cadeia de caracteres. Os delimitadores devem ser colocados entre aspas duplas. Por exemplo, ";>/" usa ponto e vírgula, maior que e barra como delimitadores. Necessário

## Tipo de retorno

Sequência

## Exemplos

`SplitEx(City, ",")`: Divide a coluna {City} em vírgulas. Por exemplo:

**Entrada:**

| Estado | Cidade |
| --- | --- |
| Washington | Seattle, Tacoma, Spokane |
| Califórnia | Los Angeles, São Francisco, São Diego |

**Saída:**

| Estado | Cidade |
| --- | --- |
| Washington | Seattle |
| Washington | Tacoma |
| Washington | Spokane |
| Califórnia | Los Angeles |
| Califórnia | São Francisco |
| Califórnia | São Paulo |

`SplitEx(Items, ";>/")`: Divide a coluna {Items} usando ponto e vírgula, maior que ou barra como delimitadores.
