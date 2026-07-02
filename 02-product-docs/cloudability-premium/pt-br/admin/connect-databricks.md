---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Conectar os bancos de dados"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
source_path: "admin/connect-databricks.html"
images:
  - "images/Databrick-Runtime.png"
  - "images/Databricks-Add-Service-Principle-permission.png"
  - "images/Databricks-Add-Service-Principle.png"
  - "images/Databricks-Service-Principle.png"
  - "images/clip_image001_-1832790195.png"
  - "images/clip_image002_-821243953.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conectar os bancos de dados

Você pode conectar sua conta do Databricks ao Cloudability para habilitar a captação de dados de custo e uso. Esta integração destina-se a ser utilizada exclusivamente para o Databricks em AWS e o Databricks em GCP. Se você estiver usando o Azure Databricks, terá granularidade de dados suficiente em seus dados de faturamento do Azure.

Leva 24 horas para que seus dados iniciais de custo e uso apareçam no site Cloudability

**Pré-requisitos**

- Deve ser um administrador do Cloudability e ter acesso à página de credenciais de fornecedores do Cloudability.

- Permissões necessárias para configurar um Catálogo do Unity, habilitar um Espaço de Trabalho e um Esquema do Sistema e criar um **Usuário Principal de Serviço** que terá acesso ao catálogo, ao esquema e à tabela.

- Você precisa ser um administrador de conta do Databricks para gerenciar as credenciais d OAuth s para os principais de serviço.
- O administrador da conta do Databricks / o administrador do Workspace pode realizar ações no console do Workspace do Databricks.

- É necessário criar um SQL Warehouse (que deve ser sem servidor), que possa ser utilizado pelo Usuário Principal do Serviço para executar a consulta
- Deveria ser possível programar o notebook para ser executado uma vez a cada 24 horas, a fim de extrair os dados de custos e uso do Databricks
- Para agendar o notebook, o cliente precisa criar uma máquina de computação que contenha a configuração do Spark.
- Por favor, verifique se você tem um contrato com compromisso ou um contrato pré-pago para o Databricks; isso ajudaria a confirmar se o site Cloudability está exibindo o custo de faturamento corretamente

Resumo da integração

Essa integração exige que os usuários configurem um Catálogo do Unity, habilitem um Espaço de Trabalho e um Esquema do Sistema e criem um Usuário Principal de Serviço que terá acesso ao catálogo, ao esquema e à tabela. Os usuários também precisam criar um SQL Warehouse, que possa ser utilizado pelo Usuário Principal do Serviço para executá-lo, com base no notebook baixado na interface de usuário de credenciais. Este notebook deve ser executado uma vez por dia para obter os dados de custos e uso do Databricks. Cloudability não tem acesso aos seus descontos personalizados com a Databricks; por isso, adicionamos uma opção para inserir essas informações na interface de credenciamento, para que possamos incluir esse desconto nos custos exibidos.

A Databricks recomenda o uso de uma identidade de entidade de serviço para ferramentas automatizadas, tarefas e aplicativos. Solicitamos que você crie uma para essa integração, pois estamos automatizando o processo de monitoramento do uso e do faturamento.

1. Configurar o Unity Catalog. Clique em [https://docs.databricks.com/en/data-governance/unity-catalog/get-started.html](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.databricks.com%2Fen%2Fdata-governance%2Funity-catalog%2Fget-started.html "(Abre em uma nova guia ou janela)").
2. Ativar um Workspace para o Unity Catalog. Clique em [https://docs.databricks.com/en/data-governance/unity-catalog/enable-workspaces.html](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.databricks.com%2Fen%2Fdata-governance%2Funity-catalog%2Fenable-workspaces.html "(Abre em uma nova guia ou janela)").
3. Ativar **o esquema do sistema** no Unity Catalog. Clique em [https://docs.databricks.com/api/azure/workspace/systemschemas/enable](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.databricks.com%2Fapi%2Fazure%2Fworkspace%2Fsystemschemas%2Fenable "(Abre em uma nova guia ou janela)")
4. Crie um **usuário principal de serviço** no nível da conta. Clique em [https://docs.databricks.com/en/admin/users-groups/service-principals.html#add-service-principals-to-your-account-using-the-account-consol](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.databricks.com%2Fen%2Fadmin%2Fusers-groups%2Fservice-principals.html%23add-service-principals-to-your-account-using-the-account-consol "(Abre em uma nova guia ou janela)").
5. Adicionar o Entidade de Serviço ao Espaço de Trabalho habilitado para o Catálogo do Unity. Clique em [https://docs.databricks.com/en/admin/users-groups/service-principals.html#add-a-service-principal-to-a-workspace-using-the-workspace-admin-settings](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.databricks.com%2Fen%2Fadmin%2Fusers-groups%2Fservice-principals.html%23add-a-service-principal-to-a-workspace-using-the-workspace-admin-settings "(Abre em uma nova guia ou janela)").
6. Conceda ao “Service Principal” o privilégio no catálogo, no esquema e na tabela recém-criados. Clique em [https://docs.databricks.com/en/data-governance/unity-catalog/manage-privileges/index.html#manage-privileges-in-unity-catalog](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.databricks.com%2Fen%2Fdata-governance%2Funity-catalog%2Fmanage-privileges%2Findex.html%23manage-privileges-in-unity-catalog "(Abre em uma nova guia ou janela)").
7. Crie um data warehouse SQL. [Clique em https://docs.databricks.com/en/compute/sql-warehouse/create.html](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.databricks.com%2Fen%2Fcompute%2Fsql-warehouse%2Fcreate.html "(Abre em uma nova guia ou janela)").

   Observação: o SQL Warehouse deve ser sem servidor
8. Conceda ao Service Principal permissão para usar o SQL Warehouse. Clique em [https://docs.databricks.com/en/compute/sql-warehouse/create.html#manage-a-sql-warehouse](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.databricks.com%2Fen%2Fcompute%2Fsql-warehouse%2Fcreate.html%23manage-a-sql-warehouse "(Abre em uma nova guia ou janela)").

Observação: Se você estiver adquirindo o Databricks por meio do marketplace de um provedor de nuvem e adicionando dados de custo e uso do Databricks com essa integração, os custos serão exibidos duas vezes nos relatórios d Cloudability. Por exemplo, se você adquiriu o Databricks pelo Marketplace do AWS, você teria:

- A rubrica de alto nível para “ AWS ”.

- Os itens de linha com os custos detalhados do Databricks e AWS Marketplace listado como vendedor.

Você precisará configurar filtros ou visualizações para ocultar os custos do Marketplace. Os custos do Marketplace não são incluídos na cobrança.

**Etapa 1 – Console da conta do Databricks**

**Criar uma entidade de serviço**

Para adicionar uma entidade de serviço à conta usando o console da conta, siga as etapas abaixo.

1. Como administrador da conta, faça login no painel de controle da conta.
2. Clique em Gerenciamento de usuários.
3. Na guia Entidades de serviço, clique em Adicionar entidade de serviço.
4. Digite um nome para a entidade de serviço.
5. Clique em “Adicionar”.
6. Selecione a guia “Credenciais e segredos”
7. Em **“ OAuth Secrets”** (Segredos de autenticação), clique em **“Generate Secret” (Gerar segredo** ).
8. Selecione o número máximo de dias e clique em “Concluído”.
9. Copie o **Segredo** e **o ID do Cliente** exibidos e, em seguida, clique em **Concluído.**

![](../../../../03-media/cloudability-premium/images/Databricks-Service-Principle.png)

**Etapa 2 – Console do Databricks Workspace**

Adicionar entidade de serviço ao espaço de trabalho

1. Faça login no espaço de trabalho.
2. Clique em Gerenciamento de usuários.
3. Selecione Configurações.
4. Clique em Identidade e acesso.
5. Clique em “Gerenciar” em “Entidades de serviço”.
6. Clique em “Adicionar entidade de serviço”.
7. Adicione o mesmo principal de serviço criado acima.

![](../../../../03-media/cloudability-premium/images/Databricks-Add-Service-Principle.png)

Adicionar permissão ao principal de serviço no armazém

1. Clique em SQL Warehouse.
2. Para que o depósito seja utilizado na consulta, clique no depósito.
3. Clique em Permissões.
4. Adicione uma Entidade de Serviço com a permissão “Pode usar ”.

![](../../../../03-media/cloudability-premium/images/Databricks-Add-Service-Principle-permission.png)

**Etapa 3 – Cloudability**

1. No site Cloudability, acesse **Configurações** > **Credenciais do fornecedor** > **Adicionar fonte de dados e selecione Databricks**
   1. Baixe o caderno

**Etapa 4 – Console do Databricks Workspace**

O cliente deve agendar a execução do notebook que baixou da interface do usuário do Cloudability para que seja executado uma vez a cada 24 horas em seu **Workspace, onde o Service Principal foi adicionado.**

Observação: Para executar este notebook, o cliente deve criar sua máquina de computação com o ambiente de execução do Databricks indicado abaixo, que deve incluir o Spark.

![](../../../../03-media/cloudability-premium/images/Databrick-Runtime.png)

Se o catálogo billing\_data existir, siga as etapas abaixo; caso contrário, execute o notebook baixado em Cloudability e, em seguida, siga as etapas abaixo.

Adicionar permissão ao principal de serviço à tabela

1. Clique no catálogo.
2. Clique no nome do catálogo para o qual é necessário conceder permissões.
3. Clique em Permissões.
4. Clique em Conceder.
5. Selecione os diretores.
6. Selecione USE CATALOG, USE SCHEMA e SELECT em Privilégios.
7. Clique em “Confirmar”.

**Etapa 5: Console do Cloudability**

1. Insira os detalhes na interface do usuário do Cloudability
   1. ID da conta do Databricks
   2. ID do cliente da Databricks
   3. Segredo do Databricks

      Observação: Copie o ID do cliente e o segredo da entidade de serviço
   4. Espaço de trabalho URL sem https – Este é o espaço de trabalho no qual você aplicou a entidade de serviço
   5. Insira o ID do depósito que você criou na etapa 2
   6. Selecione o modelo de assinatura
      1. Marketplace – Selecione o marketplace caso tenha adquirido o Databricks através do AWS ou do GCP marketplace
      2. Direto – Selecione esta opção se você tiver comprado diretamente da Databricks
   7. CSP dependente
      1. Selecione AWS ou GCP, dependendo de onde a infraestrutura estiver hospedada
   8. Selecione um modelo de pagamento
      1. Contrato confirmado
         1. Aqui, precisamos da data de início, da data de término e dos detalhes sobre o desconto em % dos compromissos
         2. Caso você tenha vários contratos de compromisso, é possível adicioná-los usando o botão +
      2. Pague conforme o uso
         1. Compartilhe a data de início do plano pré-pago
   9. Clique **em “Salvar”**
   10. Clique **em “Verificar** ”.

Um visto verde (![](../../../../03-media/cloudability-premium/images/clip_image001_-1832790195.png)) indica sucesso, enquanto um ponto de exclamação vermelho (![](../../../../03-media/cloudability-premium/images/clip_image002_-821243953.png)) indica erros

Caso a verificação não seja bem-sucedida, tente novamente após 15 minutos.

Após a conclusão desse processo, em até 24 horas, você começará a ver seus dados de faturamento e tags do Databricks sendo preenchidos no site Cloudability.

**Perguntas Frequentes**

**O serviço “ Cloudability ” oferece suporte à lista de endereços IP autorizados para controlar o tráfego direcionado ao Databricks?**

Sim, a lista de endereços IP autorizados é compatível. Entre em contato com o suporte do IBM para obter mais detalhes.

**O Cloudability oferece suporte** **a links privados ou ao compartilhamento de deltas para o Databricks?**

Links privados e o Delta Sharing ainda não são compatíveis com o Databricks.

**O que fazer caso o notebook programado não esteja em execução?**

Certifique-se de configurar uma máquina de computação com o Spark habilitado

**É possível modificar o Notebook?**

Recomenda-se não editar o notebook baixado da interface do usuário do Cloudability, pois várias operações internas utilizam essas configurações.

**Como obter as tags do Databricks?**

Cloudability suporta tags personalizadas no nível do recurso

- Esses dados fazem parte dos dados de faturamento do Databricks e não são necessárias permissões adicionais no Cloudability para habilitá-los
- Nós transmitimos metadados de uso, metadados de identidade e recursos do produto, já que ` Tags.Workspaceid ` estará visível como uma chave de tag sob `cldy:databricks:workspaceid`

**Por que é necessário inserir os descontos na interface do usuário?**

Cloudability não tem acesso aos seus descontos personalizados com a Databricks; por isso, adicionamos uma opção para inserir essas informações na interface de credenciamento, para que possamos levar esse desconto em consideração nos custos exibidos

**Qual é a importância das datas no processo de credenciamento do Databricks?**

As datas mencionadas na interface de usuário de credenciais são utilizadas para buscar os dados do Databricks.

As APIs do Databricks nos permitem obter os dados dos últimos 13 meses; os clientes podem escolher qualquer data dentro desse período para obter dados detalhados do Databricks.
