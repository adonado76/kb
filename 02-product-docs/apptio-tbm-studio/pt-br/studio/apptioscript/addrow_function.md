---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "AddRow função"
breadcrumb: []
source_path: "studio/apptioscript/addrow_function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# AddRow função

Use AddRow( ) para adicionar uma linha a uma tabela e para definir valores nas colunas dessa tabela.

## Sintaxe

```
AddRow(date, tableName, columnName=value, columnName2=value, ...)
```

## data

Determina a data para modificar os conjuntos de dados. O argumento de data pode usar um dos seguintes formatos:

| Formato do argumento | Descrição |
| --- | --- |
| "February:2008" | Adicionar uma linha em fevereiro de 2008 |
| "!START\_OF\_YEAR( February:2008 )" | Adicione uma linha para o primeiro mês do ano fiscal. |
| currentDate("MMMM:yyyy") | Adicione uma linha para o mês atual. |
| ".MostRecent" | Adicione uma linha no período de tempo editado mais recentemente para o projeto. |

## tableName

O nome do conjunto de dados, conforme indicado pelo nome de uma tabela.

## columnName

O nome de uma coluna na tabela identificada no argumento tableName.

## valor

O valor a ser inserido na célula da coluna na nova linha.

## Exemplo 1

Este exemplo está atuando em uma tabela chamada MyServers, que tem colunas chamadas servername, ram e os. Observe que a tabela pode ter outras colunas nas quais o script não está atuando. Este exemplo adiciona uma linha a uma tabela chamada MyServers para o primeiro mês do ano fiscal e define os seguintes valores para as colunas:

- nome do servidor server001
- RAM = 128
- os = WINDOWS

```
AddRow( "!START_OF_YEAR(February:2008)", MyServers, servername="server001", ram="128", os=UPPER("windows"))
```

## Exemplo 2

Este exemplo é igual ao Exemplo 1, exceto pelo fato de que ele adiciona uma linha para o mês atual em vez do primeiro mês do ano fiscal.

```
AddRow(CurrentDate("MMMM:yyyy"), MyServers, servername="server001", ram="128", os=UPPER("windows"))
```

## Exemplo 3

Este exemplo adiciona uma linha a uma tabela chamada DeliveryTracking para fevereiro de 2008. Indica que o valor do campo name é Server203, e o campo AcceptedBy contém uma mensagem de aceitação que identifica o usuário, a data e a hora da aprovação.

```
AddRow( "February:2008", DeliveryTracking, name="Server203", AcceptedB="Accepted by <%=$CurrentUser:Users.Full Name%> on <%=CurrentDate()%>")
```

## Exemplo 4

```
AddRow(CurrentDate("MMMM:yyyy"), All Projects, Project Name="unnamed", Status="Pending")
```

Para navegar posteriormente até essa linha, use o seguinte comando:

```
[[tab:Demand and Resource/@.TableTransform:All Projects/!FILTER[{Project ID}=%22$ACTION_RESULT%22]/Update Project Definition]]
```
