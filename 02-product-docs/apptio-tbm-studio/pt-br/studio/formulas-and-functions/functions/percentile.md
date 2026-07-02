---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de percentil"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/percentile.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de percentil

Retorna o valor de percentil especificado para uma determinada coluna numérica. Um percentil representa o valor abaixo do qual uma determinada porcentagem dos dados se enquadra.

Retorna um percentil específico para uma coluna específica.

Para um determinado conjunto de números, um percentil é o valor abaixo do qual uma determinada porcentagem dos números se enquadra. Por exemplo, para uma coluna que contém 0, 1, 2, 3, 4, 5, 6, 7, 8 e 9, o 30º percentil é 2.3, que é o valor abaixo do qual 30% dos números estão (0,1,2). O valor da vírgula decimal 0,3 no resultado é derivado do valor que está 30% do caminho entre 2 e 3.

## Sintaxe

`Percentile([rollup_operator]column,percentage)`

## Argumentos

*operador de rollup*

@, SOURCE, ~ ou TARGET. Esse argumento é opcional e usado somente com métricas. Consulte [Operadores de rollup](../operators.html "Aplica-se a: TBM Studio 12.0 e posterior").

*coluna* : A coluna numérica da qual será avaliado o percentil. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

*porcentagem* : Um valor numérico que representa o limite do percentil (por exemplo, 50 para a mediana, 90 para o 90º percentil). Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

## Comportamento

Retorna o valor abaixo do qual a porcentagem especificada de dados se encontra. Interpola entre valores quando a posição exata do percentil fica entre dois pontos de dados.

## Tipo de retorno

Número

## Exemplo

O exemplo a seguir retorna o 50º percentil para os valores que contribuem para o rollup na coluna Servidores. Se os Servidores na tabela de origem contiverem: 500, 600, 700 e 1200, esse exemplo retornará 650.

`=Percentile(Servers,50)`: Retorna a mediana (50º percentil) dos valores na coluna {Servers}.

`=Percentile(Sales,90)`: Retorna o valor do 90º percentil da coluna {Sales}.

Observação: O resultado do percentil pode incluir um decimal se for necessária a interpolação entre dois valores. A porcentagem deve ser um número entre 0 e 100.
