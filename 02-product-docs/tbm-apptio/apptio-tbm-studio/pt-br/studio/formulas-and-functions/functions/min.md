---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função mínima"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/min.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função mínima

Compara duas expressões numéricas e retorna o menor valor.

## Sintaxe

`Min(numeric_expression1, numeric_expression2)`

## Parâmetros

*expressão\_numérica 1 e 2*

O valor numérico ou a expressão a ser comparada. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Obrigatório. Você deve inserir duas, e somente duas, expressões numéricas.

## Comportamento

- Avalia ambas as expressões numéricas e retorna a menor das duas.
- Oferece suporte a expressões ou funções aninhadas como parâmetros de entrada.
- Retorna o valor exato da expressão menor sem modificação.

## Tipo de retorno

Número

## Exemplo

`=Min(42*Hours,Min(3,7))`: Retorna o menor valor entre 42 vezes o valor em {Hours} ou 3 (já que Min(3, 7) é avaliado como 3).

`Min(10, 20)`: Retorna 10 porque é o menor dos dois números.

`Min({Planned Hours}, {Actual Hours})`: Retorna o menor valor entre as colunas {Planned Hours} e {Actual Hours} para cada linha.

Nota:

- Útil para definir limites inferiores ou determinar valores mínimos entre duas métricas.
- Ambos os parâmetros devem ser numéricos ou ser resolvidos com expressões numéricas.
- Se quiser encontrar o valor mínimo em uma coluna, use a função Small.
