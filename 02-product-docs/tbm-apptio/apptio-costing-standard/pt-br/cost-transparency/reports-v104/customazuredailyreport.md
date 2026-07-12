---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Relatório diário personalizado Azure"
breadcrumb: []
source_path: "cost-transparency/reports-v104/customazuredailyreport.html"
images:
  - "resources/images/ct_images/customazuredailyreport_1.png"
  - "resources/images/ct_images/customazuredailyreport_10.png"
  - "resources/images/ct_images/customazuredailyreport_11.png"
  - "resources/images/ct_images/customazuredailyreport_12.png"
  - "resources/images/ct_images/customazuredailyreport_13.png"
  - "resources/images/ct_images/customazuredailyreport_14.png"
  - "resources/images/ct_images/customazuredailyreport_15.png"
  - "resources/images/ct_images/customazuredailyreport_16.png"
  - "resources/images/ct_images/customazuredailyreport_17.png"
  - "resources/images/ct_images/customazuredailyreport_18.png"
  - "resources/images/ct_images/customazuredailyreport_19.png"
  - "resources/images/ct_images/customazuredailyreport_20.png"
  - "resources/images/ct_images/customazuredailyreport_21.png"
  - "resources/images/ct_images/customazuredailyreport_4.png"
  - "resources/images/ct_images/customazuredailyreport_5.png"
  - "resources/images/ct_images/customazuredailyreport_6.png"
  - "resources/images/ct_images/customazuredailyreport_7.png"
  - "resources/images/ct_images/customazuredailyreport_8.png"
  - "resources/images/ct_images/customazuredailyreport_9.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Relatório diário personalizado Azure

Este guia o orienta na criação de um relatório diário personalizado do Azure. O relatório resultante será semelhante à imagem abaixo:

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_1.png)

## Editar relatório

A tabela **Azure EA Detailed Bill Raw** precisa de algumas modificações antes de podermos criar o relatório Azure Daily.

## Adição de fórmulas

Antes de criar o relatório diário, você precisa adicionar novas fórmulas à tabela **Azure EA Detailed Bill Raw**.

| Nome da coluna | Fórmula |
| --- | --- |
| Aplicativo | =If(Trim(Resource Group)="", "UNKNOWN",Upper(Resource Group)) |
| Unidade de negócios | =Nome da conta |
| Custo médio | =ExtendedCost/Day Último |
| Data Último dia | =DateFormat(Epoch Último dia, "aaaa-MM-dd") |
| Último dia | =Valor(Grande(Dia)) |
| Departamento | =Nome da assinatura |
| Data da época | =Dias(Data) \* 24 \* 3600 |
| Época Último dia | =Grande(Data da Época) |
| Época Último dia antes | =Último dia da época - (24 \* 3600) |
| São os últimos dois dias | =If(Último dia da época=Data da época OU Último dia da época anterior=Data da época, "Sim", "Não") |
| Torre de recursos de TI | =If(Lookup(Lookup,Lookup do provedor de serviços de nuvem,Lookup,Torre)="", "Unmapped",Lookup(Lookup,Lookup do provedor de serviços de nuvem,Lookup,Torre)) |
| Consulta | =Categoria do medidor && {Meter Sub-Category} && Nome do medidor |
| Código P | =If(Find(".",Pcode Temporary,3)>0,Pcode Temporary,Left(Pcode Temporary,8 )) |
| Pcode Temporário | =Meio(Tags,Encontrar("P.",Tags),11) |
| Provedor | ="Microsoft Azure“ |
| Categoria de serviço | =If(Lookup(Lookup,Lookup do provedor de serviços de nuvem,Lookup,Categoria de serviço)="", "Unmapped",Lookup(Lookup,Lookup do provedor de serviços de nuvem,Lookup,Categoria de serviço)) |
| Nome do serviço | =If(Lookup(Lookup,Lookup do provedor de serviços de nuvem,Lookup,Nome do serviço)="", "Unmapped",Lookup(Lookup,Lookup do provedor de serviços de nuvem,Lookup,Nome do serviço)) |
| Tipo de serviço | =If(Lookup(Lookup,Lookup de provedor de serviços de nuvem,Lookup,Tipo de serviço)="", "Unmapped",Lookup(Lookup,Lookup de provedor de serviços de nuvem,Lookup,Tipo de serviço)) |
| Centro de custo (Substituição de coluna) | =If(Trim(Cost Center)="", "Unknown",$\_) |
| Dia (Substituição de coluna) | =IF(Len(TRIM(Day))=1, "0"&TRIM(Day),TRIM(Day)) |

Além disso, se você tiver alguma tag a ser analisada, poderá criar uma coluna para cada tag.

|  |  |
| --- | --- |
| Nome do ambiente | =IF(FIND("Environment", Tags)>0, split((RIGHT(Tags,LEN(Tags)-FIND("Environment", Tags)-(LEN("Environment")+2)),1,""""), "") |

Consulte [este artigo](../configuration/tagazuretoschema.html#Parse) para obter uma explicação detalhada sobre como usar a fórmula.

## Modelar a tabela

Você precisará adicionar uma etapa de modelo no Pipeline de transformação. As tabelas modeladas são necessárias para a criação de métricas, o que faremos a seguir.

## Identificador de objeto

Dependendo dos atributos que deseja relatar, você precisará adicionar as respectivas colunas ao identificador de objeto. Para os fins deste guia, aqui estão as colunas necessárias no identificador de objeto para que o relatório funcione com a granularidade adequada:

## Criar métricas calculadas

Lembre-se de definir o Formato da tabela como Moeda para essas métricas.

| Nome da métrica | Fórmula |
| --- | --- |
| Custo MTD da fatura na nuvem | =Fatura na nuvem |
| Custo da fatura do mês anterior | =PreviousMonth(Cloud Fatura) |
| Custo médio diário MTD | = Azure EA Detailed Bill Raw.Cost Average |

## Criar relatórios

Você precisará criar dois novos relatórios: Transparência diária e Detalhes da transparência diária. A Transparência diária exibirá o Detalhe da transparência diária na forma de um pop-up modal.

## Relatório diário de transparência

O relatório básico é composto por 3 KPIs, um grupo de 3 gráficos e 1 tabela, e Slicers, conforme necessário. Para este exemplo, são mostrados 5 fatiadores comuns.

KPIs
:   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_4.png)

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_5.png)

Fatiadores
:   Os fatiadores podem ser adicionados conforme necessário para atender às necessidades de seu caso de uso/negócio. Aqui estão alguns exemplos de coisas que você poderia fatiar.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_6.png)

Grupo de gráficos
:   Os seguintes componentes do relatório são colocados em um grupo. Isso permite que você adicione um pivô que será aplicado a cada gráfico para visualizar as despesas por diferentes categorias.

Transformar
:   Um pivô pode ser adicionado conforme necessário para atender às necessidades de seu caso de uso/negócio. Aqui estão alguns exemplos de coisas sobre as quais você poderia girar.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_7.png)

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_8.png)

Gráficos
:   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_9.png)

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_10.png)

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_11.png)

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_12.png)

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_13.png)

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_14.png)

    Nota:

    Se você quiser que o Daily Invoice Cost Chart (Gráfico de custos diários da fatura) seja organizado por dia em vez de ExtendedCost,, será necessário adicionar uma classificação ao gráfico na IT Resource Tower.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_15.png)

Tabela
:   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_16.png)

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_17.png)

Gráficos agrupados
:   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_18.png)

Relatório diário de detalhes de transparência
:   O Relatório de detalhes oferece uma visão ampliada dos custos diários de acordo com o que está sendo movimentado.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_19.png)

Tabela
:   A tabela básica é composta de duas colunas:

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_20.png)

Seletor de colunas
:   Adicione colunas que façam sentido para seu caso de uso/necessidades comerciais.

Fatiadores
:   Adicione slicers que façam sentido para seu caso de uso/necessidades comerciais.

Criar Drill-To
:   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/customazuredailyreport_21.png)

    Ao criar o detalhamento nesse relatório, certifique-se de adicionar um detalhamento a cada pivô que tiver. Para este exemplo, isso significaria dinamizar a Torre de Recursos de TI, o Aplicativo, a Categoria de Serviço, o Grupo de Clientes e a Unidade de Negócios e, em seguida, adicionar o detalhamento a cada coluna, conforme aparece na tabela.
