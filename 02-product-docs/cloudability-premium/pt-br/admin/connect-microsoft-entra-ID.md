---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Conectar o Microsoft Entra ID"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
source_path: "admin/connect-microsoft-entra-ID.html"
images:
  - "images/Picture16.png"
  - "images/Picture17.png"
  - "images/Picture18.png"
  - "images/Picture19.png"
  - "images/Picture20.png"
  - "images/Picture21.png"
  - "images/Picture22.png"
  - "images/Picture23.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conectar o Microsoft Entra ID

O Microsoft Entra ID (anteriormente conhecido como Azure Active Directory ) é um serviço de gerenciamento de identidade e acesso (IAM) baseado em nuvem que atua como um provedor de identidade ( IdP ). Ele autentica e verifica as identidades de usuários, dispositivos e serviços para acesso seguro a aplicativos e recursos.

Antes de começar, certifique-se de que:

- Você é um administrador do site Cloudability.
- Você tem permissões de administrador no locatário do Microsoft Entra ID.

**Como o Cloudability se conecta ao seu locatário do Microsoft Entra ID**

- Para se conectar ao seu locatário do Microsoft Entra ID, o Cloudability registra seu próprio aplicativo no locatário do Entra ID que você escolheu para credenciar com o Cloudability. Em seguida, o site Cloudability cria uma Service Principal no seu locatário usando o aplicativo registrado.
- Para autenticação, o Cloudability usa o acesso e a chave secreta de seu aplicativo, que são armazenados e gerenciados pelo Apptio.
- Para credenciar o site Cloudability com seu Microsoft Entra ID, faça o download de um script power shell do módulo Vendor Credentials do site Cloudability e execute-o no locatário do Microsoft Entra ID que você deseja credenciar.
- Aqui está um exemplo de um script de shell de energia:

  ```
  $entraAppId = "8dd8d868-a85c-4607-acd4-491df5068a79" $cldyEntraObjectId = (Get-AzADServicePrincipal -ApplicationId $entraAppId).id if (!$cldyEntraObjectId) { New-AzADServicePrincipal -ApplicationId $entraAppId $cldyEntraObjectId = (Get-AzADServicePrincipal -ApplicationId $entraAppId).id } else { echo "Service principal already present, skipping new service principal creation" }
  ```
- A execução desse script no comando do power shell registrará o aplicativo Cloudability (com o AppID, conforme mencionado na primeira linha do script) no seu locatário e criará a Service Principal usando o aplicativo. Se uma entidade de serviço já estiver presente, ele ignorará a criação de uma nova entidade de serviço e reutilizará a entidade de serviço existente.
- Por fim, você precisará adicionar as permissões *User.ReadBasic.All* e *GroupMember. Read.All* à Entidade de Serviço.

  Observação: para credenciar o site Cloudability com seu Entra ID, não é necessário realizar nenhuma outra ação no ambiente Azure além de executar o script do power shell, conforme mencionado anteriormente, e conceder as permissões necessárias.

**Etapas detalhadas**

1. Navegue até **Configurações > Credenciais do fornecedor**.
2. Clique no botão **Adicionar fonte de dados** e selecione **Microsoft Entra ID**.

   ![Grupo de usuários](../../../../03-media/cloudability-premium/images/Picture16.png)
3. Clique em **Next** no slide.

   ![grupo de usuários](../../../../03-media/cloudability-premium/images/Picture17.png)
4. Forneça o Tenant ID do locatário específico do Azure Entra ID que você deseja credenciar com Cloudability e clique em **Save (Salvar)**.

   ![grupos de usuários](../../../../03-media/cloudability-premium/images/Picture18.png)
5. Selecione **Download Script**.

   ![download do entraid ss](../../../../03-media/cloudability-premium/images/Picture19.png)
6. Execute o script baixado no locatário específico do Azure Entra ID.
7. Adicione as permissões *User.ReadBasic* *Read.All GroupMember* à Entidade de Serviço. Siga estas etapas para adicionar as permissões:
   1. Pesquise "CloudabilityGroupReaderApp" na barra de pesquisa do Portal Azure.
   2. Uma vez dentro do aplicativo, navegue até a seção Permissões em Gerenciar.
   3. Clique em **Grant admin consent for Default Directory (Conceder consentimento de administrador para o diretório padrão** ).
   4. Depois que a autorização for concedida, você poderá ver a(s) permissão(ões) listada(s) conforme mostrado aqui.

      ![grupos de usuários](../../../../03-media/cloudability-premium/images/Picture20.png)
8. Depois que o script for executado com êxito, navegue até a **guia Configurações > Credenciais do fornecedor > Microsoft Entra ID**. A credencial será exibida com uma **marca amarela** indicando que ainda precisa ser verificada. Expandir o **...** e selecione a opção **Editar**.

   ![grupos de usuários](../../../../03-media/cloudability-premium/images/Picture21.png)
9. Clique no botão **Verify Credential (Verificar credencial** ) no slide.

   ![grupos de usuários](../../../../03-media/cloudability-premium/images/Picture22.png)
10. Se for verificada, a credencial será exibida com uma **marca verde**.

    ![grupos de usuários](../../../../03-media/cloudability-premium/images/Picture23.png)
