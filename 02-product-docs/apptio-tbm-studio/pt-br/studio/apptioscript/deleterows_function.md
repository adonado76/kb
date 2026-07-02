---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "DeleteRows função"
breadcrumb: []
source_path: "studio/apptioscript/deleterows_function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# DeleteRows função

Use a função DeleteRows( ) para excluir uma linha de tabela existente com base nos valores das colunas designadas.

## Sintaxe

Observação: Se você executar esse script em uma exibição filtrada de uma tabela, somente as linhas filtradas serão afetadas pela execução do script de exclusão de linhas.

```
DeleteRows( date, tableName[columName1="value" OPERAND columName2="value" ...])
```

## data

Determina a data para modificar o conjunto de dados. Para obter uma lista de formatos de data válidos, consulte [DateFormat function](../formulas-and-functions/functions/dateformat.htm "(Abre em uma nova guia ou janela)")

## tableName

O nome do conjunto de dados, conforme indicado pelo nome de uma tabela.

## columnName

O nome de uma coluna na tabela anotada em tableName.

## valor

O valor na linha a ser excluída.

## operando

Os operandos válidos são AND e OR.

## Exemplo 1

Esse exemplo exclui todas as linhas do conjunto de dados BuList para a data atual em que a coluna BU é igual a "Sales" ou a coluna Other é igual a "Foo"

```
DeleteRows( CurrentDate(), BuList[BU="Sales" OR Other="Foo"])
```

## Exemplo 2

Esse exemplo exclui todas as linhas do conjunto de dados BuList de janeiro de 2010 em que a coluna BU é igual a "Sales" e a coluna Date = "Jan 2010".

```
DeleteRows( "January 2010", BuList[BU="Sales" AND Date="Jan 2010"])
```
