---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Concatenação de strings"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/string-concatenation.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Concatenação de strings

**Aplica-se a** : TBM Studio 12.0 e posterior

Para formatar valores para métricas, você pode especificar uma cadeia de caracteres em uma expressão.

O exemplo a seguir coloca um cifrão ( $ ) na frente do valor da coluna Custo. Se Cost for 200, essa expressão será avaliada como $200.

`="$"+Cost`

O exemplo acima também poderia ser escrito com um E comercial ( & ) como operador de concatenação, conforme mostrado no exemplo a seguir.

`="$"&Cost`

O exemplo a seguir coloca o valor da coluna Ticket Description (Descrição do tíquete) antes do valor da coluna Ticket Number (Número do tíquete), que está entre parênteses. Se o Ticket

Description é Hardware e Ticket Number é 10065, essa expressão é avaliada como Hardware(10065).

```
=Ticket
            Description&"("&Ticket Number&")"
```

Observação: embora seja permitido usar o sinal de adição ( + ) ou o E comercial ( & ) para a concatenação de cadeias de caracteres, a melhor prática é usar o E comercial.

## Uso de hífens

Ao concatenar texto, você pode representar hífens com um E comercial duplo (&&). Muitas vezes, isso é usado para criar chaves exclusivas para entradas do registro geral. Se um item a ser concatenado estiver em branco, ele não será incluído na concatenação.

Por exemplo, se você digitar essa string:

`string1&&string2&&string3`

Isso será traduzido como:

`string1 - string3`

Observe que o && coloca um espaço antes e depois do hífen.

## Exemplo

Caso 1: Um espaço é adicionado entre 2 &&'s

="A"&&" "&&"B" será traduzido como A - - B

Caso 2: Nulo ou "" é adicionado entre 2 &&s

="A"&&""&&"B" será traduzido como A - B

Caso 3: Nenhum "" adicionado entre 2 &&s resultará em erro

="A"&&&&"B" será traduzido como ERRO
