---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "PreviousYear função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/previousyear.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# PreviousYear função

Retorna a soma de uma métrica especificada na tabela atual para o número anterior de períodos em um ano fiscal. Em um calendário de 12 períodos, seriam 12 períodos. Em um calendário de 13 períodos, seriam 13 períodos.

## Sintaxe

`PreviousYear(metric)`

## Parâmetros

*métrica* : Uma métrica na mesma tabela.

## Comportamento

- Retorna o valor total da métrica especificada no ano fiscal anterior.
- O número de períodos somados é determinado pelas configurações do calendário (por exemplo, 12 períodos para calendários mensais, 13 para calendários fiscais 4-4-5).
- Os cálculos são relativos ao período de tempo atual no contexto.

## Tipo de retorno

Número

## Exemplo

- `=PreviousYear(Cost)`: Para a data atual de agosto de 2012, o exemplo a seguir retorna a soma de {Cost} de agosto de 2011 a julho de 2012.
- `Revenue - PreviousYear(Revenue)`: Calcula a diferença de receita ano a ano subtraindo o total do ano fiscal anterior do valor do período atual.

Observação: O número de períodos usados no cálculo depende da configuração do calendário (por exemplo, 12 ou 13).
