---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "SmallIf função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/smallif.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# SmallIf função

Retorna o menor valor em um grupo com base em uma categoria especificada e em critérios opcionais.

## Sintaxe

`SmallIf(category_column, value_column, [criteria])`

## Argumentos

*category\_column* : A coluna usada para agrupar os dados. Necessário

*value\_column* : A coluna que contém os valores a serem avaliados quanto ao valor mínimo em cada categoria. Necessário

*critérios* : Opcional. Um nome de coluna, valor de texto ou valor numérico usado para filtrar a categoria. Se não for especificado, será usado o valor da coluna category\_column da linha atual. Opcional (padrão: valor da linha atual em category\_column)

## Comportamento

- Agrupa as linhas de acordo com a coluna category\_column especificada.
- Filtra as linhas usando os critérios fornecidos (se houver).
- Retorna o menor valor da coluna value\_column que corresponde aos critérios do grupo.

## Tipo de retorno

Número

## Exemplo 1: SmallIf com um critério especificado

| Item | Categoria | Comparar categoria | Preço médio | SmallIf |
| --- | --- | --- | --- | --- |
| A | Gato ABC | Gato DEF | 22 | 6 |
| D | Gato DEF | Gato ABC | 6 | 22 |
| E | Gato DEF | Gato ABC | 7 | 22 |
| F | Gato DEF | Gato ABC | 8 | 22 |

`=SmallIf(Category, Average Price, Compare Category)`

## Exemplo 2: SmallIfwithout um critério especificado

| Item | Categoria | Preço médio | SmallIf |
| --- | --- | --- | --- |
| A | Gato ABC | 22 | 22 |
| D | Gato DEF | 6 | 6 |
| E | Gato DEF | 7 | 6 |
| F | Gato DEF | 8 | 6 |

`=SmallIf(Category, Average Price)`

`SmallIf(Region, Weight, Weight)` peso: Retorna o menor peso em cada região em que a região corresponde ao valor da linha atual.

`SmallIf(Department, Budget, "Finance")` valor de orçamento: Retorna o menor valor de orçamento para linhas no departamento "Finanças".

`SmallIf(Category, Amount)` : Retorna o menor valor para a categoria de cada linha.
