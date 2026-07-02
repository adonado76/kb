---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Funções e permissões em Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Administração"
source_path: "admin/iam.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Funções e permissões em Cloudability

As funções concedem aos usuários permissão para acessar visualizações e funções específicas no site Cloudability.

Por padrão, todas as funções de usuário têm acesso a alguns recursos básicos do Cloudability, incluindo análises de custos para relatórios, painéis e o TrueCost Explorer. É possível acessar recursos adicionais atribuindo permissões à função.

**Funções no livro “ Cloudability ”**

As seguintes funções podem ser atribuídas aos usuários do Cloudability :

| Nome da função | Permissões de função | Tipos de inscrição |
| --- | --- | --- |
| Usuário do assistente de IA | O usuário com essa permissão poderá ver o widget do Assistente de IA d Apptio em Cloudability e poderá interagir com ele. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| AdvancedContainersFullAccess | Função de administrador para o Cloudability Contêineres avançados com tecnologia Kubecost. | AdvancedContainers, Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| AdvancedContainersViewOnly | Função de “Somente visualização” para os contêineres avançados do Cloudability, com tecnologia Kubecost. | AdvancedContainers, Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Captura de dados na nuvem | Essa função padrão é utilizada para usuários do CDI. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Admin | Concede acesso a todas as funções administrativas no site Cloudability. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Administração de Cobrança | Permite que os clientes definam as preferências de moeda para sua organização no Cloudability. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Usuário de automação de governança | Essa função possui a permissão “ GovernanceFeatureConfigurationFullAccess ”. O usuário com essa função terá acesso total às operações de configuração (exceto políticas) do recurso “Governança” do Cloudability. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Responsável pela aprovação de comunicados de imprensa sobre governança | Essa função possui a permissão “ GovernanceFeaturePRApprovalAccess ”. O usuário com essa função terá acesso para aprovar pull requests bloqueados no recurso “Governança” do Cloudability. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Administração de Políticas de Governança | Essa função possui a permissão “ GovernanceFeaturePolicyFullAccess ”. O usuário com essa função terá acesso total à funcionalidade de configuração de políticas (visualizar, criar e atualizar políticas) no item de menu “Governança” do recurso “ Cloudability ”. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Usuário sem restrições | Essa função possui todas as permissões da função de usuário “ Cloudability ” e do grupo “ ViewsFeatureFullAccess ”. O usuário com essa função terá acesso a todos os dados na nuvem da sua organização. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Savings Automation Admin | Função padrão para usuários que devem ter acesso administrativo ao aplicativo Cloudability Savings Automation. | Cloudability Savings Automation |
| Cloudability Savings Automation Usuário | Função padrão para usuários não administradores do Cloudability Savings Automation. | Cloudability Savings Automation |
| Cloudability Usuário | Acesso restrito ao Cloudability, sem quaisquer privilégios de modificação de dados. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudability Gerenciamento de visualizações (apenas para migração) | Por favor, NÃO utilize essa função, pois ela se destina exclusivamente à migração do sinalizador “restrito”. Como estamos descontinuando o sinalizador “restricted” em Cloudability, os usuários que NÃO possuem o sinalizador “restricted” recebem essa função automaticamente para continuar acessando a página de gerenciamento do View. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| CloudabilityContainerProvisioner | É possível provisionar e implantar o agente de métricas em contêineres. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| CloudabilityContainerUploader | É possível enviar dados de contêineres para Cloudability. | Cloudability Premium, Cloudability, Cloudability Standard, Cloudability Essential |
| Cloudwiry Admin | Função padrão para usuários que devem ter acesso administrativo ao aplicativo Cloudwiry. | Cloudwiry, Cloudability Savings Automation |
| Usuário do Cloudwiry | Função padrão para usuários que devem ter acesso não administrativo ao aplicativo Cloudwiry. | Cloudwiry, Cloudability Savings Automation |
| Usuário da API do MSP | Acesso a todos os recursos do MSP/CCB em seu próprio ambiente. | Faturamento comercial (MSP) |
| Administrador do MSP | Acesso a todos os recursos do MSP/CCB em seu próprio ambiente. Acesso de administrador nos ambientes dos usuários finais. | Faturamento comercial (MSP) |
| Gerenciador de Faturamento MSP | Acesso ao módulo de faturamento e à tabela de preços para cada consumidor final. Essa persona poderá editar/definir tarifas e margens de lucro para cada consumidor final, bem como acessar dados de custo/consumo de todos os consumidores finais e adicionar custos e itens adicionais. | Faturamento comercial (MSP) |

**Fatores que Access Administration influenciam o Cloudability**

As seguintes Access Administration funções estão mapeadas para as funções correspondentes no site Cloudability :

| Nome da função | Permissões de função |
| --- | --- |
| Admin : | Essa função permite adicionar, editar ou excluir usuários em Access Administration . Essa função abrange todas as aplicações do Apptio, incluindo o Cloudability. |
| Administrador | Essa função tem acesso total ao Cloudability.  Essa função é concedida aos usuários que fazem login em Cloudability com a função Admin ou Cloudability Admin em Access Administration . |
| Usuário | Essa função tem acesso limitado ao site Cloudability.  Essa função é concedida aos usuários que fazem login em Cloudability com a função de usuário Access Administration “ Cloudability ”. |

**Identidade e controle de acesso**

No Cloudability, o Gerenciamento de Identidade e Acesso (IAM) e o Controle de Acesso Corporativo (EAC) são utilizados para fornecer controle de identidade e acesso às funções às quais os usuários têm permissão para acessar.

O IAM e o EAC oferecem suporte a permissões que controlam os recursos do Cloudability, a criação de funções personalizadas alinhadas à identidade do usuário e o mapeamento de funções do provedor de identidade ( IdP ) para funções padrão e personalizadas do Cloudability.

Observação: as funções específicas atribuídas a um usuário no Access Administration substituirão as funções do mapeamento de funções do IdP.

**Personas e casos de uso**

As permissões do IAM e do EAC são baseadas em funções, permitindo que os usuários acessem recursos de acordo com sua função ou perfil. A tabela a seguir apresenta exemplos de casos de uso e as personas correspondentes.

| Persona | Caso de uso | Cloudability Uso |
| --- | --- | --- |
| Usuário avançado | Centro de Excelência em Nuvem ( CCoE )  Foco: profundo conhecimento em gestão de custos na nuvem, administração de plataformas e capacitação de colegas | Diária |
| Gerente de Programa ou Product Owner | Foco: custos da nuvem no contexto do projeto ou produto de que são responsáveis | Conforme a necessidade; semanalmente; dependendo da necessidade |
| DevOps Usuário | Operações em nuvem  Foco: otimização e automação do uso | Conforme a necessidade; semanalmente |
| Usuário da área financeira | Análise e relatórios de cadência no nível organizacional  Foco: planejamento, elaboração de orçamento e previsão | Semanal; mensal; trimestral |
| Executivo | Alta administração  Foco: panorama financeiro e orientação | Ad hoc; trimestral |

Não é possível excluir uma função a menos que todos os usuários atribuídos a ela tenham sido excluídos.

**Utilização do controle de identidade e acesso**

Nota:

Você precisa ser um Access Administration administrador para acessar os controles de identidade e acesso.

Você pode usar o Access Administration portal de administração do Access para acessar as funções de atribuição de funções e permissões aos usuários no Cloudability.

[Gerenciamento de permissões e funções dos usuários](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=management-manage-user-permissions-roles "(Abre em uma nova guia ou janela)")

**Permissões compatíveis**

Quando um usuário faz login em Cloudability, as permissões atribuídas por meio do Access
Administration portal de Administração de Acesso controlam o acesso aos recursos aos quais o usuário pode acessar, com base nas permissões atribuídas a ele.

As permissões compatíveis com o ` Cloudability ` são apresentadas na tabela a seguir:

| Nome da permissão | Descrição | Tipos de inscrição |
| --- | --- | --- |
| AccountGroupManagementFeatureFullAccess | Permitir que os usuários atribuídos a uma função com essa permissão acessem todas as funcionalidades (visualizar, criar, atualizar) no item de menu “Grupos de contas” do recurso Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| AccountGroupManagementFeatureViewOnlyAccess | permite que os usuários atribuídos a uma função com essa permissão visualizem, mas não editem, contas e grupos de contas no item de menu “Grupos de contas” do recurso Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| AdvancedContainersFullAccess | Permissão de administrador para o Cloudability Contêineres avançados com tecnologia Kubecost. | Advanced Containers (com tecnologia Kubecost), Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| AdvancedContainersViewOnly | Permissão de apenas visualização para os contêineres avançados do Cloudability, com tecnologia Kubecost. | Advanced Containers (com tecnologia Kubecost), Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| AdvisorFullAccess | Os usuários com essa permissão podem visualizar todos os gráficos e dados do Turbonomic e executar planos. No entanto, os usuários não podem usar o Place para reservar cargas de trabalho, criar políticas ou executar quaisquer ações recomendadas. | Cloudability Premium, Turbonomic |
| AnomalyDetectionAlertSharingFeatureAddOn | Adiciona a possibilidade de compartilhar alertas de assinatura de anomalias com outros usuários da organização. | Cloudability |
| AnomalyDetectionFeatureFullAccess | Permitir que os usuários atribuídos a uma função com essa permissão tenham acesso a todas as funcionalidades (visualizar, criar, atualizar) no item de menu “Detecção de anomalias” da funcionalidade “ Cloudability ”. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| AutomationFeatureFullAccess | Permitir que os usuários atribuídos a uma função com essa permissão tenham acesso a todas as funcionalidades (visualizar, criar, atualizar) no item de menu “Automação” do recurso “ Cloudability ”. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| AutomatorFullAccess | Os usuários com essa permissão podem utilizar todos os recursos do Turbonomic (incluindo Plan, Park e Place), mas não podem configurar a instalação do Turbonomic nem criar políticas. | Cloudability Premium, Turbonomic |
| AWSResourceInventoryFullAccess | Essa permissão deve ser concedida explicitamente a um usuário caso ele precise acessar o recurso “ AWS ” (Inventário de Recursos) no CLDY. Há também um sinalizador de recurso no backend para ativar o recurso “ AWS ” (Inventário de Recursos) para uma organização específica do cliente. No entanto, para que um usuário possa visualizar este módulo, é necessário que essa permissão seja concedida a ele. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| BudgetsAndForecastFeatureFullAccess | Permitir que os usuários atribuídos a uma função com essa permissão acessem todas as funcionalidades (visualizar, criar, atualizar) disponíveis nos itens de menu “Mês atual”, “Previsão” e “Orçamentos” do recurso “ Cloudability ”. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| BudgetsFeatureViewOnlyAccess | Permitir que os usuários atribuídos a uma função com essa permissão visualizem, mas não editem, todos os orçamentos e seus valores no item de menu “Orçamentos” do recurso Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| BusinessMappingsFeatureFullAccess | Permitir que os usuários atribuídos a uma função com essa permissão tenham acesso a todas as funcionalidades (visualizar, criar, atualizar) no item de menu “Mapeamentos de negócios” do recurso Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| BusinessMappingsFeatureViewOnlyAccess | permitir que os usuários atribuídos a uma função com essa permissão visualizem, mas não editem, os mapeamentos de negócios e suas definições no item de menu “Mapeamentos de negócios” do recurso “ Cloudability ”. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CloudabilityContainerProvisioning | Permissão para provisionar e implantar o agente de métricas do Containers. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CloudabilityContainerUploading | Permissão para enviar dados do Containers para Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CloudabilityPlanningCanAccess | Este usuário pode acessar a funcionalidade de planejamento d Cloudability. | Cloud Financial Planning, Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CloudabilityPlanningFullAccess | Permissão de acesso total global. | Cloud Financial Planning, Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CloudabilityPlanningManage | Criar/Duplicar/Excluir/Renomear Plans/ChangeBaseline/Dimensons(CRUD ). | Cloud Financial Planning, Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CloudwiryAdminFullAccess | Permita que os usuários atribuídos a uma função com essa permissão tenham acesso a todas as funcionalidades de nível administrativo do aplicativo Cloudwiry. | Cloudwiry |
| CloudwiryUserFullAccess | Permita que os usuários atribuídos a uma função com essa permissão tenham acesso a todas as funcionalidades do aplicativo Cloudwiry no nível do usuário. | Cloudwiry |
| CommitmentPreferencesFeatureFullAccess | Permitir que os usuários atribuídos a uma função com essa permissão tenham acesso a todas as funcionalidades (visualizar, criar, atualizar) no item de menu “Preferências de compromisso” do recurso Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CommitmentPreferencesFeatureViewOnly | permitir que os usuários atribuídos a uma função com essa permissão tenham acesso à funcionalidade para visualizar as informações exibidas no item de menu “Preferências de compromisso” do recurso Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| ContainersFeatureFullAccess | tudo o que está incluído na permissão "ContainersFeatureViewOnly", além da capacidade de criar e atualizar um Cldy Containers Agent. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| ContainersFeatureViewOnly | permite que os usuários atribuídos a uma função com essa permissão acessem a funcionalidade para visualizar as informações exibidas no item de menu “Containers” ( Cloudability ). | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CostSharingBasicFeatureAccess | Permita que os usuários atribuídos a uma função com essa permissão acessem todas as funcionalidades (visualizar, criar, atualizar) das alocações e regras no item de menu “ Cloudability ” `Cost Sharing`, exceto os recursos de telemetria. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CostSharingBasicFeatureViewOnlyAccess | Permita que os usuários atribuídos a uma função com essa permissão visualizem todas as alocações, regras e suas definições no item de menu “ Cloudability ” `Cost Sharing`, mas sem a capacidade de editá-las ou excluí-las. Eles também não podem acessar o recurso de telemetria. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CostSharingBasicMaintainFeatureAccess | Permite acesso total a todos os pontos de extremidade do Serviço de Modelagem, exceto ao recurso de telemetria. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CostSharingFeatureFullAccess | Permita que os usuários atribuídos a uma função com essa permissão acessem todas as funcionalidades (visualizar, criar, atualizar) de alocações, regras e uploads de dados de telemetria no item de menu “Cost Sharing” ( Cloudability ). | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CostSharingFeatureViewOnlyAccess | Permitir que os usuários atribuídos a uma função com essa permissão visualizem, mas não editem, a divisão de custos e suas definições no item de menu “Business Mappings > Cost Sharing” do Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| CostSharingMaintainFeatureFullAccess | Permite acesso total a todos os endpoints do Serviço de Modelagem. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| DataTrackingFeatureBasicAccess | Permita que os usuários atribuídos a uma função com essa permissão acessem o recurso “ DataTracking ” no Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| DeployerFullAccess | Os usuários com essa permissão podem visualizar todos os gráficos e dados do Turbonomic, usar o Place para reservar cargas de trabalho e criar políticas e modelos de alocação. No entanto, os usuários não podem executar planos nem realizar nenhuma das ações recomendadas. | Cloudability Premium, Turbonomic |
| GovernanceFeatureConfigurationFullAccess | Acesse todas as funcionalidades de configuração (visualizar, criar, atualizar), exceto as políticas, no item de menu “Governança” da funcionalidade “ Cloudability ”. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| GovernanceFeaturePolicyFullAccess | Acesse todas as funcionalidades de configuração de políticas (visualizar, criar, atualizar) no item de menu “Governança” do recurso “ Cloudability ”. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| GovernanceFeaturePRApprovalAccess | Permitir que os usuários aprovem Pull Requests que estejam bloqueados no Cloudability Governance por não cumprirem as políticas de governança. Essa permissão está incluída na função “ Cloudability Governance PR Approver”. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| GovernanceFeatureViewOnly | Acesse a funcionalidade para visualizar as informações no item de menu “Governança” do recurso “ Cloudability ”. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| InvoiceGeneration | Importar dados, acessar e criar notas fiscais. | Faturamento comercial (MSP) |
| MspBillingCloudSpendApiRead | Acesso de leitura à API de gastos em nuvem do Cloudability MSP /CCB. | Faturamento comercial (MSP) |
| MspBillingCustomLineItemsRead | Acesso de leitura a “ Cloudability MSP ” / “CCB Custom Line Items”. | Faturamento comercial (MSP) |
| MspBillingCustomLineItemsWrite | Acesso de gravação às linhas de item personalizadas d Cloudability MSP /CCB. | Faturamento comercial (MSP) |
| MspBillingExternalApiPricingRead | Acesso de leitura à API externa de preços d Cloudability MSP /CCB. | Faturamento comercial (MSP) |
| MspBillingExternalApiPricingWrite | Acesso de gravação à API externa de preços d Cloudability MSP /CCB. | Faturamento comercial (MSP) |
| MspBillingPricingRead | Acesso de leitura aos catálogos de preços d Cloudability MSP /CCB. | Faturamento comercial (MSP) |
| MspBillingPricingWrite | Acesso de gravação aos catálogos de preços d Cloudability MSP /CCB. | Faturamento comercial (MSP) |
| MspBillingSettingsRead | Acesso de leitura às configurações d Cloudability MSP /CCB. | Faturamento comercial (MSP) |
| MspBillingSettingsWrite | Acesso de gravação às configurações d Cloudability MSP /CCB. | Faturamento comercial (MSP) |
| ObserverFullAccess | Os usuários com essa permissão podem visualizar o ambiente, incluindo a Página Inicial e os Painéis. | Cloudability Premium, Turbonomic |
| OperationalObserverFullAccess | Os usuários com essa permissão podem visualizar o ambiente, incluindo a Página Inicial, os Painéis, os Grupos e as Políticas. | Cloudability Premium, Turbonomic |
| OrgCurrencyFeatureAccess | Permite que os usuários atribuídos a uma função com essa permissão acessem a tela de moedas e alterem a moeda-base padrão de uma organização. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RateOptimizationFeatureFullAccess | Permita que os usuários atribuídos a uma função com essa permissão acessem todas as funcionalidades disponíveis no item de menu “Otimização de tarifas” do recurso “ Cloudability Savings Automation ”. | Cloudability Savings Automation, Cloudwiry |
| RateOptimizationFeatureViewOnly | Permita que os usuários atribuídos a uma função com essa permissão visualizem as informações exibidas no item de menu “Otimização de tarifas” do recurso “ Cloudability Savings Automation ”. | Cloudability Savings Automation, Cloudwiry. |
| ReadBillingExternalApi | É possível ler a API externa de faturamento. | Faturamento comercial (MSP) |
| ReadOrgStructure | Acesso de leitura ao Serviço de Estrutura Organizacional | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard, Serviço de Estrutura Organizacional. |
| ReservationPortfolioFeatureFullAccess | Permitir que os usuários atribuídos a uma função com essa permissão acessem todas as funcionalidades (visualizar, criar, atualizar) no item de menu “Portfólio de reservas” do Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| ReservedInstancePlannerFeatureFullAccess | Permitir que os usuários atribuídos a uma função com essa permissão acessem todas as funcionalidades (visualizar, criar, atualizar) disponíveis no item de menu “Reserved Instance Planner” do Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingFeatureCanSnooze | Permitir que os usuários atribuídos a uma função com essa permissão realizem ações (criar, atualizar, excluir) relacionadas ao adiamento de recomendações no item de menu “Rightsizing” do recurso “ Cloudability ”. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingFeatureFullAccess | Permitir que os usuários atribuídos a uma função com essa permissão acessem todas as funcionalidades (visualizar, criar, atualizar) no item de menu “Rightsizing” do recurso “ Cloudability ”. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingFeatureViewOnly | permitir que os usuários atribuídos a uma função com essa permissão acessem a funcionalidade para visualizar as informações exibidas no item de menu “Rightsizing” do recurso “ Cloudability ”. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingPoliciesFeatureFullAccess | Permitir que os usuários atribuídos a uma função com essa permissão tenham acesso a todas as funcionalidades (visualizar, criar, atualizar) no item de menu “Políticas de redimensionamento” ( Cloudability ). | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingPoliciesFeatureViewOnly | permitir que os usuários atribuídos a uma função com essa permissão acessem a funcionalidade para visualizar as informações exibidas no item de menu “Políticas de redimensionamento” ( Cloudability ). | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingPreferencesFeatureFullAccess | Permitir que os usuários atribuídos a uma função com essa permissão tenham acesso a todas as funcionalidades (visualizar, criar, atualizar) no item de menu “Preferências de ajuste de tamanho” ( Cloudability ). | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingPreferencesFeatureViewOnly | permitir que os usuários atribuídos a uma função com essa permissão acessem a funcionalidade para visualizar as informações exibidas no item de menu “Preferências de ajuste de tamanho” ( Cloudability ). | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| RightsizingRoiFeatureFullAccess | Permitir que os usuários atribuídos a uma função com essa permissão acessem todas as funcionalidades (visualizar, criar, atualizar) disponíveis no item de menu “Rightsizing ROI” do Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| SavingsPlansFeatureFullAccess | permitir que os usuários atribuídos a uma função com essa permissão tenham acesso a todas as funcionalidades (visualizar, criar, atualizar) no item de menu “Planos de Poupança” do recurso “ Cloudability ”. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| ScopedAdvisorFullAccess | Os usuários com essa permissão podem visualizar todos os gráficos e dados do Turbonomic e executar planos. No entanto, os usuários não podem usar o Place para reservar cargas de trabalho, criar políticas ou executar quaisquer ações recomendadas. Um administrador do site do Turbonomic deve definir um escopo para esse usuário na visualização “Gerenciamento de usuários” ( Turbonomic ). | Cloudability Premium, Turbonomic |
| ScopedAutomatorFullAccess | Os usuários com essa permissão podem utilizar todos os recursos do Turbonomic (incluindo Plan, Park e Place), mas não podem configurar a instalação do Turbonomic nem criar políticas. Um administrador do site do Turbonomic deve definir um escopo para esse usuário na visualização “Gerenciamento de usuários” ( Turbonomic ). | Cloudability Premium, Turbonomic |
| ScopedDeployerFullAccess | Os usuários com essa permissão podem visualizar todos os gráficos e dados do Turbonomic, usar o Place para reservar cargas de trabalho e criar políticas e modelos de alocação. No entanto, os usuários não podem executar planos nem realizar nenhuma das ações recomendadas. Um administrador do site do Turbonomic deve definir um escopo para esse usuário na visualização “Gerenciamento de usuários” ( Turbonomic ). | Cloudability Premium, Turbonomic |
| ScopedObserverFullAccess | Os usuários com essa permissão podem visualizar o ambiente, incluindo a Página Inicial e os Painéis. Um administrador do site do Turbonomic deve definir um escopo para esse usuário na visualização “Gerenciamento de usuários” ( Turbonomic ). | Cloudability Premium, Turbonomic |
| ScopedOperationalObserverFullAccess | Os usuários com essa permissão podem visualizar o ambiente, incluindo a Página Inicial, os Painéis, os Grupos e as Políticas. Um administrador do site do Turbonomic deve definir um escopo para esse usuário na visualização “Gerenciamento de usuários” ( Turbonomic ). | Cloudability Premium, Turbonomic |
| ScopedSharedAdvisorFullAccess | Os usuários com essa permissão podem visualizar a Página Inicial e os Painéis, mas só têm acesso às VMs e aos Aplicativos. Os usuários não podem executar ações do tipo “ Turbonomic ”. Um administrador do site do Turbonomic deve definir um escopo para esse usuário na visualização “Gerenciamento de usuários” ( Turbonomic ). | Cloudability Premium, Turbonomic |
| ScopedSharedObserverFullAccess | Os usuários com essa permissão podem visualizar a Página Inicial e os painéis personalizados, mas só têm acesso às VMs e aos aplicativos. Os usuários não podem visualizar os painéis executivos nem executar ações do “ Turbonomic ”. Um administrador do site do Turbonomic deve definir um escopo para esse usuário na visualização “Gerenciamento de usuários” ( Turbonomic ). | Cloudability Premium, Turbonomic |
| ScorecardsFeatureFullAccess | permitir que os usuários atribuídos a uma função com essa permissão acessem todas as funcionalidades (visualizar, criar, atualizar) no item de menu “Scorecards” do recurso “ Cloudability ” | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| SiteAdminFullAccess | Os usuários com essa permissão podem utilizar todos os recursos do Turbonomic e modificar as configurações específicas do site para configurar a instalação do Turbonomic. Os usuários também podem administrar Grupos, Políticas, Fluxos de Trabalho, Modelos, Faturamento/Custos e Configuração de Destino, mas não E-mail, Licenças, Atualizações e Manutenção. Os usuários com essa função podem definir o escopo em outras contas. | Cloudability Premium, Turbonomic |
| TagExplorerFeatureFullAccess | Permitir que os usuários atribuídos a uma função com essa permissão tenham acesso a todas as funcionalidades (visualizar, criar, atualizar) no item de menu “Tag Explorer” do recurso Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| TagsAndLabelsFeatureFullAccess | Permitir que os usuários atribuídos a uma função com essa permissão acessem todas as funcionalidades (visualizar, criar, atualizar) disponíveis no item de menu “Tags” do recurso Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| TagsAndLabelsFeatureViewOnlyAccess | permite que os usuários atribuídos a uma função com essa permissão visualizem, mas não editem, todas as dimensões do Cloudability e suas chaves de tag mapeadas, bem como os rótulos do k8, no item de menu “Tags” do Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| TurbonomicFeatureFullAccess | Permitir que os usuários atribuídos a uma função com essa permissão acessem todas as funcionalidades (visualizar, criar, atualizar) no item de menu " Turbonomic " Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium |
| UserManagementFeatureFullAccess | permitir que os usuários atribuídos a uma função com essa permissão acessem todas as funcionalidades disponíveis no item de menu “Usuários” do recurso Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| VendorCredentialsFeatureFullAccess | Permitir que os usuários atribuídos a uma função com essa permissão tenham acesso a todas as funcionalidades (visualizar, criar, atualizar) no item de menu “Credenciais do fornecedor” do recurso Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Savings Automation, Cloudability Standard, Cloudwiry |
| ViewBillMx | Visualizar dados. | Faturamento comercial (MSP) |
| ViewsFeatureCreateOwnViewsAccess | Permita que os usuários atribuídos a uma função com essa permissão visualizem todas as visualizações e suas definições no item de menu “Visualizações” do recurso “ Cloudability ”, mas que possam editar ou excluir apenas as visualizações criadas por esse usuário. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| ViewsFeatureFullAccess | Permitir que os usuários atribuídos a uma função com essa permissão acessem todas as funcionalidades (visualizar, criar, atualizar) disponíveis no item de menu “Visualizações” do recurso Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| WorkloadPlacementFeatureFullAccess | Permitir que os usuários atribuídos a uma função com essa permissão tenham acesso a todas as funcionalidades (visualizar, criar, atualizar) no item de menu “Workload Placement” (Alocação de carga de trabalho) do Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| WorkloadPlanningFeatureCanAccess | Permita que os usuários atribuídos a uma função com essa permissão tenham acesso a todas as funcionalidades (visualizar, criar, atualizar) no item de menu “Planejamento de carga de trabalho” do Cloudability. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| WorkloadPlanningFeatureFullAccess | Permita que os usuários designados a uma função de administrador com essa permissão tenham acesso a todas as funcionalidades (visualizar, criar, atualizar) no item de menu “Planejamento de carga de trabalho” do Cloudability. Eles também têm a possibilidade de visualizar/atualizar quaisquer cargas de trabalho criadas por outros usuários. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| WorkloadPlanningPreferencesViewOnly | Permita que os usuários designados a uma função de administrador com essa permissão configurem preferências e restrições para sua organização no que diz respeito ao planejamento de cargas de trabalho. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard |
| WriteOrgStructure | Acesso de gravação ao Serviço de Estrutura Organizacional. | Cloudability, Cloudability Essential, Cloudability Premium, Cloudability Standard, Serviço de Estrutura Organizacional |
