---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "EditRows função"
breadcrumb: []
source_path: "studio/apptioscript/editrows_function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# EditRows função

Use EditRows( ) para modificar uma linha de tabela existente e para definir valores nas colunas dessa tabela.

Nota:

- Se você executar esse script na exibição filtrada de uma tabela, somente as linhas filtradas serão afetadas pela execução do script de edição de linhas.
- O recurso de pesquisa em outra tabela editável funcionará apenas para tabelas editáveis.
- Não funcionará em tabelas editáveis enriquecidas nem em várias tabelas de pesquisa.

## Sintaxe 1

```
EditRows( date, tableName[optional filters], columName="value", columName2=value,...)
```

## Sintaxe 2

```
EditRows( date, tableName[columnName1={lookupTable.columnX} AND columnName2={lookupTable.columnY} AND ...], columName="{lookupTable.columnP}", columName2=value,...)
```

## data

Determina a data para modificar o conjunto de dados.

## filtros opcionais

Os filtros usam o!Função FILTER.

## tableName

O nome do conjunto de dados, conforme indicado pelo nome de uma tabela.

## columnName

O nome de uma coluna na tabela identificada no argumento tableName. O nome da coluna pode pertencer à tabela de pesquisa ou à tabela de origem.

## valor

O valor a ser inserido na célula da coluna.

## Exemplos

Exemplo 1
:   ```
    EditRows( "<%=BuList.Date%>", BuList[BU="Sales" AND Date="<%=BuList.Date%>"], status="ACCEPTED", comment="Accepted by <%=$CurrentUser:Users.Full Name%> on <%=CurrentDate()%>")
    ```

Exemplo 2
:   ```
    EditRows( "Jan 2010", BuList[BU="Sales" AND Date="Jan 2010"], status="ACCEPTED", comment="Accepted by Bob on May 15, 2010")EditRows( "<%=BuList.Date%>", BuList[BU="Sales" AND Date="<%=BuList.Date%>"], status="ACCEPTED", comment="Accepted by <%=$CurrentUser:Users.Full Name%> on <%=CurrentDate()%>")
    ```

Exemplo 3
:   ```
    EditRows("January:2022", Plan Volume[Service Provider GOC={Service Provider GOC.Original}], Service Provider GOC={Service Provider GOC.New}, Comment={Service Provider GOC.Comment})
    ```

Exemplo 4
:   ```
    EditRows("January:2015", ET3[Name = {ET4.Name}], ID = {ET4.ID}, Seq = ({ET3.Seq}*2))
    ```

## Mensagens de Erro

- Os tipos de coluna Lookup devem ser os mesmos para a coluna [ ET3 ]

  ```
  EditRows("January:2015", ET3[Seq={ET4.Seq}], ID = 2+"ABCV")
  ```
- Duas tabelas de pesquisa [ ET4 ], [ ET4 ] não são permitidas

  ```
  EditRows("January:2015", ET3[Seq={ET4.Seq}], ID = {ET5.ID})
  ```
