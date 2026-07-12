---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função máxima"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/max.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função máxima

Compara duas expressões e retorna o maior valor.

## Sintaxe

`Max(numeric_expression1, numeric_expression2)`

## Argumentos

*numeric\_expression (expressão numérica* ): numeric\_expression1: O primeiro valor ou expressão numérica a ser comparada. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

*numeric\_expression2* : O segundo valor ou expressão numérica a ser comparada. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

## Comportamento

- Avalia ambas as expressões numéricas e retorna a maior das duas.
- Oferece suporte a expressões ou funções aninhadas como parâmetros de entrada.
- Retorna o valor exato da expressão maior sem modificação.

## Tipo de retorno

Número

## Exemplo

O exemplo a seguir contém argumentos complexos em uma função Max. O primeiro argumento é 42 vezes o valor em Hours. O segundo argumento é o maior de 3 e 7, que é 7. Assim, se Hours for 3, o primeiro argumento será avaliado como 126, que é maior que 7, portanto, a função retorna 126.

`=Max(42*{Hours},Max(3,7))`

`Max(10, 20)`: Retorna 20 porque é o maior dos dois números.

`Max({Planned Hours}, {Actual Hours})`: Retorna o maior valor entre as colunas {Planned Hours} e {Actual Hours} para cada linha.

Nota:

- Útil para definir limites superiores ou determinar valores de pico entre duas métricas.
- Ambos os parâmetros devem ser numéricos ou ser resolvidos com expressões numéricas.
- Se quiser encontrar o valor máximo em uma coluna, use a função Large.
