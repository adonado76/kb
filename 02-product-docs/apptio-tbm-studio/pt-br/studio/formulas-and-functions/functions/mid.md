---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função intermediária"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/mid.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função intermediária

Retorna um número específico de caracteres de uma cadeia de caracteres, começando em uma determinada posição a partir da esquerda.

## Sintaxe

Mid(string,início,contagem)

## Parâmetros

- *string* : A cadeia de texto da qual os caracteres serão extraídos. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário
- *start* : Um número inteiro que representa a posição do primeiro caractere a ser retornado, começando pelo caractere mais à esquerda (índice baseado em 1). Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário
- *count* : Um número inteiro que representa o número de caracteres a serem retornados. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

## Comportamento

- Extrai uma substring do texto de entrada com base na posição inicial e no comprimento fornecidos.
- A posição é baseada em 1, o que significa que Mid("abc", 1, 1) retorna "a".
- Se a contagem exceder o número de caracteres disponíveis a partir da posição inicial, ele retornará os caracteres até o final da cadeia de caracteres.

## Tipo de retorno

Sequência

## Exemplos

| Função de exemplo | Valor de Retorno |
| --- | --- |
| =Mid("123456", 2, 3) | 234 |
| =Mid("123456", 1, 2) | 12 |
| =Mid("123456", 4, 1) | 4 |
| =Mid("Eu gosto de torta.", 3, 4) | like - inicia na posição 3 e retorna 4 caracteres, incluindo espaços em branco. |
