---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função trunc"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/trunc.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função trunc

Trunca um número real removendo sua parte fracionária.

## Sintaxe

`Trunc(value)`

## Parâmetros

*valor* : O valor numérico a ser truncado. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

## Tipo de retorno

Número

## Exemplos

| Função de exemplo | Valor de Retorno |
| --- | --- |
| =Trunc( 1.23 ) | 1 |
| =Trunc( 1.985 ) | 1 |
| Trunc( -2.75 ) | -2 truncando em direção a zero. |
| Trunc( {Usage Hours} ) | Trunca os valores da coluna {Usage Hours} em sua parte inteira. |

Observação: ao contrário das funções de arredondamento, o Trunc simplesmente corta a parte decimal em vez de ajustar o número para cima ou para baixo. Útil para cálculos em que você precisa aplicar valores inteiros sem arredondamento.
