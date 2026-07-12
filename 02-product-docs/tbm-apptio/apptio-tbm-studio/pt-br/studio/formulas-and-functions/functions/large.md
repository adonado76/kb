---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função grande"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/large.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função grande

Retorna o maior valor em uma coluna especificada.

## Sintaxe

`Large([rollup_operator]column)`

## Parâmetros

*operador de rollup*

@, SOURCE, ~ ou TARGET. Esse argumento é opcional e usado somente com métricas. Consulte [Operadores de rollup](../operators.html "Aplica-se a: TBM Studio 12.0 e posterior").

*coluna* : A coluna para pesquisar o maior valor. Você pode especificar um prefixo de tabela usando TableName:ColumnName. Necessário

## Comportamento

Examina a coluna especificada e retorna o maior valor (máximo).

## Tipo de retorno

Numérico

## Exemplo

*Large(Budget)* : Retorna o maior valor da coluna "Budget".

*Large(Financials:Cost)* : Retorna o maior valor da coluna "Cost" na tabela "Financials".
