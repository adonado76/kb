---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de energia"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/power.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de energia

Eleva um número de base especificado à potência de um expoente especificado, realizando um cálculo exponencial.

## Sintaxe

`Power(base, exponent)`

## Parâmetros

*base* : O valor de base numérica a ser elevado a uma potência. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

*expoente* : O expoente numérico ao qual a base será elevada. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

## Comportamento

- Eleva a base à potência do expoente (ou seja, base^exponente).
- Lida com expoentes positivos e negativos, incluindo valores fracionários.
- Retorna um resultado decimal (duplo), independentemente de as entradas serem inteiras ou flutuantes.

## Tipo de retorno

Número

## Exemplo

O exemplo a seguir eleva 2 à terceira potência, o que retorna 8.: `=Power(2,3)`

`Power(5, 0)`: Retorna 1 porque qualquer número elevado à 0ª potência é 1.

`Power({CPU Count}, 2)`: Eleva o valor da coluna {CPU Count} ao quadrado.

Observação: uma base de 0 com um expoente negativo é indefinida e resultará em um erro.
