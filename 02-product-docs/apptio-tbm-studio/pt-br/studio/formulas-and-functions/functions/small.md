---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função pequena"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/small.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu014.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função pequena

Retorna o menor valor em uma coluna especificada.

## Sintaxe

`Small([rollup_operator]column)`

## Parâmetros

*operador de rollup*

@, SOURCE, ~ ou TARGET. Esse argumento é opcional e usado somente com métricas. Consulte [Operadores de rollup](../operators.html "Aplica-se a: TBM Studio 12.0 e posterior").

*coluna* : A coluna para pesquisar o menor valor. Você pode especificar um prefixo de tabela usando TableName:ColumnName. Necessário

## Comportamento

Examina a coluna especificada e retorna o menor valor (mínimo).

## Tipo de retorno

Número

## Exemplos

![imagem de função pequena](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu014.png)

`=Small(@Desktop)`

`=Small(Desktop)`

`Small(Budget)`: Retorna o menor valor da coluna "Orçamento".

`Small(Financials:Cost)`: Retorna o menor valor da coluna "Cost" na tabela "Financials".
