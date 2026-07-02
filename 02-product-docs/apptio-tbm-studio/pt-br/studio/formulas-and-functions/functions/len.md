---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função Len"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/len.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função Len

Retorna o número de caracteres em uma determinada cadeia de caracteres, incluindo espaços.

## Sintaxe

`Len(string_expression)`

## Parâmetros

*string\_expression* : O valor a ser avaliado. Pode ser uma cadeia de caracteres literal, uma referência de coluna ou uma expressão concatenada. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

## Comportamento

- Avalia a expressão fornecida e retorna o número total de caracteres no resultado.
- Conta todos os caracteres, inclusive espaços em branco e pontuação.

## Tipo de retorno

Número

## Exemplos

- No exemplo a seguir, se a coluna Ticket Description da linha atual contiver a string Hardware, a função retornará 8, que é o número de caracteres da string Hardware.`=Len({Ticket Description})`
- No exemplo a seguir, a string Support é adicionada à expressão. Portanto, se a coluna Ticket Description da linha atual contiver a string Hardware, a função retornará 15, que é o número de caracteres da string Hardware (8) mais o número de caracteres da string Support (7).`=Len("Support"+Ticket Description)`
