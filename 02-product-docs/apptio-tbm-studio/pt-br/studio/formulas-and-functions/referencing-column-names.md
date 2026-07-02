---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Referência a nomes de colunas"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/referencing-column-names.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Referência a nomes de colunas

**Aplica-se a** : TBM Studio 12.0 e posterior

Os nomes das colunas diferenciam maiúsculas de minúsculas e podem incluir espaços. Ao fazer referência a nomes de colunas, a melhor prática é colocá-los entre chaves, o que é necessário quando os nomes de colunas contêm caracteres especiais. Ao fazer referência a colunas agrupadas usando operadores de rollup, você pode fazer com que uma função avalie os valores que contribuíram para o rollup, em vez do valor do rollup.

## Regras gerais

Abaixo estão as regras gerais para fazer referência a colunas em conjuntos de dados.

| Para fazer referência a uma coluna em: | Use este formato: |
| --- | --- |
| o mesmo conjunto de dados ou tabela | {column name} |
| um conjunto de dados ou tabela diferente | {data set name}:{column name} |
| um conjunto de dados em um projeto diferente no mesmo domínio | nome do projeto! {data set name} : {column name} |
| um conjunto de dados em um projeto diferente em um domínio diferente | nome do domínio: nome do projeto! {data set name} : {column name} |

## Referência a nomes de colunas: caracteres especiais

Nas funções, se você fizer referência a um nome de coluna que contenha algum caractere especial, deverá colocar o nome da coluna entre chaves: { }.

A tabela a seguir lista os caracteres especiais.

| Caractere | Nome |
| --- | --- |
| & | E comercial |
| \* | Asterisco |
| @ | No sinal |
| ) | Fechar parênteses |
| : | Colón |
| , | Vírgula |
| = | Sinal de igual |
| ! | Ponto de exclamação |
| / | Barra para frente |
| - | Hífen |
| [ | Suporte esquerdo |
| ( | Abrir parênteses |
| . | Período |
| + | Sinal de mais |
| ] | Suporte direito |
| " | Aspas duplas retas |
| ~ | Tilde |

## Exemplo de nome de coluna com um caractere especial

Para fazer referência a um nome de coluna que contenha um asterisco (\*), como Hours\*Rate, coloque o nome da coluna entre colchetes { } para diferenciá-lo da fórmula Hours\*Rate, conforme mostrado no exemplo a seguir:

`Round({Hours*Rate},2)`

Você também deve usar chaves em torno do nome de uma coluna se ela contiver uma palavra-chave (nome de função). Por exemplo, o nome da coluna **Diff** contém **if**, que é o nome de uma função, portanto, você deve fazer referência a esse nome de coluna entre chaves: {Diff}.

**Prática recomendada:** Sempre coloque os nomes das colunas entre chaves.

## Referência a colunas agrupadas

Ao fazer referência a uma coluna agrupada, uma função avalia o valor acumulado do agrupamento. Entretanto, colocar um @ (sinal de arroba) antes do nome da coluna, como em (@coluna), faz com que algumas funções avaliem os valores que contribuíram para o rollup. O @ pode ser usado dessa forma com as seguintes funções: [Média](functions/average.html "Retorna o valor médio em uma coluna ou métrica especificada."), [Grande](functions/large.html "Retorna o maior valor em uma coluna especificada."), [Percentil](functions/percentile.html "Retorna o valor de percentil especificado para uma determinada coluna numérica. Um percentil representa o valor abaixo do qual uma determinada porcentagem dos dados se enquadra.") e [Pequeno](functions/small.html "Retorna o menor valor em uma coluna especificada.").

Por exemplo, considere as tabelas a seguir. A tabela a seguir mostra uma tabela antes do agrupamento.

| c | c1 |
| --- | --- |
| a | 1 |
| a | 2 |
| a | 3 |
| b | 4 |
| b | 5 |
| b | 6 |
| c | 7 |
| c | 8 |
| c | 9 |

O agrupamento dos dados da tabela acima pela coluna c fornece os resultados mostrados na tabela abaixo. A coluna c1 agora contém as somas de unidades distintas na coluna c. A tabela também contém uma nova coluna chamada.Count, que contém o número de linhas em cada grupo.

| **c** | **c1** | **.Contagem** |
| --- | --- | --- |
| a | 6 | 3 |
| b | 15 | 3 |
| c | 24 | 3 |

Colocar um sinal de arroba ( @ ) antes do nome da coluna faz com que determinadas funções avaliem os valores que contribuíram para o rollup (Tabela 1) para cada agrupamento. Chamar a função =Small( @c1 ) na tabela agrupada (Tabela 2) retorna o menor valor nos dados pré-rollup (Tabela 1) para cada grupo.

A tabela a seguir mostra os resultados quando a coluna c2 contém a função =Small( @c1 ).

| c | c1 | c2 | .Contagem |
| --- | --- | --- | --- |
| a | 6 | 1 | 3 |
| b | 15 | 4 | 3 |
| c | 24 | 7 | 3 |

## Palavras reservadas

Se um nome de coluna usado em uma fórmula corresponder exatamente às palavras a seguir ou começar com uma das palavras seguidas de um espaço, você deverá colocar o nome da coluna entre colchetes.

- se
- então
- mais
- terminar
- sub
- verdadeiro
- Não
- excluir

Por exemplo:

| **Antigo** | **Novo** |
| --- | --- |
| sub | {sub} |
| sub A | {sub A} |
| SUB b | {SUB b} |
| final x | {end x} |
