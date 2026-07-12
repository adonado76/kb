---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Introdução a fórmulas e funções"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/introduction-to-formulas-and-functions.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Introdução a fórmulas e funções

**Aplica-se a** : TBM Studio 12.0 e posterior

Você pode usar fórmulas para inserir valores calculados em uma coluna de tabela ou em uma métrica. Uma função é um procedimento predefinido que pode ser usado em uma fórmula para simplificar a codificação de cálculos complexos.

Usar fórmulas e funções em:

- Os campos **Value**, **Value Override** e **Possible Values** de uma coluna do conjunto de dados.
- O campo **Cálculo de valor** para uma métrica.
- A barra de fórmulas na faixa de opções **Relatório**.
- Uma definição de driver de unidade.

## Fórmulas

Uma expressão é uma combinação de símbolos e operadores que podem ser avaliados para obter um único valor de dados. As expressões simples podem ser uma única constante, variável, coluna ou função escalar. Os operadores podem ser usados para unir duas ou mais expressões simples em uma expressão complexa.

Uma expressão pode incluir qualquer um dos seguintes elementos:

- Constantes
- Nome da coluna
- Fórmulas
- Funções

Uma expressão de cadeia de caracteres é avaliada como uma cadeia de caracteres. Uma expressão numérica é avaliada como um número. Uma expressão de data é avaliada como uma data. Muitas funções recebem expressões como argumentos.

O formato das fórmulas é:

`=expression`

O exemplo a seguir é uma fórmula simples que multiplica o valor na coluna **Rate (Taxa)** pelo valor na coluna **Time (Tempo** ).

`=Rate*Time`

## Funções

Uma função é um procedimento predefinido que insere um valor em uma tabela ou modelo. O formato das funções é:

`=Function_Name(arguments)`

Os nomes das funções são exibidos em MixedCase,, mas não diferenciam maiúsculas de minúsculas. Os argumentos representam os dados de entrada que a função requer. O exemplo a seguir mostra uma chamada à função Max, com os argumentos necessários, que, nesse caso, são nomes de colunas. Essa função avalia os valores nas colunas SalesEast e SalesWest e retorna o maior dos dois valores.

`=Max(SalesEast,SalesWest)`

Para obter descrições detalhadas de todas as funções, consulte [Funções - lista anotada](functions/functions.htm "(Abre em uma nova guia ou janela)").

## Onde as funções podem ser usadas

As funções podem ser usadas em vários lugares diferentes no site TBM Studio:

- Conjuntos de dados
- Métricas calculadas e relatórios com colunas de métricas
- Colunas de fórmula em tabelas de relatórios
- Texto Dinâmico
- Fórmulas de fontes de alocação

As descrições das funções incluem uma lista dos locais formalmente suportados onde uma função pode ser usada. Uma função pode funcionar em outro lugar, mas seu comportamento será inconsistente.
