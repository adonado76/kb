---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Conectar Microsoft Azure"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
source_path: "admin/azure-cm-setup-premium.html"
images:
  - "images/TurboTarget-other-CSPs.png"
  - "images/azure-turbonomic-integration.jpg"
  - "images/regenerate_11_35_55_am_png.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conectar Microsoft Azure

Configurar as credenciais do Cloudability para acessar os dados de gerenciamento de custos do Azure exportando um arquivo CSV do Portal Azure. O arquivo CSV captura dados de custo e uso e os salva em um armazenament Azure. Em seguida, o usuário recebe o acesso Cloudability a esse armazenamento para ler os dados.

1. Configurar o gerenciamento de custos

   Configure os dados de faturamento formatados n CSV e para serem exportados automaticamente para um armazenamento n Azure diariamente.

   - Saiba mais sobre o [Connecting with Azure (MCA) - Exportações de gerenciamento de custos](azure-cm-exports-mca.html)
   - Saiba mais sobre como [se conectar com Azure (EA) - Exportações de gerenciamento de custos](azure-cm-exports-ea.html)
   - Saiba mais sobre o [Connecting with Azure (MCA) - Detalhes de custo API](azure-cmapi-mca.html)
   - Saiba mais sobre como [se conectar com Azure (EA) - API de detalhes de custos](azure-cmapi-ea.html)
2. Permitir o dimensionamento de direitos e o planejamento de RI

   Forneça ao Cloudability informações sobre a configuração de seus dados de faturamento no Portal Azure.

   - Saiba mais sobre [Setup Azure Rightsizing e Planejamento de RI](azure-advanced-rightsizing-premium.html)
3. Habilitar a coleta de métricas de memória

   Forneça ao Cloudability acesso somente leitura aos dados de custo e uso em seu armazenamento Azure.
4. - Saiba mais sobre a [configuração Azure Coleta de métricas de memória](azure-advanced-metrics.html)

Um exemplo do tipo de informação que o Cloudability exige do Portal Azure está listado abaixo;

- ID do locatário
- iD da assinatura
- nome do grupo de recursos
- nome da conta de armazenamento
- nome do contêiner
- nome de diretório
- nome da exportação de custos
- nome da exportação amortizada

Antes de começar

Antes de começar a configurar as credenciais do Cloudability, confirme que você é um administrador do Cloudability e que atende aos seguintes requisitos.

Certifique-se de que você tenha uma das seguintes funções Azure Active Directory em sua organização:

- Administrador global
- Desenvolvedor de aplicativos
- Administrador de aplicativos em nuvem
- Azure Savings Plan Reader (para clientes do site Cloudability Premium )

No portal Azure, você deve ter as permissões fornecidas por um desses escopos Azure para criar a exportação de dados de faturamento.

Saiba mais sobre [https://docs.microsoft.com/en-us/azure/cost-management-billing/costs/understand-work-scopes](https://docs.microsoft.com/en-us/azure/cost-management-billing/costs/understand-work-scopes "(Abre em uma nova guia ou janela)")

- Proprietário (pode visualizar/gerenciar tudo, inclusive a configuração de custos)
- Colaborador (pode visualizar/gerenciar tudo, inclusive a configuração de custos, exceto o controle de acesso)
- Contribuinte do gerenciamento de custos (pode visualizar/gerenciar a configuração de custos)

Observação: Para aplicar com sucesso a permissão “Enrollment Reader” à função do IAM (necessária para recursos avançados, como Planos de Economia e Planejamento de Instâncias Reservadas), a conta de usuário que executa o script do PowerShell deve, por sua vez, possuir, no mínimo, a função “Enrollment Writer” no EA.

Para contas Azure Storage :

- Você deve ter permissões de "gravação" para alterar a conta de armazenamento configurada (independentemente das permissões na exportação).
- A conta de armazenamento deve ser configurada para armazenamento em blob ou arquivo. Se possível, Cloudability você deve criar uma nova conta de armazenamento dedicada aos dados de gerenciamento de custos.

Para a função de leitor do Azure Savings Plan:

Se você tiver planos de economia para suas cargas de trabalho do Azure, habilite o acesso do Turbonomic a esses planos de economia atribuindo a função integrada Savings Plan Reader à entidade de serviço do Cloudability.

Observação: Antes de executar as etapas abaixo, o principal de serviço do aplicativo “ Cloudability ” já deve existir no(s) locatário(s) Azure onde a função “Savings Plan Reader” será atribuída. Siga primeiro os passos descritos nas seções [Conectando-se com Azure (EA) - Exportações de Gerenciamento de Custos](azure-cm-exports-ea.html), [Conectando-se com Azure (EA) - API de Detalhes de Custos](azure-cmapi-ea.html), [Conectando-se com Azure (MCA) - Exportações de Gerenciamento de Custos](azure-cm-exports-mca.html), [Conectando-se com Azure (MCA) - API de Detalhes de Custos](azure-cmapi-mca.html) e/ou [Configurar o Dimensionamento Adequado e o Planejamento de Instâncias Reservadas Azure](azure-advanced-rightsizing.html) para criar a entidade de serviço Cloudability no(s) locatário(s).

1. Faça login no portal Azure com uma conta de usuário que tenha permissões para atribuir funções a planos de poupança [https://portal.azure.com](https://portal.azure.com/ "(Abre em uma nova guia ou janela)").

   Certifique-se de que está trabalhando no diretório Azure correto, onde atribuirá a função Savings Plan Reader.
2. Acesse a página “Planos de poupança”: [https://portal.azure.com/#view/Microsoft\_Azure\_Reservations/ReservationsBrowseBlade/productType/SavingsPlan](https://portal.azure.com/#view/microsoft_azure_reservations/reservationsbrowseblade/producttype/savingsplan "(Abre em uma nova guia ou janela)")
3. Na página Planos de poupança, selecione Atribuição de função.
4. Na página Controle de acesso, selecione Adicionar atribuição de função.
5. Na página Adicionar atribuição de função :

   1. Selecione a guia Role (Função ).
   2. Na barra de pesquisa, digite Savings Plan Reader como sua palavra-chave de pesquisa.
   3. Selecione Savings Plan Reader na lista de funções incorporadas que é exibida e, em seguida, selecione Next.
   4. Na guia Membros, selecione + Selecionar membros.
   5. Pesquisar o CloudabilityUtilizationDataCollector principal do serviço.
   6. Adicione a entidade de serviço. Opcionalmente, especifique uma descrição para essa atribuição de função e, em seguida, selecione Next.
   7. Na guia Review + Assign, revise suas configurações e, em seguida, selecione Review + Assign.

Após a atualização para Cloudability Premium, o status dos relatórios de faturamento e dos relatórios avançados de cada uma das contas Azure (EA ou MCA) na página de listagem não será alterado. No entanto, o administrador do Cloudability precisa editar cada conta de assinatura seguindo as etapas que permitem que Cloudability compartilhe essas contas com Turbonomic.

Observação: é necessário ter permissões de administrador para acessar esta página.

1. Em Cloudability, navegue até Configurações > Credenciais do fornecedor > Azure.
2. Passe o cursor sobre o ícone da conta para a qual você deseja fazer o download do modelo. São exibidas opções adicionais.
3. Selecione o ![ícone de lápis de edição de credenciais](../../../../03-media/cloudability-premium/images/regenerate_11_35_55_am_png.jpg) ícone para abrir a opção “Editar uma credencial”.
4. O painel Editar uma credencial é aberto.
5. Selecione a opção no botão de alternância Ajuste avançado de recursos.
6. Gerar script de configuração.
7. Atualize as permissões executando o script.
8. Reverificar a conta.

Existem permissões adicionais Turbonomic que são adicionadas às permissões básicas (Dados de cobrança), avançadas (Dados de utilização) e Otimizar recursos (executar ações). Depois que sua conta for verificada, a lista de permissões poderá ser visualizada selecionando a opção Detalhes em cada conta Azure listada em Cloudability.

![captura de tela das permissões do turbonomic](../../../../03-media/cloudability-premium/images/azure-turbonomic-integration.jpg)

**Status de credenciais**

Cloudability A tela de credenciais do fornecedor exibe o status da conta a partir de:

- Cloudability
- Turbonomic

Depois que os modelos mais recentes forem executados, o status da conta deverá estar sincronizado entre Cloudability e Turbonomic. Para obter detalhes sobre o status da conta, verifique a seção de detalhes da conta.

![](../../../../03-media/cloudability-premium/images/TurboTarget-other-CSPs.png)

- **[Conexão com Azure EA - Gerenciamento de custos de exportação](../admin/azure-cm-exports-ea.html)**
- **[Conexão com Azure EA - API de detalhes de custos](../admin/azure-cmapi-ea.html)**
- **[Conectando-se com Azure MCA - Exportações de gerenciamento de custos](../admin/azure-cm-exports-mca.html)**
- **[Conectando-se com Azure MCA - Detalhes de custo API](../admin/azure-cmapi-mca.html)**
- **[Configure Credenciais Avançadas, Azure Rightsizing e Planejamento de Instância Reservada](../admin/azure-advanced-rightsizing-premium.html)**
- **[Azure Tags](../admin/azure-resource-group-tags.html)**
- **[Configurar uma coleta de métricas de memória d Azure](../admin/set_up_azure_memory_metrics_collection.html)**  
   O agente de monitoramento Azure coleta dados de monitoramento de máquinas virtuais Azure e os envia para o monitor Azure.
- **[Referência de permissões Microsoft Azure](../admin/permissions-reference-azure.html)**
