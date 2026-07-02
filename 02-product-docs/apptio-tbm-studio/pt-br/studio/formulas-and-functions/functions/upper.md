---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função superior"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/upper.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função superior

Converte a cadeia de caracteres de entrada em todos os caracteres maiúsculos.

## Sintaxe

`Upper(expression)`

## Parâmetros

*expressão* : O texto a ser convertido em maiúsculas. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

## Comportamento

- Recebe uma string de entrada e converte todos os caracteres alfabéticos em seus equivalentes em maiúsculas.
- Os caracteres não alfabéticos (por exemplo, números, símbolos) são retornados sem alterações.
- Se a entrada já estiver em maiúsculas, a string original será retornada.

## Tipo de retorno

Sequência

## Exemplos

| Função de exemplo | Valor de Retorno |
| --- | --- |
| =Upper("Orçamento para trabalhos de casa") | HWBUDGET |
| =Upper( "hwBudget" ) | HWBUDGET |

Observação: útil para padronizar entradas de texto para comparações sem distinção entre maiúsculas e minúsculas ou formatação consistente.
