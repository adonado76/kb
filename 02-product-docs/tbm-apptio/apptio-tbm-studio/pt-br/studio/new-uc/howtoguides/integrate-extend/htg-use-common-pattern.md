---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Guia prático: Como usar padrões comuns de script"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Integrar e ampliar"
  - "Scripting"
source_path: "studio/new-uc/howtoguides/integrate-extend/htg-use-common-pattern.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guia prático: Como usar padrões comuns de script

**Objetivo:** Aprender padrões comprovados de arquitetura orientada a objetos ( ApptioScript ) para cenários empresariais comuns.

**Tempo estimado:** 45 minutos para revisar todos os padrões

**Pré-requisitos:** Ter concluído o primeiro guia prático ou possuir conhecimentos equivalentes sobre o ApptioScript

Este guia apresenta oito padrões comuns que você pode adaptar às suas implementações. Cada padrão inclui o caso de uso empresarial, um exemplo completo de código e notas de implementação.

## Padrão 1: Consultar valores de outra tabela

**Caso de uso empresarial**

Você tem uma tabela de mapeamento de pessoal na qual os usuários selecionam um funcionário. Você deseja preencher automaticamente o departamento do funcionário a partir de uma tabela mestre de funcionários, de forma semelhante à função VLOOKUP do Excel.

**O Roteiro**

```
' Lookup department from employee master table
' When user selects Employee ID, fetch their department
 
row.Department = lookup(EmployeeID, Department, EmployeeID, EmployeeMaster)
```

**Como ela funciona**

A função lookup() recebe quatro parâmetros: o valor a ser comparado ( EmployeeID da linha atual), a coluna a ser retornada (Departamento), a coluna de referência ( EmployeeID na tabela de pesquisa) e o nome da tabela de pesquisa ( EmployeeMaster ).

**Alternativa: uso da sintaxe de referência de tabela**

```
' Alternative lookup syntax using table reference
{row.Unit of Measure} = All Business Services:Unit of Measure[Service ID=Service
        ID]
```

Observação: a função de pesquisa só funciona com tabelas editáveis. Para consultas a outros tipos de tabela, use a sintaxe de referência de tabela mostrada acima.

## Padrão 2: Lógica condicional (SE/ENTÃO)

**Caso de uso empresarial**

Quando um usuário seleciona um estado, você deseja tornar o campo “Cidade” obrigatório para alguns estados (como a Califórnia), mas opcional para outros, e converter automaticamente os nomes das cidades para letras minúsculas, por uma questão de consistência.

**O Roteiro**

```
' Make City required for California, optional for others
' Also standardize city name to lowercase
 
If State = "CA"
 row.City.isRequired = "true"
 ' Standardize to lowercase
 row.City = LOWER(City)
Else
 row.City.isRequired = "false"
End If
```

**Exemplo com várias condições**

```
' Different validation based on expense type
If ExpenseType = "Capital"
    row.DepreciationPeriod.isRequired =
        "true"
    row.DepreciationPeriod.isEditable =
        "true"
ElseIf ExpenseType = "Operating"
    row.DepreciationPeriod.isRequired =
        "false"
    row.DepreciationPeriod.isEditable =
        "false"
 row.DepreciationPeriod = ""
End If
```

Dica: você pode aninhar instruções `if` dentro de outras instruções `if` para criar lógicas complexas, mas mantenha o aninhamento superficial (no máximo 2 ou 3 níveis) para facilitar a manutenção.

## Padrão 3: Controle de acesso às células baseado em funções

**Caso de uso empresarial**

Você deseja permitir que apenas os administradores editem valores financeiros, enquanto os usuários comuns possam visualizá-los, mas não modificá-los. Isso oferece uma camada adicional de controle além da segurança no nível da linha.

**O Roteiro**

```
' Only Apptio Admins can edit the Amount column
If "<%=$CurrentUser:Users.Role%>" = "Apptio Admin"
 row.Amount.isEditable = "true"
Else
    row.Amount.isEditable =
        "false"
End If
```

**Notas de implementação**

- Este script é executado ao carregar a página, portanto, a editabilidade das células é definida quando a tabela é exibida
- A verificação de função utiliza o nome exato da função, conforme definido na administração do TBM Studio
- Combine com a segurança no nível da linha (RLS) para um controle de acesso abrangente

## Padrão 4: Manipulação de datas

**Caso de uso empresarial**

É necessário trabalhar com datas em vários formatos para diferentes finalidades: registrar registros de data e hora para trilhas de auditoria, definir períodos fiscais para operações com dados ou calcular o início do ano fiscal.

**Padrões comuns de data**

```
' Capture current timestamp with custom format
row.Timestamp = "<%=DateFormat(NOW(),"MM-dd-yyyy hh:mm:ss a")%>"
 
' Get current fiscal period (for use in data operations)
' Returns format like "January:2025"
AddRow(CurrentDate("MMMM:yyyy"), MyTable, Name="NewRecord")
 
' Add row for start of fiscal year
AddRow("!START_OF_YEAR(February:2025)", BudgetTable, Category="Annual")
 
' Add row for most recently edited period
AddRow(".MostRecent", AdjustmentsTable, Type="Correction")
```

**Referência sobre formatos de data**

|  |  |  |
| --- | --- | --- |
| **String de formatação** | **Exemplo de saída** | **Caso de uso** |
| mm-dd-aaaa | 15/01/2025 | Formato de data dos EUA |
| MMMM:aaaa | January:2025 | Exercício fiscal (obrigatório para operações com dados) |
| MMMM:AFyyyy | January:FY2025 | Formato do exercício fiscal |
| hh:mm a | 14h30 | Hora com AM/PM |
| hh:mm:ss a | 14h30min45s | Hora com segundos |

Aviso: Para operações com dados como AddRow( ) e EditRows( ), as datas devem ser indicadas com o nome completo do mês (janeiro, e não jan) no formato MMMM:aaaa.

## Padrão 5: Operações com strings

**Caso de uso empresarial**

Você precisa padronizar a entrada de dados, combinar valores para exibição ou criar mensagens dinâmicas. As funções de string ajudam a garantir a consistência dos dados e a gerar mensagens informativas para o usuário.

**Padrões comuns de cadeias de caracteres**

```
' Standardize text to uppercase
row.VendorCode = UPPER(VendorCode)
 
' Standardize text to lowercase
row.Email = LOWER(Email)
 
' Concatenate values for a composite field
row.AcceptedBy = "Accepted by <%=$CurrentUser:Users.Full Name%> on
        <%=CurrentDate()%>"
 
' Build a detailed comment
row.Comment = "Approved: " & Description & " (" & Amount & ")"
```

**Concatenação de strings**

Use o operador & para concatenar cadeias de caracteres. É possível combinar texto literal (entre aspas), valores de colunas e texto dinâmico em uma única expressão.

## Padrão 6: Alterações no status do fluxo de trabalho (ações dos botões)

**Caso de uso empresarial**

Vocês têm um processo de planejamento de demanda no qual os gerentes dos centros de custo apresentam planos, e o departamento financeiro os aprova ou rejeita. Você precisa de botões que atualizem o status do fluxo de trabalho (por exemplo, “Enviar”, “Aprovar”, “Rejeitar”).

**Script do botão “Enviar”**

```
' Submit Plan - changes CSM Status to "Submitted"
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], 
 CSM Status="Submitted")
```

**Script do botão “Aprovar”**

```
' Approve Plan - Finance approves the submission
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], 
 Finance Status="Approved")
```

**Script do botão "Rejeitar"**

```
' Reject Plan - Finance rejects the submission
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], 
 Finance Status="Rejected")
```

**Script do botão “Redefinir tudo” (somente para administradores)**

```
' Reset All - Returns all records to initial state
' Note: Empty filter [] applies to all rows
EditRows("Jun 2019", Demand Plan Status[], 
 CSM Status="Not Submitted", 
 Finance Status="Pending", 
 CopyTable="No")
```

**Como associar scripts a botões**

1. No Report Studio, alterne para o Modo de Edição
2. Clique com o botão direito do mouse no botão e selecione **Propriedades**
3. Selecione a guia **Ações**
4. Insira seu script no campo “**Ação do servidor** ”
5. Clique **em OK**

## Padrão 7: Notificações por e-mail sobre eventos

**Caso de uso empresarial**

Quando um gerente de centro de custo envia um plano de demanda, você deseja notificar automaticamente o aprovador designado por e-mail com os detalhes do envio.

**O Roteiro**

```
' Send notification when plan is submitted
If eventType = "cellEdit(Submission_Status)"
    If {row.Submission Status} =
        "Submitted"
        ' Send email to the designated
        approver
 SendEmail(row.Approver, 
            "Demand Plan submitted for
        review and approval", 
            "Demand Plan submitted by
        " & row.Submitter & 
            " for the " &
        row.Organization Name & " department. " &
            "Special comment from
        submitter: " & row.Submission Comment)
 End If
End If
```

**SendEmail Sintaxe**

`SendEmail("recipient@company.com", "Subject Line", "Email Body
Content")`

**Notas de implementação**

- Usar ` cellEdit(ColumnName )` impede que o e-mail seja reenviado quando outras colunas forem editadas
- O destinatário pode ser um valor de célula (como row.Approver ) ou um endereço de e-mail predefinido
- Use & para concatenar strings e criar conteúdo dinâmico para e-mails

Aviso: Teste cuidadosamente os scripts de e-mail em um ambiente de desenvolvimento. Scripts incorretos podem enviar e-mails indesejados a destinatários reais.

## Padrão 8: Copiar dados entre tabelas

**Caso de uso empresarial**

Depois que o departamento financeiro aprovar um plano de demanda, você deve copiar os volumes previstos para uma tabela de “aprovados” que alimente os relatórios posteriores. Isso cria um instantâneo do estado aprovado.

**CopyTable Exemplo**

```
' Copy approved forecast to snapshot table
CopyTable(
   
        "reference.apptio.com:<%=ProjectName()%>/Reports/<%=CurrentDate("MMMM:yyyy")%>/CostModels/Default/.TableTransform:Volume
        Forecasts Transform/.Summary/",
   
        "reference.apptio.com:<%=ProjectName()%>",
 "Volume Forecasts Approved",
   
        "<%=CurrentDate("MMMM:yyyy")%>"
)
```

**CopyEditableTable Exemplo**

```
' Copy editable table with auto check-in
CopyEditableTable(
   
        "tests.apptio.net:MyProject/Data/January:FY2015/Source Data",
 "tests.apptio.net:MyProject",
 "Archived Data",
 "overwrite",
 autocheckin="true"
)
```

## Principais diferenças

|  |  |  |
| --- | --- | --- |
| **Função** | **Utilização** | **Check-in automático** |
| CopyTable() | Tabelas de relatórios, conjuntos de dados brutos | Não (locais na área de trabalho de desenvolvimento) |
| CopyEditableTable() | Tabelas editáveis com controle de modo | Opcional (parâmetro autocheckin) |

Observação: o comando ` CopyTable ` salva os dados na pasta de trabalho de desenvolvimento do usuário atual e NÃO faz o check-in das alterações automaticamente. Considere restringir essa funcionalidade aos administradores.

## Padrões adicionais

## Percorrendo os dados

Use a função Loop para percorrer as linhas de um conjunto de dados e realizar operações em cada linha.

```
' Process each row in a data set
Loop mydatasetname
 Debug("Cost=" & Cost)
 ' Add additional operations here
End Loop
```

## Exclusão condicional de linhas

Use ` DeleteRows( )` para remover linhas que atendam a critérios específicos de uma tabela editável.

```
' Delete all rows where BU is "Sales" OR Other is "Foo"
DeleteRows(CurrentDate(), BuList[BU="Sales" OR Other="Foo"])
 
' Delete rows matching multiple conditions (AND)
DeleteRows("January 2010", BuList[BU="Sales" AND Date="Jan 2010"])
```

## Adicionando linhas programaticamente

Use a função " AddRow( " para criar novos registros em tabelas editáveis com valores iniciais.

```
' Add a new project record for the current period
AddRow(CurrentDate("MMMM:yyyy"), All Projects, 
 Project Name="unnamed", 
 Status="Pending")
 
' Add a server record for a specific period
AddRow("February:2008", MyServers, 
 servername="server001", 
 ram="128", 
 os=UPPER("windows"))
```

## O que vem a seguir

- Seção 5.6: ApptioScript Referência — Documentação completa da função com todos os parâmetros e opções
- [Configurar a segurança de dados](../work-with-data/data-security.html) — Saiba mais sobre a segurança no nível da linha, que complementa o controle de acesso baseado em scripts
- [Conecte-se por meio de APIs](api-integration.html) — Para integrações avançadas além do ApptioScript

**Tópico principal:** [Scripting](../../../../studio/new-uc/howtoguides/integrate-extend/scripting.html)
