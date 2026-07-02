---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "ReplaceRegex função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/replaceregex.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ReplaceRegex função

Executa uma substituição baseada em expressão regular em valores de texto em uma coluna. Útil para extrair ou limpar dados usando a correspondência avançada de padrões.

## Sintaxe

`ReplaceRegex(column_name, match_expression, replacement_expression)`

## Argumentos

*column\_name* : O nome da coluna que contém o texto a ser substituído.

*match\_expression* : A expressão regular que identificará o texto a ser substituído.

*replacement\_expression* : A expressão regular usada para criar o texto de substituição.

## Comportamento

- Pesquisa cada linha da coluna especificada em busca de correspondências com a expressão regular fornecida.
- Se for encontrada uma correspondência, o resultado será construído usando a expressão de substituição, que pode incluir grupos de captura.
- Se nenhuma correspondência for encontrada, o valor original da coluna será retornado sem alterações. Usa a sintaxe de expressão regular do Java e oferece suporte a correspondências não gananciosas usando '?'.

## Tipo de retorno

Sequência

## Exemplo

Suponha a seguinte sintaxe:

`ReplaceRegex([Source Column],[Regex Statement],[Capture Group])`

Se a instrução regex encontrar uma correspondência na coluna de origem, a fórmula retornará o valor do grupo de captura. Se nenhuma correspondência for encontrada, ele retornará o valor da coluna de origem. A variante de regex compatível com a função é Java.

Aqui está um exemplo específico:

```
=ReplaceRegex(Journal Entry
      Description,"^.*(INVOICE).{0,8}?(\d{10}).*","$2")
```

Essa fórmula procurará a palavra "INVOICE" (em letras maiúsculas) na coluna Journal Entry Description. Se encontrar essa cadeia, ele retornará o primeiro número de 10 dígitos que encontrar dentro de 8 caracteres do final da palavra. Você poderia usar essa fórmula para analisar números de faturas de 10 dígitos a partir de uma descrição de entrada de texto livre no diário. Neste exemplo, o primeiro grupo de captura ($1) é "INVOICE" e o segundo grupo de captura ($2) é o número de dez dígitos (\d {10} ).

Aqui está um exemplo de sua saída:

![](../../../resources/images/studio_images/studioimages/studio_diagram_output%20example.png)

Agora, vamos detalhar o que está acontecendo na expressão regular deste exemplo:

- O último.\* corresponde a qualquer caractere, qualquer número de vezes.
- Novamente, o parêntese especifica que esse número é um grupo de captura. Nesse caso, seu grupo de captura é 2.
- 10} significa que a regra anterior deve ser aplicada a 10 caracteres em uma linha. Portanto, \d {10} significa "combine 10 números em uma linha"
- O \d significa combinar qualquer número.
- O ponto de interrogação (?) significa que a correspondência anterior deve corresponder ao menor número possível de caracteres. Por exemplo, se você tiver um número de 11 dígitos, os primeiros 10 dígitos serão combinados com o próximo termo, não os últimos 10. Remoção do? em vez disso, corresponderá aos últimos 10.
- O ponto (.) significa o mesmo que antes. No entanto, o endereço {0,8} significa que ele corresponde a um número mínimo de 0 e máximo de 8 caracteres.
- O parêntese em que a fatura está envolvida especifica que seu valor deve ser capturado. O valor mais à esquerda entre parênteses é o grupo de captura 1. Cada grupo de captura adicional aumenta o número em 1, da esquerda para a direita.
- A palavra "INVOICE" significa que corresponde à palavra exata INVOICE. É sensível a maiúsculas e minúsculas.
- O asterisco (\*) significa que os critérios anteriores podem corresponder a qualquer número de caracteres. Portanto, o asterisco de ponto (.\*) significa corresponder a qualquer número de qualquer caractere.
- O ponto (.) é um curinga que corresponde a qualquer caractere.
- O acento circunflexo (^) significa que nossa expressão regular deve começar a corresponder ao início do valor na Descrição do registro no diário.

Observe a saída da linha:

O NÚMERO DA MINHA FATURA PRINCIPAL É 6872954678, MAS TAMBÉM TEMOS UMA FATURA PRINCIPAL DE 1234567890

Essa saída está correspondendo ao segundo número de fatura, não ao primeiro. Isso se deve ao primeiro ponto Asterisco (.\*) na expressão regular. Esse termo corresponderá a tantos caracteres quanto possível até encontrar um que não possa corresponder. Se quiséssemos que ele correspondesse ao menor número possível de caracteres, poderíamos adicionar um? à nossa oferta de expressões regulares:

```
=ReplaceRegex(Journal Entry
      Description,"^.*?(INVOICE).{0,8}?(\d{10}).*","$2")
```

Para obter mais informações sobre a sintaxe regex ou para testar suas próprias instruções regex, visite [http://www.rexegg.com/regex-quickstart.html](http://www.rexegg.com/regex-quickstart.html "(Abre em uma nova guia ou janela)") e [regex101.com](https://regex101.com/ "(Abre em uma nova guia ou janela)").

Nota:

- Para capturar partes específicas da cadeia de caracteres correspondente, use parênteses na expressão de correspondência e faça referência a elas como "\(1", "\)2" etc. na expressão de substituição.
- Se nenhuma correspondência for encontrada em uma linha, o valor original da coluna será retornado.
- Certifique-se de testar seus padrões de regex usando ferramentas on-line ou ambientes baseados em Java para garantir a compatibilidade.
