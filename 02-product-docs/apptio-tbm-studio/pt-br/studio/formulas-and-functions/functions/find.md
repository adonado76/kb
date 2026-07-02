---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Localizar função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/find.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Localizar função

Retorna a posição da primeira ocorrência de uma cadeia de caracteres de pesquisa em outra cadeia, começando em uma posição opcional. Essa função diferencia maiúsculas de minúsculas.

O Find é igual ao [Search](search.html), exceto pelo fato de que o Find diferencia maiúsculas de minúsculas.

## Sintaxe

`Find(search_string, in_string, [starting_position])`

## Parâmetros

- *search\_string* : A substring a ser pesquisada. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário
- *in\_string* : A cadeia de caracteres para pesquisar. Você também pode fornecer o nome de uma coluna. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário
- *starting\_position* : A posição a partir da qual a pesquisa será iniciada (índice baseado em 1). Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Opcional (padrão: 1)

## Comportamento

- Realiza uma pesquisa com distinção entre maiúsculas e minúsculas para uma substring dentro de outra string.
- Retorna a posição (começando em 1) da primeira correspondência encontrada.
- Retorna 0 se a substring não for encontrada.
- Se a posição\_inicial não for fornecida, a pesquisa começará a partir do início da cadeia de caracteres.
- A função se comporta como Search, mas diferencia maiúsculas de minúsculas.

## Exemplos

- Find("Functional", "58762 Functional Actuals"): Retorna 7, a posição da substring 'Functional'.
- Find("c", "58762 Functional Actuals", 12): Retorna 19, iniciando a pesquisa após o 12º caractere.
- Find("99", "58762 Functional Actuals"): Retorna 0, pois '99' não foi encontrado.
- LEFT(IP, Localizar(".", IP, Localizar(".", IP) + 1)): Retorna os dois primeiros octetos de um endereço IP. Por exemplo, para ' 10.10.1.113 ', o resultado é ' 10.10 '.

Observação: a função Localizar diferencia maiúsculas de minúsculas. Se você precisar de uma pesquisa sem distinção entre maiúsculas e minúsculas, use a função Pesquisar. Todos os parâmetros aceitam expressões (por exemplo, literais, colunas ou funções aninhadas).

## Tipo de retorno

Número
