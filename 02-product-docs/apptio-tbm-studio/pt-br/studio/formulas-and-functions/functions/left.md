---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função esquerda"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/left.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função esquerda

Retorna um número especificado de caracteres de uma cadeia de caracteres (incluindo espaços em branco), começando pela esquerda.

## Sintaxe

`Left(string, count)`

## Parâmetros

*string* : A cadeia de caracteres da qual extrair caracteres. Você também pode usar uma referência de coluna. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

*count* : O número de caracteres a serem retornados da esquerda. Se o valor for uma cadeia de caracteres, ele será convertido em um número. Se a conversão falhar, o valor padrão será 0. Opcional (padrão: 1)

## Comportamento

Extrai caracteres do início da cadeia de caracteres de entrada com base na contagem. Se a contagem não for especificada, será retornado 1 caractere.

## Tipo de retorno

Sequência

## Exemplos

- Left("Seattle", 3): Retorna 'Sea'.
- Left(Name, 1): Retorna o primeiro caractere da coluna "Name".
- Left("Location"): Retorna 'L', pois nenhuma contagem é fornecida e o padrão é 1.

| Função de exemplo | Valor de Retorno |
| --- | --- |
| =Esquerda("123456",3) | 123 |
| =Esquerda("123456",1) | 1 |
| =Esquerda("123456") | 1 |
| =Esquerda("Eu gosto de torta.",6) | Eu gosto |
| =Esquerda("Eu gosto de torta.") | I |
