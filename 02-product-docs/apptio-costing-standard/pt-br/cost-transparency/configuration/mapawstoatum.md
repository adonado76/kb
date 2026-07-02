---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Mapeie o AWS Marketplace para ATUM"
breadcrumb: []
source_path: "cost-transparency/configuration/mapawstoatum.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Mapeie o AWS Marketplace para ATUM

Se você consumir serviços do AWS Marketplace, deverá ingerir e modelar essas contas da mesma forma que suas contas de serviço do AWS. AWS cria um arquivo de faturamento separado do AWS Marketplace para cada relatório de faturamento que você configurar para ser criado em suas preferências de faturamento.

Assim como nas contas de serviços típicas do AWS, o Apptio recomenda o uso do relatório de alocação de custos do AWS Marketplace que agrega em nível mensal. Para obter mais informações sobre os serviços do AWS Marketplace, acesse [https://aws.amazon.com/marketplace/](https://community.apptio.com/external-link.jspa?url=https%3A%2F%2Faws.amazon.com%2Fmarketplace%2F "(Abre em uma nova guia ou janela)").

Aplica-se a: Apptio Costing Standard ou Apptio Cloud Cost Management em execução em TBM Studio v12.3.3 ou posterior.

## Tarefa 1: Configure um novo conector DataLink para automatizar a ingestão de sua fatura do Marketplace

### Procedimento

1. Crie um novo conector Datalink (Classic) AWS ou copie um conector AWS existente (Saiba mais).
2. Configure a autenticação.

   Observação: ao usar a delegação, se você copiar um conector existente, essa seção já estará preenchida.
3. Clique em Billing Report (Relatório de faturamento).
4. Em Tipo de relatório, selecione Avançado.
5. Em File Pattern (Padrão de arquivo), digite o seguinte padrão:"<your AWS account number>-aws-cost-allocation-AWSMarketplace- {CYYY} - {MM}.csv>"
6. Configure o Apptio Destination, Notifications e Scheduling com base em seus requisitos específicos.
