---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Azure Instâncias reservadas - alocações de ingestão e custo"
breadcrumb: []
source_path: "cost-transparency/configuration/azurereserved.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Azure Instâncias reservadas - alocações de ingestão e custo

Microsoft Azure lançou as instâncias reservadas (RIs) no final de 2017. Os custos associados a esses RIs podem ser consideráveis e precisam ser levados em conta ao considerar seus gastos com o site Azure.

Aplica-se a: Gerenciamento de custos da nuvem em TBM Studio 12.5 +.

## Visão geral

Atualmente, as cobranças de RI não são refletidas na fatura do Azure EA e precisam ser ingeridas separadamente e, em seguida, alocadas aos recursos apropriados (VMs) para que os custos efetivos dessas VMs sejam calculados adequadamente.

Este guia fornece as etapas necessárias para ingerir as cobranças de RI de sua organização e alocar com precisão essas cobranças aos recursos apropriados em sua fatura do Azure EA.

Implicações na adaptação:

- Taxas de instância reservada de acesso - os custos de RI não são refletidos na conta de EA do Azure e precisarão ser trazidos para o Apptio por meio de um conector REST do Datalink (Classic).
- Amortização e alocação dos custos da instância reservada - Os custos do RI precisarão ser amortizados durante o período do RI e, em seguida, alocados aos recursos na conta que se beneficiam dessas compras do RI.
