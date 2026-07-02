---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Funções e permissões do usuário"
breadcrumb:
  - "Planning"
  - "Introdução"
source_path: "it-planning/planning/user-role-perm.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Funções e permissões do usuário

As funções e permissões do usuário controlam quem pode acessar, editar e gerenciar dados no Apptio Planning. As funções definem o nível de acesso dentro do aplicativo, enquanto as permissões fornecem um controle mais granular sobre tarefas específicas.

## Funções de usuário padrão

Apptio O planejamento inclui cinco funções de usuário predefinidas:

1. **Admin**
   1. Acesso total a todos os recursos do Apptio Planning.
   2. Inclui permissões administrativas em outros aplicativos Apptio por meio de FrontDoor.
2. **Proprietário do processo orçamentário**
   1. Acesso total a todos os recursos do Apptio Planning.
   2. Normalmente, é responsável por coordenar o ciclo orçamentário e gerenciar os ciclos de vida dos planos.
3. **Proprietário do centro de custo**

   1. Podem editar despesas para os departamentos aos quais estão atribuídos.
   2. Útil para colaboradores de orçamento em nível de departamento.
4. **Gerente de projetos do IIP**
   1. Podem editar despesas de projetos aos quais estão atribuídos no Planejamento Integrado de Investimentos (IIP).
   2. Concentrou-se no gerenciamento de finanças individuais em nível de projeto.
5. **Gerente de portfólio do IIP**
   1. Pode editar despesas de projetos atribuídos no IIP.
   2. Também pode conceder permissões de usuário em projetos e criar novos projetos.
   3. Normalmente, supervisiona um portfólio de projetos e aloca permissões.

## Funções customizadas

Além das funções padrão, você pode criar **funções personalizadas** em **FrontDoor**. As funções personalizadas permitem que você adapte o acesso para atender às necessidades específicas da sua organização.

## Permissões

A tabela a seguir lista as permissões disponíveis e suas descrições:

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| **Nome da permissão** | **Descrição** | **Admin** | **Proprietário do processo orçamentário** | **Proprietário do centro de custo** | **Gerente de projetos do IIP** | **Gerente de portfólio do IIP** |
| ApiCanReadData | Permite o acesso aos dados da tabela via API. Necessário para a integração da transparência de custos. | x |  |  |  |  |
| CanComment | Permite adicionar e visualizar comentários no nível do plano. | x | x | x | x | x |
| canEditExternalCode | Concede permissão para editar códigos externos. | x |  |  |  |  |
| CompanyProfileConfig | Permite a visualização e a edição das configurações do perfil da empresa. | x |  |  |  |  |
| CTIConfig | Permite a visualização e a edição das configurações da Integração da Transparência de Custos. | x | x |  |  |  |
| DataOrchestrationServiceFeatureFullAccess | Fornece acesso total a todos os pontos de extremidade/ações do Data Orchestration Service. Necessário para o site automatizado Data Management. | x |  |  |  |  |
| EditPlanning | Concede permissão para visualizar e editar planos. | x | x | x | x | x |
| EditReferenceData | Permite a edição, a importação e a publicação de dados de referência. | x | x |  |  |  |
| EditRestrictedDimensions | Permite a edição de dimensões e atributos configurados com acesso restrito. | x | x |  |  |  |
| ExternalLineEdit | Concede permissão para editar itens externos. | x | x |  |  |  |
| IIPProjectExpenseEdit | Concede permissão para visualizar e editar itens de linha do projeto. Também permite editar projetos na lista de projetos. |  |  |  | x |  |
| IIPProjectManage | Concede recursos completos de gerenciamento de projetos: crie e exclua projetos, edite dados de atributos e gerencie despesas em todos os projetos de um plano. | x | x |  |  |  |
| IIPProjectPermissionManage | Permite o acesso à página Project Permissions (Permissões do projeto). | x | x |  |  | x |
| ITPCompensationAdjustmentAllPeriodsEdit | Permite a edição de ajustes de remuneração do trabalho para todos os períodos do plano. | x | x |  |  |  |
| ITPCompensationAdjustmentEdit | Permite editar ajustes de remuneração do trabalho somente para ciclos de remuneração definidos. | x | x | x |  |  |
| ITPPlanSettingsEdit | Concede permissão para editar as páginas Plan Settings (Configurações do plano). | x | x |  |  |  |
| ITPPlanSettingsView | Concede permissão para visualizar (mas não editar) as páginas Plan Settings (Configurações do plano). |  |  |  |  |  |
| ManagePlans | Permite a criação, o arquivamento e a exclusão de planos. | x | x |  |  |  |
| ManageUsers | Concede acesso total para gerenciar funções e permissões de usuários no console Access Administration. | x |  |  |  |  |
| ViewAssets | Concede visibilidade à guia Ativos e permite a edição de detalhes de itens de linha de ativos. | x | x | x | x | x |
| ViewChangeHistoryFeatureViewOnly | Concede visibilidade ao Log de Eventos do Histórico de Alterações | x | x |  |  |  |
| ViewContracts | Concede visibilidade à guia Contratos e permite a edição dos detalhes do item de linha do contrato. | x | x | x | x | x |
| ViewLabor | Concede visibilidade à guia Trabalho e permite a edição de detalhes do item de linha de trabalho. | x | x | x | x | x |
| ViewPlanning | Permite a visualização, mas não a edição de planos. | x | x | x | x | x |
| ViewReferenceData | Permite a visualização, mas não a edição de dados de referência. | x | x |  |  |  |
| ViewSpendManagement | Permite a visualização, mas não a edição de dados reais no Gerenciamento de despesas. | x | x | x | x | x |
| ViewCloud | Permite visualizar e editar linhas na guia Nuvem | x | x | x | x | x |
| CanImporFromCloudability | Fornece acesso para importar dados de Cloudability para a guia Nuvem e excluir itens importados de Cloudability. | x | x |  |  |  |
| *ITPPredictiveForecastingFeatureFullAccess* | Oferece acesso total para gerar e visualizar previsões no planejamento. | x | x | x |  |  |

## Permissões de objeto de custo

As permissões de objetos de custo determinam quais usuários podem visualizar, editar, enviar ou aprovar planos em nível de departamento. Somente os usuários com a função **Proprietário do centro de custo** são elegíveis para receber acesso ao departamento. Os usuários com funções de **Administrador** ou **Proprietário do processo orçamentário** têm automaticamente acesso a todos os departamentos por padrão. O acesso do usuário é gerenciado no nível do plano por meio de **Plan** → **Settings** → **User Permissions.**

Consulte [Permissões de objeto de custo](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=configuration-cost-object-permissions "(Abre em uma nova guia ou janela)") para obter mais informações.

## Permissões de projeto

As permissões do projeto determinam quais usuários podem visualizar ou editar as despesas do projeto. Somente os usuários com a função **IIP Portfolio Manager** ou **IIP Project Manager** podem receber acesso ao projeto. Os usuários com funções de **Administrador** ou **Proprietário do processo orçamentário** têm automaticamente acesso a todos os departamentos por padrão. O acesso do usuário é gerenciado no nível do plano por meio de **Plan** → **Projects** → **Permissions.**

Consulte [Permissões do projeto](iip/project-level-access-control.html) para obter mais informações
