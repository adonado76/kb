---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "CurrentDate função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/currentdate.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# CurrentDate função

Retorna a data de início do período de tempo selecionado no momento, se o tempo estiver ativado. Caso contrário, retorna o Eon 2000.

## Sintaxe

`CurrentDate([format_string])`

## Parâmetros

*string\_de\_formato*

Especifica um formato de data personalizado para o valor de retorno, seguindo as mesmas convenções de [DateFormat](dateformat.html "Converte uma expressão de data em um formato de data especificado.") função. Opcional.

## Comportamento

- Retorna a data de início do período de tempo selecionado no momento.
- Se for fornecida uma format\_string, a saída será formatada de acordo; caso contrário, será usado um formato padrão.
- A função aceita zero ou um argumento.

## Exemplos

- `CurrentDate()`

  Retorna a data de início no formato padrão.
- `CurrentDate("yyyy-MM-dd")`

  Retorna a data de início formatada como "ano-mês-dia".

## Tipo de retorno

Sequência

Consulte também:

- [Horas](hours.html "Converte um valor de data no número de horas desde 1º de janeiro de 1970, como um valor numérico.")
- [Agora](now.html)
- [Minutos](minutes.html "Converte um valor de data no número de minutos desde 1º de janeiro de 1970, como um valor numérico.")
- [Meses](months.html "Converte uma data especificada em um valor decimal que representa o número de períodos desde 1º de janeiro de 1970. Útil para cálculos baseados em tempo, como determinação de durações ou custos proporcionais.")
