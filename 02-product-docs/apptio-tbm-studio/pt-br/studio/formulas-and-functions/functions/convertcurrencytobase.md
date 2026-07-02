---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "ConvertCurrencyToBase função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/convertcurrencytobase.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ConvertCurrencyToBase função

Converte um valor para a moeda base, dividindo-o pela taxa correspondente da tabela Câmbio de moedas.

## Sintaxe

`ConvertCurrencyToBase(source column, currency code, rate type)`

## Parâmetros

*coluna de origem* : Uma cadeia de texto que especifica o código de moeda ISO (por exemplo, "EUR") que identifica a moeda de destino. Necessário

*código da moeda* : Uma cadeia de texto que especifica o código de moeda ISO (por exemplo, "EUR") que identifica a moeda de destino. Necessário

*tipo de taxa* : Uma cadeia de texto que especifica o tipo de taxa a ser usada na tabela Currency Exchange (por exemplo, "Plan"). Necessário

## Comportamento

- Procura a taxa de câmbio na tabela Currency Exchange que corresponde ao código de moeda e ao tipo de taxa fornecidos.
- Multiplica o valor de origem pela taxa correspondente para converter o valor da moeda base para a moeda especificada.
- Se nenhuma taxa correspondente for encontrada, a função retornará zero.

## Tipo de retorno

Número

## Exemplos

`ConvertCurrencyToBase(Expense, "EUR", "Plan")`: Converte o valor na coluna Despesa de euros para a moeda base usando o tipo de taxa "Plano".

`ConvertCurrencyToBase(SalesAmount, "JPY", "Actual")`: Converte o SalesAmount de ienes japoneses para a moeda base usando o tipo de taxa "Real".

Observação: é uma prática recomendada converter todos os valores financeiros em uma moeda comum antes de usá-los em drivers ou relatórios. Normalmente usado em uma coluna de transformação para garantir a representação consistente da moeda em todos os conjuntos de dados.
