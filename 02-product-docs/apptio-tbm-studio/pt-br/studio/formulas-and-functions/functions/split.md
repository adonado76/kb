---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de divisão"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/split.html"
images:
  - "resources/images/studio_images/studioimages/studio/aug482.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de divisão

**Aplica-se a** : TBM Studio 12.0 e posterior

Retorna um elemento de uma cadeia de caracteres delimitada.

## Sintaxe

`Split(string,n[,delimiters])`

## Parâmetros

- string: A cadeia de caracteres para dividir e extrair um elemento. Normalmente, trata-se de uma referência de coluna. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário
- n: Um número inteiro que indica qual elemento deve ser retornado. Um número positivo conta a partir da esquerda; um número negativo conta a partir da direita. Necessário
- delimitadores: Opcional. Uma cadeia de caracteres delimitadores para dividir a cadeia. São permitidos vários caracteres (por exemplo, ";>/" usa ponto e vírgula, maior que e barra). Use um ponto (.) para representar um espaço. O padrão é "/-". Opcional (padrão: /-)
- ignoreAdjacentDelimiters: Opcional. Um booleano (verdadeiro ou falso) que indica se os delimitadores adjacentes devem ser tratados como um só. O padrão é true. Opcional (padrão: true)

## Tipo de retorno

Sequência

## Exemplos

Suponha que você tenha uma coluna em uma tabela que contém o nome e o sobrenome dos funcionários. Por exemplo: John Smith, Tom Jones, Sarah Brown. Você deseja separar o primeiro nome do sobrenome para produzir a tabela a seguir:

![função de divisão de imagem](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug482.png)

Para isso, você deve inserir as seguintes equações no campo **Value Override (Substituição de valor** ) para as colunas First Name (Nome) e Last Name (Sobrenome). O delimitador " " representa o espaço em branco entre o primeiro e o último nome.

| Coluna | Fórmula de substituição de valor |
| --- | --- |
| Nome | =Split( Name,1," ") |
| Sobrenome | =Split( Name,2," ") |

Abaixo estão outros exemplos da função Split.

| Exemplo de função | Valor de retorno |
| --- | --- |
| =Dividir("a/b/c/d",3,"/") | c |
| =Dividir("a,b,c,d",7,",") | Nulo |
| =Dividir("a&b&c&d",4,"&") | d |
| =Dividir("foo",1) | foo (a string inteira) |
| =Dividir("foo",2) | Nulo |
| =Dividir("a/b/c/d",-3) | b |

- `Split("Seattle, Tacoma, Spokane", 2, ",")`: Retorna " Tacoma" - o segundo item da lista separada por vírgulas.
- `Split("Region/US-East", -1)`: Retorna "East" - o último elemento dividido pelos delimitadores padrão "/-".
- `Split({City List}, 3, ",;")`: Divide os valores na coluna {City List} usando vírgula ou ponto e vírgula e retorna o terceiro elemento.

Observação: use valores negativos para n para contar os elementos a partir da direita. Se os delimitadores adjacentes devem ser ignorados (por exemplo, para evitar elementos em branco), defina ignoreAdjacentDelimiters como true.
