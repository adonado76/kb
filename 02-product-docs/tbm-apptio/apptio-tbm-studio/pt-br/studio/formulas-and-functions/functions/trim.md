---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função Trim"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/trim.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função Trim

Remove os espaços à esquerda e à direita de uma cadeia de caracteres especificada. Ele não remove espaços em uma cadeia de caracteres.

## Sintaxe

`Trim(expression[, trimUnicodeWhitespace][, additionalCharacters])`

## Parâmetros

- *expressão* : A cadeia de caracteres a ser cortada. Os espaços em branco à esquerda e à direita serão removidos. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário
- *trimUnicodeWhitespace* : Opcional. Um valor booleano (verdadeiro ou falso) que especifica se todos os caracteres de espaço em branco Unicode devem ser aparados. Se omitido, o padrão é false. Opcional (padrão: false)
- *additionalCharacters* : Opcional. Uma cadeia de caracteres adicionais a ser removida de ambas as extremidades da entrada. Isso além dos espaços em branco. Deve ser colocado entre aspas duplas (por exemplo, "\*"). Opcional

## Comportamento

- Remove os espaços em branco padrão ou Unicode do início e do fim da cadeia de caracteres de entrada.
- Não altera espaços em branco ou caracteres localizados no corpo da cadeia de caracteres.
- Se forem especificados caracteres adicionais, eles também serão removidos de ambas as extremidades da cadeia de caracteres.

## Tipo de retorno

Sequência

## Exemplos

| Exemplo de função | Valor de retorno |
| --- | --- |
| =Trim(" servidor" ) | servidor (sem espaços iniciais) |
| =Trim("servidor ") | servidor (sem espaços finais) |
| =Trim("servidor xyz") | servidor xyz |
| Trim( {Description}, true, "\*") | Remove espaços em branco Unicode à esquerda/à direita e asteriscos dos valores da coluna {Description}. |

Observe no terceiro exemplo que os espaços não são removidos entre o texto dentro da cadeia de caracteres.
