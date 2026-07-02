---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Se a função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/if.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Se a função

Avalia uma expressão de filtro e retorna um valor se for verdadeiro e outro valor se for falso. Oferece suporte a operações AND e OR na condição.

## Sintaxe

`If(filter_expression, true_expression, false_expression)`

## Argumentos

*filter\_expression* : A condição a ser avaliada. Oferece suporte a operadores lógicos como AND, OR e operadores de comparação (=,!=, <, >, <=, >=, IN, NOT IN). Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

*true\_expression* : O valor a ser retornado se a expressão filter\_expression for avaliada como true. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

*false\_expression* : O valor a ser retornado se a expressão filter\_expression for avaliada como falsa. Observação: esse parâmetro aceita uma expressão, o que significa que você pode fornecer um valor literal, uma referência de coluna ou o resultado de outra função. Necessário

## Comportamento

- Avalia a condição fornecida (filter\_expression).
- Se a condição for avaliada como verdadeira, retorna o resultado de true\_expression.
- Se a condição for avaliada como falsa, retorna o resultado de false\_expression.
- Há suporte para operações lógicas como AND e OR, com AND avaliado antes de OR, a menos que seja substituído por parênteses.
- Suporta o aninhamento de funções If entre si para uma lógica mais complexa.
- Suporta a maioria das funções dentro da instrução If, mas não suporta as funções LookupEx, TableMatch, ou External Data Lookup.

## Tipo de retorno

Depende do tipo de retorno de true\_expression ou false\_expression (String, Number ou Date).

## Exemplos

- O exemplo a seguir retorna 1 se a coluna Type contiver a string Int; caso contrário, retorna o valor da coluna NumCPU :`=If(Type="Int",1,NumCPU)`
- O exemplo a seguir retorna "yes" se a coluna B for igual a 100 e a coluna C for igual a "hello", ou se a coluna A for maior que zero. Caso contrário, ele retorna "não"

  ```
  If(colA > 0 OR colB = 100 AND colC = “hello”,
                “yes”, “no”)
  ```
- O exemplo a seguir examina o campo Type (Tipo) na tabela Consulting Hours (Horas de consultoria) para determinar se as horas são faturáveis. Se for o caso, ele retorna o número de horas inseridas na coluna Hours (Horas). Se as horas não forem faturáveis, ele retornará um zero.

  ```
  =If({Consulting
                Hours.Type}="Billable",{Consulting Hours.Hours},0)
  ```
- O exemplo a seguir executa um cálculo simples de pagamento de horas extras:

  ```
  =If(Hours>40,Rate*40+Overtime
                Rate*(Hours-40),Rate*Hours)
  ```
- O exemplo a seguir seleciona um programa de navegação com base no sistema operacional:`=If(OS_Type="Windows","Internet Explorer","Firefox")`
- O exemplo a seguir retorna 0 quando nulo e 1 caso contrário:`=If(IsDataPresentHere="",0,1)`
- O exemplo a seguir mostra um If aninhado:`=If(a=b,If(c=d,q,p),z)`
- O exemplo a seguir calcula o valor absoluto:`=If(x<0,x*(-1),x)`
- O exemplo a seguir retornaria um valor de 1:

  ```
  =If(Trim("Baskets ") = Pluralize("Basket"), 1, 0
                )
  ```
- O exemplo a seguir retornaria "true" se um número de telefone sem fio não fosse um dos números especificados:

  ```
  =IF(Wireless Number NOT IN
                ("202-321-4143","310-697-9064"),"true","false")
  ```

Nota:

- Se você estiver escrevendo uma instrução If aninhada muito complexa, considere usar a função TableMatch em vez disso.
- As funções podem ser usadas em condições e resultados If, exceto LookupEx, TableMatch, e External Data Lookup.
- Para comparações em branco, use "" em vez da palavra-chave BLANK.
