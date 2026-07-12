---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função Abs"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/abs-function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função Abs

Retorna o valor absoluto de um número ou expressão, removendo qualquer sinal negativo.

## Sintaxe

`Abs(expression)`

## Parâmetros

**expressão** : Um valor numérico ou uma fórmula que é avaliada como um número. Pode incluir variáveis, constantes ou outras funções. Opcional

## Tipo de retorno

Número

Se o resultado da expressão for negativo, o Abs o converterá em um número positivo. Se o resultado for positivo, ele permanecerá inalterado.

## Exemplos

**Abs(-5)**

Devoluções 5

**Abs(Soma(Orçamento) - Soma(Custo))**

Retorna a diferença absoluta entre o orçamento total e o custo

**Abs(Preço \* Quantidade)**

Retorna o valor absoluto do produto do preço e da quantidade

Observação: você pode passar um número simples, uma referência de coluna ou uma fórmula completa como argumento.
