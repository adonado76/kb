---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "apptioscript"
title: "EditRows function"
breadcrumb: []
source_path: "apptioscript/editrows_function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# EditRows function

Use EditRows() to modify an existing table row, and to set values in the columns of that
table.

Note:

- If you run this script on filtered view of a table, only the filtered rows will be impacted by
  the execution of edit rows script.
- Lookup to another editable table feature will work for editable table only.
- It will not work for enriched editable table, nor will it work for multiple lookup tables.

## Syntax 1

```
EditRows( date, tableName[optional filters], columName="value", columName2=value,...)
```

## Syntax 2

```
EditRows( date, tableName[columnName1={lookupTable.columnX} AND columnName2={lookupTable.columnY} AND ...], columName="{lookupTable.columnP}", columName2=value,...)
```

## date

Determines the date to modify the data set.

## optional filters

The filters use the !FILTER function.

## tableName

The name of the data set, as indicated by the name of a table.

## columnName

The name of a column in the table identified in the tableName argument. The column name can
belong to the lookup table or the source table.

## value

The value to insert in the cell of the column.

## Examples

Example 1
:   ```
    EditRows( "<%=BuList.Date%>", BuList[BU="Sales" AND Date="<%=BuList.Date%>"], status="ACCEPTED", comment="Accepted by <%=$CurrentUser:Users.Full Name%> on <%=CurrentDate()%>")
    ```

Example 2
:   ```
    EditRows( "Jan 2010", BuList[BU="Sales" AND Date="Jan 2010"], status="ACCEPTED", comment="Accepted by Bob on May 15, 2010")EditRows( "<%=BuList.Date%>", BuList[BU="Sales" AND Date="<%=BuList.Date%>"], status="ACCEPTED", comment="Accepted by <%=$CurrentUser:Users.Full Name%> on <%=CurrentDate()%>")
    ```

Example 3
:   ```
    EditRows("January:2022", Plan Volume[Service Provider GOC={Service Provider GOC.Original}], Service Provider GOC={Service Provider GOC.New}, Comment={Service Provider GOC.Comment})
    ```

Example 4
:   ```
    EditRows("January:2015", ET3[Name = {ET4.Name}], ID = {ET4.ID}, Seq = ({ET3.Seq}*2))
    ```

## Error Messages

- The Lookup column types must be same for the column
  [ET3]

  ```
  EditRows("January:2015", ET3[Seq={ET4.Seq}], ID = 2+"ABCV")
  ```
- Two look up tables [ET4], [ET4] are not
  allowed

  ```
  EditRows("January:2015", ET3[Seq={ET4.Seq}], ID = {ET5.ID})
  ```
