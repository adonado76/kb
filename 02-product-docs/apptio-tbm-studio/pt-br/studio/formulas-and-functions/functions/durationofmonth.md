---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "DurationOfMonth função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/durationofmonth.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# DurationOfMonth função

A função DurationOfMonth retorna o número de dias, horas, minutos, segundos ou milissegundos em um mês para um ano específico. Ele leva em conta os anos bissextos.

## Sintaxe

```
DurationOfMonth (time_unit [, month [, year]])
```

## Tipo de retorno

Número

## Parâmetros

- *time\_unit* : Especifica a unidade de tempo a ser retornada. Valores suportados: 'd' para dias, 'h' para horas, 'm' para minutos, 's' para segundos, 'S' para milissegundos. Necessário
- *mês* : Opcional. Uma expressão que é avaliada como o mês (1-12). Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Opcional (padrão: mês atual)
- *ano* : Opcional. Uma expressão que é avaliada como o ano. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Opcional (padrão: ano atual)

## Exemplos

- Retorna 29 porque fevereiro de 2024 tem 29 dias (ano bissexto):`=DurationOfMonth("d", 2,
  2024)`
- Retorna o número de horas no mês atual:`=DurationOfMonth("h")`

Observação: Unidades de tempo compatíveis: "d" (dia), "h" (hora), "m" (minuto), "s" (segundo), "S" (milissegundo). Se o mês ou o ano forem omitidos, a data atual será usada como padrão.
