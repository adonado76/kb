---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "LargeIf função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/largeif.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LargeIf função

Retorna o maior valor em um grupo com base em uma categoria especificada e em critérios opcionais.

## Sintaxe

`LargeIf(category_column, value_column, criteria)`

## Parâmetros

*category\_column* : A coluna usada para agrupar os dados. Necessário

*value\_column* : A coluna que contém os valores a serem avaliados quanto ao valor máximo em cada categoria. Necessário

*critérios* : Opcional. Um nome de coluna, valor de texto ou valor numérico usado para filtrar a categoria. Se não for especificado, será usado o valor da coluna category\_column da linha atual. Opcional (padrão: valor da linha atual em category\_column)

## Comportamento

- Agrupa as linhas de acordo com a coluna category\_column especificada.
- Filtra as linhas usando os critérios fornecidos (se houver).
- Retorna o maior valor da coluna value\_column que corresponde aos critérios do grupo.

## Tipo de retorno

Número

## Exemplos

**Exemplo 1** : LargeIf com um critério especificado:

| Item | Categoria | Comparar categoria | Preço médio | LargeIf |
| --- | --- | --- | --- | --- |
| A | Gato ABC | Gato DEF | 22 | 8 |
| D | Gato DEF | Gato ABC | 6 | 22 |
| E | Gato DEF | Gato ABC | 7 | 22 |
| F | Gato DEF | Gato ABC | 8 | 22 |

`=LargeIf(Category, Average Price, Compare Category)`

**Exemplo 2** : LargeIf sem um critério especificado:

| Item | Categoria | Preço médio | LargeIf |
| --- | --- | --- | --- |
| A | Gato ABC | 22 | 22 |
| D | Gato DEF | 6 | 8 |
| E | Gato DEF | 7 | 8 |
| F | Gato DEF | 8 | 8 |

`=LargeIf(Category, Average Price)`: Retorna o maior valor para a categoria de cada linha.

`LargeIf(Region, Weight, Weight)`: Retorna o maior peso em cada região em que a região corresponde ao valor da linha atual.

`LargeIf(Department, Budget, "Finance")`: Retorna o maior valor de orçamento para linhas no departamento "Finanças".
