---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "PreviousMonth função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/previousmonth.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# PreviousMonth função

Retorna o valor de uma métrica especificada do mês anterior na mesma tabela. Útil para comparar os valores atuais com os do mês anterior.

## Sintaxe

`PreviousMonth(metric)`

## Parâmetros

*métrica* : Uma métrica na mesma tabela. A função retorna o valor dessa métrica para o mês anterior.

## Tipo de retorno

Número

## Exemplo

- Para uma data atual de agosto de 2012, o exemplo a seguir retorna o valor de Custo para julho de 2012. `PreviousMonth(Cost)`
- Calcula a mudança mês a mês no custo. `Cost -
  PreviousMonth(Cost)`

Observação: essa função opera no contexto da tabela atual e não faz referência a tabelas externas. Se não houver dados para o mês anterior, a função retornará nulo.
