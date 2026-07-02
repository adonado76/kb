---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "ApptioScript exemplos"
breadcrumb: []
source_path: "studio/apptioscript/apptioscript_examples.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ApptioScript exemplos

Use os exemplos a seguir para revisar os usos de ApptioScript.

## Exemplo 1

```
' An example script used in OnCellValueChanged
If State = "CA"
row.City.isRequired = "true"
' Any function can be called here
' example: lower case the city cell
row.City = LOWER(City)
' a better way of doing lookup instead of using dynamic text
row.Japanese = lookup(Number,Japanese,Number,Japan)
Else
row.City.isRequired = "false"
End If
```

## Exemplo 2

```
If State = "WA"
row.City.isEditable = "false"
Else
row.City.isEditable = "true"
End If
```

## Exemplo 3

```
An example of calling a procedure:
Sub Test()
Test2()
End Sub
Sub Test2()
Return("Foo")
End Sub
```

## Exemplo 4

```
Test() 'this calls Test() subprocedure defined in Example 3
```

## Exemplo 5 Tabelas editáveis

Digite o código em TBM Studio: **Tabela editável > Script**.

## Trilha de auditoria

Editar célula - exemplo 1

```
If eventType = "cellEdit(Name)"
if row.Name="X"
SendEmail("email Id", "subject", "content")
end if
end if
```

Editar célula - exemplo 2

```
If eventType = "cellEdit(Name)" OR eventType = "cellEdit(ID)"
if row.Name="X"
SendEmail("email Id", "subject", "content")
end if
end if
```

Editar célula - exemplo de erro

```
If eventType = "cellEdit(wrong column name)"
if row.Name="X"
SendEmail("email Id", "subject", "content")
end if
end if
could not evaluate [wrong column name] in cellEdit command
```

Nível de linha - captura Editado por e Data de edição (formato de data = MM-dd-aaaa hh:mm a)

```
if eventType = "cellEdit" OR eventType = "addRow"
{row.Edited By}="<%=$CurrentUser:Users.Id%>"
{row.Edit Date}="<%=Dateformat(NOW(),"MM-dd-yyyy hh:mm a")%>"
end if
```

Nível de linha - captura Editado por e Data de edição (formato de data = MM-dd-aaaa hh:mm a)

```
if eventType = "cellEdit" OR eventType = "duplicateRow"
{row.Edited By}="<%=$CurrentUser:Users.Id%>"
{row.Edit Date}="<%=Dateformat(NOW(),"MM-dd-yyyy hh:mm a")%>"
end if
```

## Controle a capacidade de edição de uma coluna

```
row.FIELDNAME.isEditable = "false"
```

## Células editáveis baseadas em funções

```
If "<%=$CurrentUser:Users.Role%>" = "Apptio Admin"
row.Amount.isEditable="false"
Else
row.Amount.isEditable="true"
End If
```

## Preencher o valor em uma célula a partir de outra pesquisa

```
{row.Unit of Measure}=All Business Services:Unit of Measure[Service ID=Service ID]
```

## Exemplo 6 Botão para apoiar o fluxo do processo

Insira o código em Propriedades do botão: **Guia Ações > Ações do servidor**.

## Enviar plano (alteração do status do consumidor)

```
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], CSM Status="Submitted")
```

## Cancelar envio do plano (alteração do status do consumidor)

```
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], CSM Status="Not Submitted")
```

## Rejeitar plano (modificação do status financeiro)

```
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], Finance Status="Rejected")
```

## Cancelar envio do plano (alteração do status financeiro)

```
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], Finance Status="Approved")
```

## Reinicialização (alteração do status financeiro)

```
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], CSM Status = "Not Submitted", Finance Status = "Pending", CopyTable="No")
```

## Reset All (Processar alteração de status do proprietário)

```
EditRows("Jun 2019", Demand Plan Status[], CSM Status = "Not Submitted", Finance Status = "Pending", CopyTable="No")
```

## CopyTable

```
copytable("reference.apptio.com:<%=ProjectName()%>/Reports/<%=CurrentDate("MMMM:yyyy")%>/CostModels/Default/.TableTransform:Volume Forecasts Transform/.Summary/","reference.apptio.com:<%=ProjectName()%>","Volume Forecasts Approved","<%=CurrentDate("MMMM:yyyy")%>")
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], CopyTable="Copied")
```

Observação: CopyTable colocará a tabela no espaço de trabalho de desenvolvimento dos usuários atuais e NÃO fará o check-in das alterações. Por esse motivo, talvez você queira que essa funcionalidade seja controlada por um administrador em vez de um usuário.

## Exemplo 7 ApptioScript de ApptioOne Demanda

Tabela editável de entrada do Plano de Volume

```
row.Service ID.isEditable = "false"
row.Service Offering.isEditable = "false"
row.Application Name.isEditable = "false"
row.Unit of Measure.isEditable = "false"
row.Rate.isEditable = "false"
row.Baseline Volume.isEditable = "false"
if eventType = "cellEdit" OR eventType = "addRow"
{row.Edited By}="<%=$CurrentUser:Users.Id%>"
{row.Edit Date}="<%=Dateformat(NOW(),"MM-dd-yyyy hh:mm:ss a")%>"
end if
```
