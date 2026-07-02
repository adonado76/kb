---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de soma"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/sum.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de soma

Retorna a soma total dos valores na coluna numérica especificada.

## Sintaxe

`Sum(column)`

## Argumentos

*coluna* : A coluna numérica a ser somada. Opcional

## Tipo de retorno

Número

## Exemplos

A tabela a seguir mostra os resultados quando a coluna Sum contém a função =Sum(Value):

| Grupo | Valor | Soma |
| --- | --- | --- |
| A | 4 | 108 |
| A | 8 | 108 |
| B | 15 | 108 |
| B | 16 | 108 |
| B | 23 | 108 |
| C | 42 | 108 |

A tabela agrupada a seguir mostra os resultados quando a coluna Sum (Soma) contém a função =Sum(Value):

| Grupo | Valor | .Contagem | Soma |
| --- | --- | --- | --- |
| A | 12 | 2 | 108 |
| B | 54 | 3 | 108 |
| C | 42 | 1 | 108 |

## Possíveis resultados enganosos

A função Sum pode resultar em resultados tecnicamente corretos, mas enganosos. Por exemplo, suponha que você tenha a seguinte tabela:

| Data center | Número ofServers | Custo total | Custo por servidor |
| --- | --- | --- | --- |
| Leste | 1 | US$ 100 | US$ 100 |
| Oeste | 4 | US$ 200 | US$ 50 |
| Total | 5 | US$ 300 | $60 |

A coluna Custo por servidor é calculada dividindo-se o custo total pelo número de servidores. O valor de Custo por servidor na linha Total também é calculado com base em 5 servidores com um custo total de US$ 300: US$ 300/5 = US$ 60.

Se você usar a função Sum (soma) para a coluna Cost per Server (custo por servidor), obterá o seguinte resultado:

| Data center | Número ofServers | Custo total | Custo por servidor |
| --- | --- | --- | --- |
| Leste | 1 | US$ 100 | US$ 300 |
| Oeste | 4 | US$ 200 | US$ 300 |
| Total | 5 | US$ 300 | $60 |

`Sum(Cost)` : Retorna o total de todos os valores da coluna {Cost}.
