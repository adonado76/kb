---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "IsNumeric função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/isnumeric.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# IsNumeric função

Avalia uma expressão para determinar se é um número válido, retornando 'true' ou 'false' como uma cadeia de caracteres.

## Sintaxe

*IsNumeric("value")*

ou

*IsNumeric({column nome})*

`IsNumeric(expression)`

## Parâmetros

*valor*

A cadeia de caracteres a ser avaliada. Ele deve ser colocado entre aspas.

*{column name}*

O nome de uma coluna em uma tabela.

## Comportamento

- Verifica se a expressão fornecida é avaliada como um valor numérico.
- Retorna a string 'true' se o valor for um número.
- Retorna a string 'false' se o valor não for um número.
- Pode avaliar cadeias de caracteres entre aspas e referências de coluna.
- Ignora caracteres não numéricos, como '%', ao determinar a validade numérica.

## Tipo de retorno

A função retorna o booleano **true** ou **false**.

## Comentários

Você pode usar a função dentro da função IF em ambos os lados da equação e na função STATUSICON.

Por exemplo:

```
IF(IsNumeric("423"),"OK","Check for
        error.")
```

`STATUSICON(IsNumeric("123"), LEN(TRIM(" hello ")) = 5 )`

## Exemplos

Os exemplos a seguir são mostrados com seus valores de retorno.

- `IsNumeric("95")` = verdadeiro
- `IsNumeric("95%")`= verdadeiro
- `IsNumeric("95 Percent")` = falso
- `IsNumeric({Location})` = falso
- `IsNumeric({345})`= verdadeiro

Observação: use aspas ao redor de cadeias literais ao avaliar valores constantes. Ao usar nomes de colunas, coloque-os entre chaves { }.
