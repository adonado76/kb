---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função média"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/average.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função média

Retorna o valor médio em uma coluna ou métrica especificada.

## Sintaxe

`Average(column)`

## Argumentos

*operador de rollup*

@, SOURCE, ~ ou TARGET. Esse argumento é opcional e usado somente com métricas. Consulte [Operadores de rollup](../operators.html "Aplica-se a: TBM Studio 12.0 e posterior").

*coluna* : O nome da coluna ou métrica para a qual será calculada a média. Opcional

## Tipo de retorno

Número

## Exemplo

`Average(Budget)`retorna o valor médio da coluna "Orçamento".

`Average(Financials:Expense)`: Retorna o valor médio da coluna "Expense" (Despesa) na tabela "Financials" (Finanças).

Observação: Você pode especificar apenas uma coluna ou uma tabela e uma coluna juntas usando um separador de dois pontos. A função ignora valores nulos e valores não numéricos ao calcular a média.
