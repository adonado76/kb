---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "LookupMetric função"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/functions/lookupmetric.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupMetric função

**Aplica-se a** : TBM Studio 12.0 e posterior

Procura uma coluna de outra métrica usando o mesmo caminho de dados. Ele usa o caminho atual, substitui uma nova métrica e executa novamente o modelo antes de procurar um valor em uma coluna especificada.

## Onde usar

Essa função pode ser usada em:

- Métricas calculadas e relatórios com colunas de métricas
- Colunas de fórmula em tabelas de relatórios

Use para procurar uma métrica no caminho de dados atual que normalmente não está disponível.

## Sintaxe

`LookupMetric(metric,column)`

## Argumentos

*métrica*

O nome da métrica a ser usada.

*coluna*

A coluna da nova tabela a ser pesquisada.

## Tipo de retorno

Métrica

## Exemplo

Esse exemplo resulta em uma tabela AssignmentRatios que tem uma coluna adicional chamada {NewCol}.

```
demo.apptio.com:BanksDemo/
CostModels/
Default/
Cost/
1199145600000/
Services/
.Drivers/
Servers/
!FILTER[ServerCMDB.Server Product="ASP.NET"]/
!GROUPBY[ServerCMDB.Server Product]/
.AssignmentRatios/
!NEWCOLUMN[{NewCol}=LookupMetric(Chargeback,{ASP.NET})]/
```

O valor da coluna {NewCol} é fornecido pela função LookupMetric que faz referência à coluna {ASP.NET} da tabela a seguir:

```
demo.apptio.com:BanksDemo/
CostModels/
Default/
```

`Chargeback`

```
/
1199145600000/
Services/
.Drivers/
Servers/
!FILTER[ServerCMDB.Server Product="ASP.NET"]/!GROUPBY[ServerCMDB.Server
              Product]/
.AssignmentRatios/
```

Consulte também:

- [Pesquisa de IP](iplookup.htm "(Abre em uma nova guia ou janela)")
- [Lookup e Lookup\_Wild](lookupandlookup_wild.htm "(Abre em uma nova guia ou janela)")
- [LookupEx](lookupexandlookupex_wild.htm "(Abre em uma nova guia ou janela)")
- [LookupFromPath](lookupfrompath.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(Abre em uma nova guia ou janela)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(Abre em uma nova guia ou janela)")
