---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Configure Credenciais Avançadas, Azure Rightsizing e Planejamento de Instância Reservada"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
  - "Conectar Microsoft Azure"
source_path: "admin/azure-advanced-rightsizing-premium.html"
images:
  - "images/azure-cldy-turbo-integration.jpg"
  - "images/azure-premium-1.jpg"
  - "images/azure-rightsizing-credentials.jpg"
  - "images/azure_rightsizing11.jpg"
  - "images/azure_rightsizing12.jpg"
  - "images/azure_rightsizing16.jpg"
  - "images/azure_rightsizing7.jpg"
  - "images/azure_rightsizing8.jpg"
  - "images/azure_rightsizing9.jpg"
  - "images/details.jpg"
  - "images/regenerate_11_35_55_am_png.jpg"
  - "images/vc_ss1.jpg"
  - "images/vc_ss2.jpg"
  - "images/vc_ss4.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Configure Credenciais Avançadas, Azure Rightsizing e Planejamento de Instância Reservada

Azure A credencial de nível de assinatura desbloqueia os seguintes recursos no site Cloudability :

- Aplicar tags de grupos de recursos a recursos dentro dos grupos de recursos

  Saiba mais sobre o [mapeamento de tags](tag-data.html)
- Otimização - por meio de Rightsizing e Instâncias Reservadas (RIs)

  Saiba mais Obtenha [recomendações para dimensionar seus recursos de nuvem com o Rightsizing](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

  Saiba mais sobre o [portfólio de reservas](../product/reservation-portfolio.html)

Atualmente, nossa plataforma usa uma função personalizada chamada “CloudabilitySubscriptionDataReader” on Subscriptions com as permissões mencionadas abaixo para obter os dados necessários:

- Microsoft.Compute/virtualMachines/read
- Microsoft.Compute/virtualMachines/extensions/read
- Microsoft.Compute/disks/read
- Microsoft.Sql/servers/databases/read
- Microsoft.Sql/servers/read
- Microsoft.Sql/servers/elasticpools/read
- Microsoft.Insights/metricDefinitions/read
- Microsoft.Insights/metrics/read
- Microsoft.Resources/subscriptions/read
- Microsoft.Resources/subscriptions/resourceGroups/read
- Microsoft.Authorization/roleAssignments/read
- Microsoft.Insights/Metricnamespaces/Read
- Microsoft.Consumption/usageDetails/read
- Microsoft.Consumption/pricesheets/read
- Microsoft.CostManagement/query/read
- Microsoft.Commerce/UsageAggregates/read
- Microsoft.Commerce/RateCard/read
- Microsoft.Network/networkInterfaces/read

Utilizamos o fluxo de concessão de autorização do OAuth 2.0 para registrar nossa aplicação e criar uma entidade de serviço no locatário Azure. Você pode ler mais sobre esse processo aqui: [https://docs.microsoft.com/en-us/azure/active-directory/develop/app-objects-and-service-principals](https://docs.microsoft.com/en-us/azure/active-directory/develop/app-objects-and-service-principals "(Abre em uma nova guia ou janela)")

Antes de começar

Você deve atender aos requisitos mínimos para obter uma credencial bem-sucedida.

- Você é um administrador do Cloudability. A função Cloudability Administrator lhe dá acesso à página Vendor Credentials (Credenciais do fornecedor), onde você pode gerenciar suas credenciais.

  Saiba mais sobre como [gerenciar credenciais de fornecedores](manage-vendor-credentials.html)
- Você tem uma das seguintes funções Azure Active Directory em sua organização:
  - Administrador global
  - Desenvolvedor de aplicativos
  - Administrador de aplicativos em nuvem

  Isso é necessário para o fluxo de concessão de autorização do OAuth 2.0. Veja [https://docs.microsoft.com/en-us/azure/active-directory/develop/app-objects-and-service-principals](https://docs.microsoft.com/en-us/azure/active-directory/develop/app-objects-and-service-principals "(Abre em uma nova guia ou janela)")

  Sua função Azure Active Directory (AD) é usada para registrar nosso aplicativo corporativo no seu locatário Azure AD e criar a Service Principal.
- Você é proprietário (ou superior) da assinatura que está credenciando. Isso é necessário para o fluxo de concessão de autorização do OAuth 2.0. Consulte [https://docs.microsoft.com/en-us/azure/active-directory/develop/app-objects-and-service-principals](https://docs.microsoft.com/en-us/azure/active-directory/develop/app-objects-and-service-principals "(Abre em uma nova guia ou janela)"). Você precisa ser pelo menos um proprietário da assinatura para que as permissões possam ser anexadas à entidade de serviço por meio do IAM.

Observação: certifique-se de ter a permissão “ billing:EnrollmentReader ” na sua conta de cobrança.

Ativar a função personalizada somente leitura em uma assinatura

As etapas a seguir pressupõem que você já tenha adicionado um EA Azure à página Vendor Credentials (Credenciais do fornecedor) do site Cloudability. Além disso, você tem uma ou mais assinaturas listadas nessa página para as quais gostaria de nos fornecer acesso.

Saiba mais sobre como [configurar o gerenciamento de custos para novos clientes do Cloudability Azure Enrollment Agreement (EA)](azure-cm-ea.html)

1. Em Cloudability, edite a assinatura. Selecione o ícone “Editar” da assinatura para a qual você deseja conceder acesso a Cloudability. ![adicionar captura de tela da credencial do azure](../../../../03-media/cloudability-premium/images/vc_ss1.jpg)
2. Selecione o botão “Gerar link” para gerar um URL para cada assinatura selecionada, que você utilizará posteriormente para concluir o fluxo de concessão de autorização OAuth 2.0 para cada uma dessas assinaturas.
   1. Selecione Assinaturas.

      ![selecionar captura de tela da credencial](../../../../03-media/cloudability-premium/images/vc_ss2.jpg)
   2. Escolha “Ajuste avançado de recursos” como “Somente leitura” em vez de “Automatizar ações ”.
   3. Selecione a(s) assinatura(s) para a(s) qual(is) deseja gerar o(s) link(s).

      ![editar captura de tela da credencial](../../../../03-media/cloudability-premium/images/azure-premium-1.jpg)
   4. selecione Ok para concluir suas seleções.
   5. Selecione Generate Links (Gerar links ). Um link é gerado para cada Subscription que você selecionou.
3. Selecione cada link para concluir o registro de nosso aplicativo e criar uma entidade de serviço.
4. Conclua o fluxo “ OAuth ” 2.0, acionado a partir do link.

   ![captura de tela do principal de serviço](../../../../03-media/cloudability-premium/images/vc_ss4.jpg)
5. Aceite o CloudabilityUtilizationDataCollector para concluir o processo de consentimento.

   ![captura de tela do cloudabilityutilizationdatacollector](../../../../03-media/cloudability-premium/images/azure_rightsizing7.jpg)
6. Verifique se o consentimento foi bem-sucedido no portal Azure :
   - Active Directory. Você pode verificar se o aplicativo foi aprovado com sucesso na seção Aplicativos corporativos em Azure Active Directory.

     ![captura de tela do diretório ativo](../../../../03-media/cloudability-premium/images/azure_rightsizing8.jpg)
7. Assinatura do IAM. Você pode verificar se a entidade de serviço tem atribuída a função personalizada “ ‘CloudabilitySubscriptionDataReader’ ” na assinatura. ![captura de tela do subscriptiondatareader](../../../../03-media/cloudability-premium/images/azure_rightsizing9.jpg)

Confirme que você credenciou sua assinatura com sucesso.

Retorne à página Vendor Credentials (Credenciais do fornecedor) em Cloudability para verificar as credenciais.

**Verificar credenciais** **por meio de ações em massa**

Para verificar várias contas rapidamente, clique no botão Ações em massa. Esta tela exibe todas as contas, exceto aquelas com o status Credenciais necessárias (X).

1. Selecione as contas que precisam ser verificadas.
2. Clique em **Revisar Seleção**
3. Clique em **Verificar.**

Isso acionaria o processo de verificação em massa e o botão de ações em massa ficaria desativado até que o processo fosse concluído.

Depois de concluídas, as contas passarão para o status de Credencial Verificada ou Credencial Inválida (devido a erros).

Observação: caso o número de contas seja muito grande, isso pode demorar alguns minutos.

Você poderá ver uma caixa de seleção amarela ou verde, na coluna Recursos avançados, para a Assinatura.

- Uma caixa de seleção verde para uma assinatura indica que o site Cloudability possui,
  - uma função personalizada somente leitura na Assinatura (por meio de nossa entidade de serviço)
- Uma caixa de seleção amarela indica que o site Cloudability tem uma credencial incompleta, por exemplo, o processo de credencial pode ter sido iniciado (ou seja, temos um registro em nosso banco de dados), mas não há permissões associadas a essa credencial.
- Uma cor de status vermelha para a credencial indica que há um erro com a credencial.

Observação: Agora podemos habilitar todos os recursos avançados por meio de nossa entidade de serviço (isso requer que a entidade de serviço tenha a função “ CloudabilitySubscriptionDataReader ” nas assinaturas). A caixa de permissões será exibida como uma caixa de seleção amarela, mas isso não é problema.

1. Verifique novamente a credencial clicando na seta circular. ![reverificar captura de tela da credencial](../../../../03-media/cloudability-premium/images/azure_rightsizing11.jpg)

   Uma marca de seleção é exibida brevemente após a verificação bem-sucedida.

   ![captura de tela da credencial bem-sucedida](../../../../03-media/cloudability-premium/images/azure_rightsizing12.jpg)

   Talvez seja necessário atualizar o navegador para obter novas alterações.
2. Selecione ![ícone de detalhes da imagem](../../../../03-media/cloudability-premium/images/details.jpg) para visualizar as permissões atualizadas.

   ![captura de tela do dimensionamento de direitos do azure](../../../../03-media/cloudability-premium/images/azure-rightsizing-credentials.jpg)s
3. Verifique se você tem a função CloudabilitySubscriptionDataReader na assinatura. Essa função na assinatura é identificada por essas 11 permissões, representadas por marcas de seleção verdes. ![captura de tela do leitor de dados de subscrição](../../../../03-media/cloudability-premium/images/azure_rightsizing16.jpg)

Observação: algumas permissões estão em verde e outras em vermelho. Desde que tenhamos as 11 permissões mostradas em verde acima, os recursos avançados estarão desbloqueados para essa assinatura.

É necessária uma permissão adicional para as contas do Azure EA.

A permissão de leitor de inscrição será adicionada a ApptioCloudability para acessar os dados do SQL RI Planner em Azure (incluindo Azure Compute, SQL, Cosmos DB e os planos de economia)

Clique aqui para [configurar a coleta de métricas de memória do site Azure](azure-advanced-metrics.html)

Atualização de clientes existentes do Cloudability para o Cloudability Premium

Após a atualização para Cloudability Premium, o status dos relatórios de faturamento e dos relatórios avançados de cada conta Azure na página de listagem muda automaticamente para o status de erro.. Portanto, um administrador do Cloudability precisa editar cada conta seguindo as etapas abaixo, o que definirá o status correto da conta no Cloudability para a ingestão de dados do Azure, além de permitir que o Cloudability compartilhe essas contas com o Turbonomic.

1. Em Cloudability, navegue até Configurações > Credenciais do fornecedor > Azure.
2. Passe o cursor sobre o ícone do pagador ou do projeto para o qual você deseja atualizar as credenciais.
3. Selecione o ![ícone de edição](../../../../03-media/cloudability-premium/images/regenerate_11_35_55_am_png.jpg) ícone para abrir a opção “Editar uma credencial”.
4. Escolha entre “Redimensionamento avançado como somente leitura” e “Automatizar ações”:
5. Gerar script de configuração.
6. Atualize as permissões executando o script.
7. Reverificar a conta.

Existem permissões adicionais do Turbonomic que são atribuídas aos níveis básico (Dados de faturamento), avançado (Dados de utilização) e Otimizar recursos (executar ações), as quais estão documentadas nos documentos da Central de Ajuda. Assim que sua conta for verificada, você poderá visualizar a lista de permissões selecionando a opção Detalhes em cada conta do Azure listada na seção Cloudability. ![captura de tela da credencial do azure turbo](../../../../03-media/cloudability-premium/images/azure-cldy-turbo-integration.jpg)

Caso os clientes existentes não adicionem as novas permissões, então

- Não haveria nenhuma alteração na interface do usuário das credenciais do fornecedor.
- As ações automatizadas serão exibidas como Desativadas nas assinaturas.
- Na guia "Detalhes", todas as permissões do " Turbonomic " aparecem com uma marca "x" VERMELHA.

Quando as novas permissões forem ativadas em assinaturas com a seleção Readonly

- As ações automatizadas ainda serão exibidas como Desativadas.
- Na guia "Detalhes", as permissões d Turbonomic e para "Custos", "Faturamento" e "Execução de faturamento" aparecerão com uma marca de seleção verde.

Assim que as novas permissões forem ativadas nas ações do Automate e a(s) conta(s) for(em) verificada(s)

- As ações automatizadas serão marcadas como Ativadas.
- Na guia "Detalhes", todas as permissões do " Turbonomic " aparecem com uma marca de seleção verde.

Observação: A opção “Ativar/Desativar ações automatizadas” é exibida na interface de usuário de credenciais do fornecedor com base na seleção feita no botão de alternância e no download do modelo.

**Tópico principal:** [Conectar Microsoft Azure](../admin/azure-cm-setup-premium.html)
