---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função redonda"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/round.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função redonda

Arredonda um número real para um número especificado de casas decimais usando o algoritmo "round-half-up". Isso significa que os valores que terminam em 0,5 são arredondados para longe de zero.

## Sintaxe

`Round(numeric_expression, digits)`

## Argumentos

*numeric\_expression (expressão numérica* ): Uma expressão que é avaliada como o número a ser arredondado. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

*dígitos* : Uma expressão inteira que especifica o número de casas decimais a serem arredondadas. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

## Comportamento

- Arredonda o valor de entrada para o número especificado de casas decimais.
- Usa o algoritmo "round-half-up": os valores que terminam em 0,5 são arredondados para longe de zero.
- Se os dígitos forem zero, o valor será arredondado para o número inteiro mais próximo.

## Tipo de retorno

Número

**Exemplos básicos** :

| Função de exemplo | Valor de Retorno |
| --- | --- |
| =Round( 1.23,1) | 1.2 |
| =Round( 1.23,0) | 1 |
| =Round( 1.57,1) | 1.6 |
| =Round( 1.452,0) | 1 |
| Round( -23.5, 0) | -23, pois o arredondamento se afasta de zero para valores de 0,5. |

## Incorporação de uma função

Suponha que você tenha o seguinte conjunto de dados:

| A | B |
| --- | --- |
| 3 | 2 |
| 6 | 11 |
| 5 | 7 |
| 4 | 9 |

Você deseja dividir a coluna A pela coluna B e arredondar para duas casas decimais, colocando o resultado na coluna C. Você insere o seguinte no campo Valor da coluna C:

`=Round((A/B),2)`

O resultado é a tabela a seguir:

| A | B | C |
| --- | --- | --- |
| 3 | 2 | 1.5 |
| 6 | 11 | 0.55 |
| 5 | 7 | 0.71 |
| 4 | 9 | 0.44 |
