---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Conecte-se New Relic"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
source_path: "admin/newrelic-integration-premium.html"
images:
  - "images/cloudability-newrelic-account-insights-keys.jpg"
  - "images/cloudability-newrelic-credentails-list.jpg"
  - "images/cloudability-newrelic-datasource-filter.jpg"
  - "images/cloudability-newrelic-insights-key-details.jpg"
  - "images/cloudability-newrelic-rightsizing-list.jpg"
  - "images/vc_ss9.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conecte-se New Relic

New Relic é uma plataforma popular de gerenciamento de desempenho de aplicativos (APM). Essa integração permite que os clientes do Apptio Cloudability utilizem o New Relic como seu provedor preferencial de dados de utilização, resultando em recomendações aprimoradas de dimensionamento para máquinas virtuais Amazon EC2, GCP GCE e Azure Compute. O suporte a [várias contas](https://docs.newrelic.com/docs/accounts/install-new-relic/account-setup/manage-apps-or-users-sub-accounts "(Abre em uma nova guia ou janela)") também está incluído nessa integração.

Em comparação com os provedores de dados de utilização nativos, o New Relic fornece métricas de desempenho da plataforma mais precisas (CPU, rede, disco) e acesso às métricas de memória do sistema operacional convidado. Com essa fonte de dados de maior precisão, o mecanismo de redimensionamento apresenta recomendações mais fundamentadas, proporcionando até 15% de economia adicional, além das oportunidades de economia existentes, reduzindo ainda mais seus gastos com a nuvem.

Antes de começar

As etapas a seguir são necessárias para habilitar a integração do New Relic com o Cloudability com sucesso:

- **Máquinas virtuais**

Cada recurso da máquina virtual precisa ter o agente de infraestrutura New Relic instalado. As instruções variam de acordo com o sistema operacional; atualmente, são suportados Linux e Windows.

[Linux](https://docs.newrelic.com/docs/infrastructure/install-infrastructure-agent/linux-installation/install-infrastructure-agent-linux-using-package-manager "(Abre em uma nova guia ou janela)")

[Windows](https://docs.newrelic.com/docs/infrastructure/install-infrastructure-agent/windows-installation/install-infrastructure-agent-windows-server-using-msi-installer "(Abre em uma nova guia ou janela)")

- New Relic Contas

Para cada conta do New Relic, você deve fornecer um ID da conta e uma chave de consulta do Insights. Cloudability usa essas credenciais somente leitura para recuperar as métricas de desempenho dos recursos da sua máquina virtual associada por meio da [API Insights](https://docs.newrelic.com/docs/insights/insights-api/get-data/query-insights-event-data-api "(Abre em uma nova guia ou janela)").

Veja abaixo

[Obtenção de credenciais de conta](#obtainin "(Abre em uma nova guia ou janela)")

[Inserindo credenciais d New Relic](#entering "(Abre em uma nova guia ou janela)")

Etapas para a integração

- Habilitando a integração d Azure

Além do agente New Relic, também são necessárias integrações Azure para máquinas virtuais Azure Compute. Ele fornece os dados necessários em nível de recurso, como assinatura e ID do locatário, para obter IDs de recursos inequívocos.

[Habilitar integração com o Azure](https://docs.newrelic.com/docs/integrations/microsoft-azure-integrations/getting-started/activate-azure-integrations "(Abre em uma nova guia ou janela)")

- **Obtenção das credenciais da conta**

Para gerenciar ou obter suas credenciais da conta New Relic :

1. Acesse [insights.newrelic.com](https://docs.newrelic.com/docs/integrations/microsoft-azure-integrations/getting-started/activate-azure-integrations "(Abre em uma nova guia ou janela)") e alterne para a conta desejada
2. No menu esquerdo, clique em **Manage data (Gerenciar dados** )
3. No menu superior, clique em **API Keys (Chaves de API** )
4. Para criar uma nova chave, clique em **Chaves de consulta [+]**
5. Para visualizar ou editar uma chave existente, clique no botão **Editar** apropriado. ![captura de tela das chaves api](../../../../03-media/cloudability-premium/images/cloudability-newrelic-account-insights-keys.jpg)

A tela abaixo permite que o cliente crie ou edite as Notas associadas a uma chave do Insights Query.

Nessa tela, o cliente pode obter o seguinte:

- ID da conta (um número de sete dígitos ou mais)
- Chave de consulta do Insights (a chave começa com NRIQ-)

  Observação: Sugerimos que você identifique essa chave de consulta como `cloudability-integration` para fins de rastreamento e auditoria.

  ![captura de tela da chave de consulta](../../../../03-media/cloudability-premium/images/cloudability-newrelic-insights-key-details.jpg)

Inserindo credenciais d New Relic

Para integrar as novas credenciais de relíquias em Cloudability :

1. Em Cloudability, navegue até Configurações > Credenciais do fornecedor > Adicionar fonte de dados > New Relic. O painel Adicionar conta do New Relic é exibido.

   Ou

   Em Cloudability, navegue até Configurações > Credenciais do fornecedor > New Relic. Selecione Add a Credential (Adicionar uma credencial ). O painel Adicionar uma credencial é aberto.
2. Insira as credenciais do New Relic.
3. Selecione “Salvar ”.![captura de tela da lista de novas relíquias](../../../../03-media/cloudability-premium/images/vc_ss9.jpg)

Como confirmar o sucesso

Depois que as credenciais são validadas, o cliente pode alterar, excluir ou atualizar a credencial.

- Para modificar uma credencial, selecione Edit
- Para excluir uma credencial, selecione Excluir
- Para validar uma credencial, selecione Atualizar.![reresh newrelic captura de tela](../../../../03-media/cloudability-premium/images/cloudability-newrelic-credentails-list.jpg)

Utilizando o redimensionamento

Após a conclusão da configuração, o cliente pode visualizar as recomendações de ajuste de tamanho na coluna Fonte de dados. ![captura de tela do rightsizing do newrelic](../../../../03-media/cloudability-premium/images/cloudability-newrelic-rightsizing-list.jpg)

Filtrar ou classificar por fonte de dados

O cliente pode filtrar ou classificar a lista de recomendações pelo provedor da fonte de dados de utilização.

- Para classificar, clique no título da coluna **Fonte de dados** e a lista será classificada por esse valor.
- Para filtrar, clique no valor Fonte de dados para limitar as recomendações a esse valor ou clique no menu Filtros e selecione **Medida = Fonte de dados**, **Operador = igual** a e **Valor = New Relic**.
- Para limpar o filtro, clique no menu **Filtro** e, em seguida, exclua a condição clicando no ícone “x”.![captura de tela do filtro newrelic](../../../../03-media/cloudability-premium/images/cloudability-newrelic-datasource-filter.jpg)

GCP Integração

Para obter mais informações sobre como conectar os serviços d Google Cloud Platform ao New Relic, consulte [https://docs.newrelic.com/docs/infrastructure/google-cloud-platform-integrations/get-started/connect-google-cloud-platform-services-new-relic/](https://docs.newrelic.com/docs/infrastructure/google-cloud-platform-integrations/get-started/connect-google-cloud-platform-services-new-relic/ "(Abre em uma nova guia ou janela)")

Atualização para clientes existentes do Cloudability para o Cloudability Premium

Após a atualização para Cloudability Premium, o Status de Verificação de cada conta New Relic na página de listagem não será alterado nesta versão. No entanto, o administrador do Cloudability precisa editar cada conta seguindo as etapas que permitem que Cloudability compartilhe essas contas com Turbonomic.

1. Clique em Editar na conta New Relic.
2. Insira um valor de campo adicional para User Key e clique em Save.

Após a validação e verificação, Cloudability compartilha a conta com Turbonomic.
