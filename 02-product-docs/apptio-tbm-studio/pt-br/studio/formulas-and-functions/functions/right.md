---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função correta"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/right.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função correta

Retorna o número especificado de caracteres a partir do final (lado direito) de uma cadeia de caracteres, incluindo espaços em branco.

## Sintaxe

`Right(string[, count])`

## Argumentos

*string* : A cadeia de caracteres da qual serão extraídos os caracteres da direita. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

*count* : O número de caracteres a serem retornados da esquerda. Se o valor for uma cadeia de caracteres, ele será convertido em um número. Se a conversão falhar, o valor padrão será 0. Opcional (padrão: 1). Um número inteiro que especifica o número de caracteres a serem retornados. Se esse argumento não for especificado, o padrão será 1. Se esse argumento for avaliado como um rótulo ou uma cadeia de caracteres, o sistema tentará convertê-lo em um número. Se não for possível, o valor será zero.

## Comportamento

- Extrai caracteres a partir do lado direito da cadeia de caracteres de entrada.
- Retorna exatamente o número de caracteres especificado pelo parâmetro count.
- Se a contagem for maior que o comprimento da cadeia, a cadeia inteira será retornada.
- Se a contagem for omitida, 1 caractere será retornado por padrão.

## Tipo de retorno

Sequência

## Exemplos

| Função de exemplo | Valor de Retorno |
| --- | --- |
| =Direita("123456", 3) | 456 |
| =Direita("123456", 1) | 6 |
| =Direita("123456") | 6 |
| =Direita("Eu gosto de torta", 3) | pizza |
| Right( {Hostname}, 5) | Retorna os últimos 5 caracteres do valor na coluna {Hostname}. |
| Direita("rede") | Retorna "k", pois a contagem padrão é 1. |
| Direita("servidor", 3) | ver |
|  |  |

Observação: os espaços em branco são tratados como caracteres e incluídos no resultado.
