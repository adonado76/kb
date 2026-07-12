---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de pesquisa"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/search.html"
images:
  - "resources/images/studio_images/studioimages/studio_diagram_search.png"
  - "resources/images/studio_images/studioimages/studio_search_string.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de pesquisa

Procura uma cadeia de caracteres especificada (*search\_string* ) em outra cadeia de caracteres (*in\_string* ) e retorna um valor que representa a posição na *in\_string*, contando da esquerda para a direita, do primeiro caractere da *search\_string*.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_search_string.png)

Opcionalmente, você pode especificar uma *starting\_position* para a pesquisa. A *starting\_position* é um valor inteiro que representa a posição na *in\_string*, contando da esquerda para a direita, para iniciar a pesquisa. A pesquisa é realizada da esquerda para a direita.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_diagram_search.png)

A pesquisa retorna um valor se encontrar a *search\_string* incorporada na *in\_string*. Por exemplo, ele encontrará torta em espiões. Se nenhuma correspondência for encontrada, ele retornará 0.

A pesquisa não é compatível com caracteres curinga.

A pesquisa não diferencia maiúsculas de minúsculas.

## Sintaxe

`Search(search_string, in_string, starting_position)`

## Argumentos

*search\_string* : A substring a ser pesquisada. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

*in\_string* : A cadeia de caracteres para pesquisar. Você também pode fornecer o nome de uma coluna. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

*starting\_position* : A posição a partir da qual a pesquisa será iniciada (índice baseado em 1). Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Opcional (padrão: 1)

## Tipo de retorno

Número

## Exemplos

- O exemplo a seguir retorna 7, que é a posição da letra " F" na primeira instância da *search\_string*.`=Search("Functional", "58762 Functional
  Actuals")`
- O exemplo a seguir retorna 19, que é a posição da letra "c" na primeira instância da *search\_string* depois que o deslocamento de 12 caracteres é feito.`=Search("c", "58762 Functional Actuals",
  12)`
- O exemplo a seguir retorna 0, porque a *search\_string* "99" não foi encontrada na *in\_string*.`=Search("99", "58762 Functional
  Actuals")`
- O exemplo a seguir usa funções de pesquisa aninhadas em uma função LEFT para capturar os dois primeiros octetos de um endereço IP.`=LEFT(IP, Search(."",IP,Search(."",IP)+1))`Como os octetos de IP podem conter de 1 a 3 dígitos, o argumento count da função LEFT deve ser um par de funções de pesquisa aninhadas que localizam o segundo ponto (. ) de cada endereço IP.

A pesquisa interna é realizada primeiro. Ele encontra o local do primeiro ponto e, com 1 adicionado, fornece um argumento *starting\_position* para a pesquisa externa que faz com que ela comece no caractere após o primeiro ponto. A pesquisa externa retorna a posição do segundo ponto, o que dá à função LEFT um argumento *de contagem* preciso para capturar os dois primeiros octetos do endereço.

Por exemplo, se a coluna IP contiver um valor de 10.10.1.113, a pesquisa interna retornará um valor de 3, ao qual será adicionado 1, retornando 4. O valor de retorno 4 é a *posição\_inicial* para a pesquisa externa, que retorna 6. O valor de retorno 6 é a *contagem* para a função LEFT, que retorna 10.10.

Esse exemplo é uma boa maneira de encontrar uma parte de um endereço IP, mas, ao pesquisar endereços IP completos, use a função [IPLOOKUP](iplookup.htm "(Abre em uma nova guia ou janela)").

Observação: A função de pesquisa não diferencia maiúsculas de minúsculas. Se você precisar de uma pesquisa que diferencie maiúsculas de minúsculas, use a função Localizar. Todos os parâmetros aceitam expressões (por exemplo, literais, colunas ou funções aninhadas).
