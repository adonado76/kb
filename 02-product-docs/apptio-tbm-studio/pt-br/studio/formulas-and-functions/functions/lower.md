---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função inferior"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/lower.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função inferior

Converte a cadeia de caracteres de entrada em todas as letras minúsculas. caracteres

## Sintaxe

`Lower(expression)`

## Parâmetros

*expressão* : O texto a ser convertido em letras minúsculas. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

## Comportamento

- Recebe uma string de entrada e converte todos os caracteres alfabéticos em seus equivalentes em minúsculas.
- Os caracteres não alfabéticos (por exemplo, números, símbolos) são retornados sem alterações.
- Se a entrada já estiver em minúsculas, a string original será retornada.

## Tipo de retorno

Sequência

## Exemplos

| Função de exemplo | Valor de Retorno |
| --- | --- |
| =Menor("Orçamento para trabalhos de casa") | orçamento de hardware |
| =Lower( "hwBudget" ) | orçamento de hardware |
| Menor("Finanças") | finanças |
| Lower( {Department Name} ) | Converte todos os valores da coluna {Department Name} em letras minúsculas. |

Observação: útil para padronizar entradas de texto para comparações sem distinção entre maiúsculas e minúsculas ou formatação consistente.
