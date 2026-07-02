---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "LookupFromPath função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/lookupfrompath.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupFromPath função

**Aplica-se a** : TBM Studio 12.0 e posterior

Recupera valores de qualquer tabela em qualquer domínio e projeto. Se houver várias correspondências, a função retornará {VARIOUS} para colunas de texto e uma soma para colunas numéricas.

Observação: Essa função não funcionará em conjuntos de dados se a função fizer referência a um componente de relatório no mesmo projeto.

## Onde usar

Essa função pode ser usada em colunas de fórmula em tabelas de relatórios.

Observação: essa função não pode ser usada em conjuntos de dados.

## Sintaxe

`LookupFromPath("lookup_table_path",source_column,matching_column,lookup_value_column)`

## Argumentos

*caminho da tabela de pesquisa*

Caminho completo para a tabela de origem. Observe que você deve colocar aspas ao redor do caminho se ele for uma cadeia de caracteres literal.

Por exemplo:

`"abccompany.com:test/Data/September:2010/line items"`

Você pode criar o caminho a partir de outras funções, como DomainName, ProjectName, e CurrentDate. Consulte a seção Exemplos abaixo.

*coluna\_fonte*

A coluna na tabela atual que se vincula à coluna em outra tabela.

*coluna\_correspondente*

A coluna na outra tabela que se vincula à tabela atual.

*coluna\_valor\_procurado*

A coluna na outra tabela que fornecerá os valores.

## Tipo de retorno

O valor da coluna de pesquisa. Se houver várias correspondências, a função retornará {VARIOUS} para colunas de texto e uma soma para colunas numéricas.

## Exemplos

- Abaixo está um exemplo de um caminho simples inserido diretamente e um caminho equivalente inserido usando funções. As cadeias de caracteres literais inseridas no caminho devem estar entre aspas. O sinal & é usado como um operador de concatenação.

  ```
  “apptio.com:BankDemo/Data/January:2010/GL Actuals”
                DomainName()& “:” & ProjectName() & “/Data/” & CurrentDate(“MMMM:yyyy”) &
                “/<some table name here>”
  ```
- Abaixo está um exemplo de um caminho complexo usando as funções DomainName, ProjectName, e CurrentDate.

  ```
  DOMAINNAME() & “:” & PROJECTNAME() &
                “/Reports/” &
  CURRENTDATE(“MMMM:yyyy”) &
                  “/
  CostModels/
  Default/
  .View:Product Capacity Owner/
  Business
                  Domains/
  .WithDefaultMetric-Planned Price/
  .DrillTo/
  <%/.DrillTo/<%=ObjectName%>/
  !FILTER[All IT
                  Products.ProductID=<%=ProductID%>]/
  !FILTER[All
                IT Products.Is Adjustment=%22No%22]/
  .LineItemsTable"
  ```

Consulte também:

- [Pesquisa de IP](iplookup.htm "(Abre em uma nova guia ou janela)")
- [Lookup e Lookup\_Wild](lookupandlookup_wild.htm "(Abre em uma nova guia ou janela)")
- [LookupEx](lookupexandlookupex_wild.htm "(Abre em uma nova guia ou janela)")
- [LookupMetric](lookupmetric.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(Abre em uma nova guia ou janela)")
