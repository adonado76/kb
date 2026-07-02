---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Função de loop"
breadcrumb: []
source_path: "studio/apptioscript/loop_function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Função de loop

Use a função Loop para fazer um loop em um conjunto de dados brutos e executar instruções para cada linha do conjunto de dados.

## Sintaxe

```
Loop data set
statements
End Loop
```

## conjunto de dados

O conjunto de dados.

## declarações

As instruções que você deseja executar para cada linha do conjunto de dados.

## Exemplo

O exemplo a seguir imprime Cost = e o valor de Cost para cada linha no conjunto de dados chamado mydatasetname.

```
Loop mydatasetname
Debug("Cost=" Cost)
End Loop
```
