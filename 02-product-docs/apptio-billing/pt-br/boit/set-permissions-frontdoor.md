---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Definir permissões de usuário do Billing Standard no Frontdoor"
breadcrumb: []
source_path: "boit/set-permissions-frontdoor.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Definir permissões de usuário do Billing Standard no Frontdoor

Billing Standard no TBM Studio 12, os usuários usam o Frontdoor Admin Console para o gerenciamento de usuários. Para obter mais informações, consulte Sobre o Frontdoor, a página Apptio Access
Administration .

Para executar as ações a seguir, os usuários do Billing Standard precisam das seguintes permissões do Frontdoor:

- **ViewDataQualityAndMonthlyProcessReports** - Permite que o usuário acesse a Coleção de qualidade de faturamento.
- **ViewBusinessRelationshipReports** - Permite que o usuário acesse tudo, EXCETO a coleção Billing Quality.
- **ManageAndSendInvoices** - Permite que o usuário configure e envie contas de e-mail.
- **ViewServiceProviderReports** - Permite que o usuário acesse a coleção de relatórios do provedor de serviços de TI.
- **ViewBusinessUserReports** - Permite que o usuário acesse a coleção de relatórios de taxas de serviço.

As seguintes funções prontas para uso fornecem acesso ao aplicativo Billing Standard , mas restringem o acesso a TBM Studio:

- **Business Consumer** - Fornece acesso à coleta de relatórios de Taxas de Serviço e Transparência de Custos.
- **Business Owner (Proprietário do negócio** ) - Fornece acesso para visualizar todas as informações do site Billing Standard , com exceção de Data Quality (Qualidade dos dados) e Bill Distribution (Distribuição de faturas).
- **Service Manager** - Fornece acesso ao provedor de serviços de TI e às coleções de relatórios de taxas de serviço em Billing Standard .
