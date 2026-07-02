---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de meses"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/months.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de meses

Converte uma data especificada em um valor decimal que representa o número de períodos desde 1º de janeiro de 1970. Útil para cálculos baseados em tempo, como determinação de durações ou custos proporcionais.

## Sintaxe

`Months(date_expression, format)`

## Argumentos

- *date\_expression* : Uma expressão que é avaliada como uma data a ser convertida em um valor duplo. O formato é: "MM/DD/YYYY HH:MM" ou qualquer outro formato de data padrão suportado pelo aplicativo. A expressão pode ser o nome de uma coluna.
- *format* : Um literal de cadeia de caracteres que especifica o formato da data (por exemplo, "MM/dd/yyyy"). Opcional se o formato da data for detectável automaticamente. Opcional

## Comportamento

- Retorna o número de períodos (meses) desde 1º de janeiro de 1970 como um número decimal.
- Os períodos parciais são incluídos como valores fracionários. Por exemplo, 1.1 representa um mês inteiro e parte de outro.
- Pode ser usado em fórmulas para calcular durações, alocar custos ou comparar prazos.

## Tipo de retorno

Número

## Exemplo

- `Months("01/01/1970")`: Retorna 1 porque é a data de referência.
- `Months("01/02/1970")`: Retorna 1.032.
- `Months({ProjectEnd}) - Months({ProjectStart})`: Calcula a duração em meses entre duas datas do projeto.
- `(Months({ProjectEnd}) - Months({ProjectStart}))*` Multiplica o número de meses entre as datas de início e término pelo custo mensal do projeto para estimar o custo total.

Nota:

- O resultado inclui meses parciais como valores decimais, o que o torna adequado para cálculos rateados.
- O formato de data é necessário somente se a entrada de data não puder ser analisada automaticamente pela plataforma.
- A função é baseada em 1º de janeiro de 1970 como referência de época.
