---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Sintaxe para fórmulas e funções"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/syntax-for-formulas-and-functions.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Sintaxe para fórmulas e funções

**Aplica-se a** : TBM Studio 12.0 e posterior

Além das convenções básicas de sintaxe para fórmulas e códigos de função, a sintaxe da função inclui regras para:

- **Pesquisa de dados** - Faz referência à tabela atual (pesquisa interna) e a outras tabelas (pesquisa externa).
- **Referência a nomes de colunas** - Ao fazer referência a nomes de colunas, a melhor prática é colocá-los entre chaves, o que é necessário quando os nomes de colunas contêm caracteres especiais.
- **Operadores** - Há suporte para operadores padrão e operadores de rollup, que fazem referência às unidades de origem ou destino de um rollup de dados.
- **Concatenação de str** ings - Você pode formatar fórmulas para incluir strings combinadas, como unidades de medida, com valores calculados.

## Convenções de sintaxe

As informações abaixo empregam as seguintes convenções para descrever a sintaxe da função.

- **Monoespaço** - Este documento apresenta toda a sintaxe da função em monoespaço.
- **MixedCase monospace** - Os nomes das funções são exibidos em MixedCase,, mas não diferenciam maiúsculas de minúsculas.
- **[ ] (colchetes)** - Elementos opcionais. (Não digite os colchetes)
- **,...n** - Indica que o argumento anterior pode ser repetido qualquer número de vezes, separado por vírgulas.

## Espaços

Não coloque espaços nas fórmulas, exceto como parte de uma cadeia de caracteres entre aspas ou conforme necessário nos nomes das colunas. Neste documento, as especificações de sintaxe podem incluir espaços para melhorar a legibilidade, mas todos os exemplos são fornecidos sem espaços. A sintaxe nesses documentos de ajuda utiliza fonte monoespaçada e espaços para melhorar a legibilidade. No entanto, os espaços não devem ser usados ao escrever fórmulas e funções no aplicativo.

## Cordas

Coloque todas as cadeias de caracteres entre aspas duplas ( " " ).

Por exemplo:

"Custos totais para o ano de 2009"

Os nomes das colunas não são considerados cadeias de caracteres e não precisam ser colocados entre aspas duplas.

Para escapar de um símbolo de citação, use aspas duplas ("" "").

## Valores de retorno nulos

As funções que resultam em 0 ou nulo são exibidas como 0 no campo.
