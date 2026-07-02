---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Conecte-se Oracle Cloud"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
source_path: "admin/connect-oracle-cloud.html"
images:
  - "images/OCI-api-key.png"
  - "images/OCI-generate-api-key.png"
  - "images/OCI-user-groups-.png"
  - "images/generating__api_oci_3.jpg"
  - "images/oracle-cloud-adding-credentials-child-tenancies.jpg"
  - "images/terraform_script_1.jpg"
  - "images/terraform_script_2.jpg"
  - "images/terraform_script_3.jpg"
  - "images/terraform_script_4.jpg"
  - "images/terraform_script_5.jpg"
  - "images/terraform_script_7.jpg"
  - "images/validating_oci_1.jpg"
  - "images/validating_oci_3.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conecte-se Oracle Cloud

Você pode conectar sua instância do Oracle Cloud Infrastructure (OCI) ao Cloudability para habilitar a coleta de dados de custo e uso.

Observação: pode levar até 24 horas para que seus dados iniciais de custo e uso apareçam no site Cloudability.

Para garantir total compatibilidade e suporte, siga as etapas de conexão conforme descrito. Não são suportadas configurações personalizadas. Se tiver dúvidas, entre em contato com o **Suporte IBM**.

Resumo da integração

1. Como obter seus dados de custo e uso no Cloudability

   Cloudability obtém seus dados de custo e uso do OCI a partir dos Relatórios de Custos, que pertencem ao OCI e estão localizados na locação raiz do seu console do OCI. Para fornecer ao Cloudability acesso aos seus dados de custo e uso do OCI, você precisa validar as credenciais da sua tenancy raiz, pois os dados das suas tenancies secundárias são agregados à tenancy raiz.

   O processo de credenciamento é realizado por meio de um script do Terraform, e o OCID da sua tenancy raiz é necessário para gerar e executar o script. O script inclui comandos para criar um grupo e um usuário, adicionar o usuário ao grupo, criar políticas e associá-las ao grupo, de modo que Cloudability possa acessar os relatórios de custos pelo console do OCI. Observe que essas políticas concedem à Cloudability permissão de somente leitura para os dados do OCI.

   Depois que o script for executado no console do OCI, você precisará gerar chaves de assinatura. A última etapa será colar o nome da região de origem, o OCID do usuário, o OCID do grupo, a impressão digital e a chave privada na interface do usuário d Cloudability.
2. Como obter seus dados de utilização no Cloudability

   Depois de concluir o processo de credenciamento da sua tenancy raiz, você receberá dados de utilização do OCI apenas para a sua tenancy pai. Após a verificação das credenciais, suas instâncias secundárias serão exibidas na interface de usuário de credenciamento, e você precisará passar pelo processo de credenciamento dessas instâncias secundárias também para obter seus dados de utilização. A obtenção de dados de utilização permitirá que a Cloudability forneça recomendações para o dimensionamento adequado. Você pode encontrar mais detalhes na parte inferior desta página, na seção “  Adicionando credenciais para suas sublocações  ”.

**Pré-requisitos**

Antes de começar, verifique o seguinte:

- Você é um administrador do Cloudability.
- Você possui permissões de administrador no console do OCI.
  - Isso é necessário para executar o script do Terraform no console do OCI.

Etapas de integração

Obtenha seu ID de locatário da OCI

1. Faça login no console da Infraestrutura em Nuvem do Oracle (OCI).
2. Selecione Governança e Administração no menu de navegação no canto superior esquerdo do painel.
3. Selecione “Contratos de locação” no cabeçalho “Gerenciamento da organização”. Seus contratos de locação estão listados aqui.
4. Copie o ID do seu tenancy pai, selecionando o ícone de cópia ao lado do ID do seu tenancy cujo nome contenha “Parent tenancy”.
5. No site Cloudability, acesse Configurações > Credenciais do fornecedor > OCI.
6. Selecione Adicionar uma credencial. O painel “Adicionar uma credencial” é exibido no lado esquerdo.
7. Cole o ID do contrato de locação principal.
8. Selecione Salvar.

Gerar o script do Terraform

Depois que o ID do contrato de locação estiver salvo, selecione  Gerar script. Ele faz o download do script do Terraform. Por favor, crie uma pasta específica, por exemplo: Cloudability, e salve o script nessa pasta em seu computador. Isso é feito porque, ao enviar o script, não é possível enviá-lo individualmente — é preciso enviar a pasta que contém o script.

A seguir, está o conteúdo do Terraform utilizado pelo Cloudability para criar os recursos necessários:

```
variable "cloudablity_user_email" {
				description = "This is a variable to assign the email to user. If not provided, default email will be set."
				type        = string
				default     = "cldyuser@cloudability.com"
				}
				 
				resource "oci_identity_user" "cloudablity_user" {
				compartment_id = "ocid1.tenancy.oc1..aaaaaaaa4pjpasfply4eky7dl6msfdt3doqpfpmbuw2aesigtvedd4oxhufa"
				description = "This is a Cloudability user and they will be accessing cost data from your tenant."
				name = "CloudabilityDataCollector_User"
				freeform_tags = {
				"User_Created_For"= "Cloudability"
				}
				}
				 
				resource "oci_identity_group" "cloudability_group" {
				compartment_id = "ocid1.tenancy.oc1..aaaaaaaa4pjpasfply4eky7dl6msfdt3doqpfpmbuw2aesigtvedd4oxhufa"
				description = "This is a Cloudability group and it will be accessing cost data from your tenant."
				name = "CloudabilityDataCollector_Group"
				freeform_tags = {
				"Group_Created_For"= "Cloudability"
				}
				}
				 
				resource "oci_identity_user_group_membership" "user_group_membership" {
				group_id = oci_identity_group.cloudability_group.id
				user_id = oci_identity_user.cloudablity_user.id
				}
				 
				resource "oci_identity_policy" "cloudability_policy" {
				compartment_id = "ocid1.tenancy.oc1..aaaaaaaa4pjpasfply4eky7dl6msfdt3doqpfpmbuw2aesigtvedd4oxhufa"
				description = "This policy will retrieve permissions to access the cost report and list policy."
				name = "CloudabilityCostDataReaderPolicy"
				freeform_tags = {
				"Policy_Created_For"= "Cloudability"
				}
				statements = [
				"define tenancy reporting as ocid1.tenancy.oc1..aaaaaaaaned4fkpkisbwjlr56u7cj63lf3wffbilvqknstgtvzub7vhqkggq",
				"endorse group ${oci_identity_group.cloudability_group.name} to read objects in tenancy reporting",
				"allow group ${oci_identity_group.cloudability_group.name} to read organizations-tenancy in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read organizations-family in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read policies in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read metrics in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read rate-cards in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read instance-images in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to inspect instances in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read instance-family in tenancy"
				]
		}
```

Observação: A variável “cloudablity\_user\_email” foi adicionada ao script do Terraform, pois se trata de uma informação obrigatória para os usuários que utilizam o Identity Domain em seu console do OCI. O endereço de e-mail “ cldyuser@cloudability.com ” é um exemplo provisório e pode ser alterado diretamente no script do Terraform ou atualizado posteriormente, quando for carregado no console do OCI.

Carregue o script do Terraform

1. No console do OCI, selecione o menu de navegação no canto superior esquerdo da página do painel e, em seguida, selecione Serviços para desenvolvedores.

   ![Captura de tela do OCI Terraform](../../../../03-media/cloudability-premium/images/terraform_script_1.jpg)
2. Selecione “Stacks” no cabeçalho “ Resource Manager ”.

   Observação: Certifique-se de selecionar o compartimento raiz no Escopo dalista na visualização do lado esquerdo.

   ![Captura de tela do gerenciador de recursos do OCI](../../../../03-media/cloudability-premium/images/terraform_script_2.jpg)
3. Selecione “Criar pilha” para criar uma nova pilha.

   ![Captura de tela da pilha criada pelo OCI](../../../../03-media/cloudability-premium/images/terraform_script_3.jpg)
4. Na página Criar pilha, selecione Minha configuração para fazer o upload dos arquivos de configuração do Terraform.

   ![Captura de tela da minha configuração do OCI](../../../../03-media/cloudability-premium/images/terraform_script_4.jpg)
5. Na seção “Configuração da pilha”, selecione “Pasta” e, em seguida, navegue até a pasta onde o arquivo de configuração está armazenado.
6. Selecione “Enviar” na janela pop-up.

   Observação: Certifique-se de que o compartimento selecionado tenha a opção “(raiz)” marcada no campo “Criar no compartimento ”.

   ![Carregar captura de tela do Terraform da OCI](../../../../03-media/cloudability-premium/images/terraform_script_5.jpg)
7. Na caixa de texto Nome, digite “ Cloudability ” como valor. Selecione Próximo.
8. Agora você tem a opção de atualizar o endereço de e-mail “ cldyuser@cloudability.com ” que consta no script do Terraform. Essa variável só é necessária se você tiver um Domínio de Identidade no seu console OCI e pode ser atualizada nesta etapa, se necessário.
9. Selecione a versão do Terraform como “ 1.5 ”
10. Marque a caixa de seleção “Executar e aplicar ”.

    ![](../images/OCI_Terrform_version%20update.png)
11. Selecione Criar para criar a pilha.

O Resource Manager validará o arquivo Terraform fornecido e criará uma nova pilha.

Monitore o status do trabalho (estado do ciclo de vida) recuperando o trabalho. “Concluído” indica que a tarefa foi concluída.

Esta tarefa criará um usuário, um grupo e uma política. A operação pode demorar algum tempo, dependendo da complexidade do trabalho. Enquanto o trabalho estiver em execução, ou após sua conclusão, você receberá o conteúdo dos registros do trabalho.

Depois que a pilha for criada, você poderá visualizá-la na seção Pilhas.

![Captura de tela da pilha do Terraform da OCI](../../../../03-media/cloudability-premium/images/terraform_script_7.jpg)

Validar os recursos criados

1. Selecione Identidade e Segurança no menu de navegação no canto superior esquerdo do painel.

   ![Captura de tela do Terraform da OCI sobre identidade e segurança](../../../../03-media/cloudability-premium/images/validating_oci_1.jpg)
2. Selecione Usuários no cabeçalho Identidade, acessando Identidade → Domínio → Selecionar domínio → guia Gerenciamento de usuários.

   É possível observar um usuário chamado "CloudabilityDataCollector\_User", que foi criado pela tarefa do Terraform.

   Observação: Se você não desejar que o Cloudability crie um usuário local e, em vez disso, preferir ter um usuário “federado”, consulte [Federação de um usuário para credenciamento no OCI](oci-credentialing.html).
3. Selecione Grupos no cabeçalho Identidade. Se você estiver utilizando o Identity Domain, será necessário selecionar Domínios no cabeçalho Identidade, em seguida, selecionar Domínio padrão, Gerenciamento de usuários e, por fim, selecionar Grupos. Você pode observar um grupo chamado “ "CloudabilityDataCollector\_Group" ”, que foi criado pela tarefa do Terraform.
4. Selecione “ CloudabilityDataCollector\_Group ” para verificar se “ CloudabilityDataCollector\_User ” foi adicionado a este grupo como “Membro do grupo”.
5. Na seção Informações do grupo, copie o OCID do grupo e salve-o. Essas informações precisarão ser coladas posteriormente na interface do usuário d Cloudability.

   ![](../../../../03-media/cloudability-premium/images/OCI-user-groups-.png)
6. Selecione Políticas no cabeçalho Identidade.

   ![Captura de tela das políticas do Terraform da OCI](../../../../03-media/cloudability-premium/images/validating_oci_3.jpg)

   É possível observar a política chamada “ "CloudabilityCostDataReaderPolicy" ”, que foi criada pela tarefa do Terraform. Esta política contém todas as políticas necessárias para obter dados do ambiente do cliente. A alteração do nome desta política não é permitida.

Gerar a chave da API

1. Selecione Identidade e Segurança no menu de navegação no canto superior esquerdo do painel.
2. Selecione Usuários no cabeçalho Identidade, acessando Identidade → Domínio → Selecionar domínio → guia Gerenciamento de usuários.

   Observação: Se você estiver utilizando o módulo Identity Domain, selecione Domínios no cabeçalho Identidade e, em seguida, selecione Domínio padrão e Usuários.
3. Selecione o usuário chamado "CloudabilityDataCollector\_User".
4. Selecione Chaves de API → Adicionar chave de API

   ![](../../../../03-media/cloudability-premium/images/OCI-api-key.png)
5. Selecione Gerar par de chaves de API.

   ![](../../../../03-media/cloudability-premium/images/OCI-generate-api-key.png)
6. Selecione Baixar chave privada. Você precisará colá-lo mais tarde na interface do usuário d Cloudability.
7. Selecione Baixar chave pública.
8. Selecione Adicionar e a impressão digital será gerada.
9. Selecione o arquivo “View Configuration ”.

   ![Captura de tela da configuração da visualização do Terraform no OCI](../../../../03-media/cloudability-premium/images/generating__api_oci_3.jpg)

Etapa 2 – No site Cloudability – Adicione informações na interface do usuário do Cloudability

1. No site Cloudability, acesse Configurações > Credenciais do fornecedor > Adicionar fonte de dados > OCI. O painel “Adicionar conta OCI” é exibido.

   Ou

   No site Cloudability, acesse Configurações > Credenciais do fornecedor > OCI. Selecione Adicionar uma credencial. O painel “Adicionar credencial” é exibido.

   Cole as informações no arquivo de configuração conforme mostrado a seguir:
   - Região inicial : é exibida ao lado de “região” no arquivo de configuração
   - ID do usuário : É exibido ao lado de “usuário” no “Arquivo de configuração”.
   - ID do grupo : Essa informação foi salva na etapa anterior. Você pode encontrar esse OCID acessando Identidade e Segurança > Grupos > ' CloudabilityDataCollector\_Group '.
   - Espaço de nomes : Este é o seu espaço de nomes OCI; preencha com o espaço de nomes configurado.
   - Impressão digital : Ela é exibida diretamente no  Arquivo de configuração.
   - Senha : Pode-se deixar esse campo em branco.
   - Chave privada : essa informação foi salva na etapa anterior.

     Observação: certifique-se de colar a Chave Privada na íntegra em Cloudability, incluindo “-----BEGIN PRIVATE KEY----” e “-----END PRIVATE KEY----”.
2. Selecione Salvar.
3. Selecione “Verificar credencial ”.

   Observação: certifique-se de selecionar Salvar antes de selecionar Verificar credencial para evitar mensagens de erro.

Se as informações forem verificadas corretamente, uma marca de seleção verde aparecerá na seção “Relatórios de cobrança ”. Uma marca de seleção verde também aparecerá na seção Recursos avançados, mas apenas para a instância raiz.

Após a conclusão desse processo, em poucas horas,

- Cloudability passará a exibir seus dados de faturamento e tags OCI no site Cloudability.
- Os dados sobre preços também seriam coletados
- Cloudability também exibirá as locações subordinadas da OCI.

Como próximo passo, você precisará configurar as credenciais das locações secundárias do OCI.

Depois de visualizar seus dados OCI, você pode prosseguir com a atualização de suas tags e mapeamentos de negócios. Saiba mais sobre isso na [publicação da comunidade Apptio](https://community.apptio.com/blogs/soline-plichta/2023/09/14/cloudability-for-oci-cost-management-faq "(Abre em uma nova guia ou janela)").

Etapa 3 – Em “ Cloudability ” – Adicionando credenciais para suas subinstâncias

Assim que suas credenciais forem verificadas, seus tenancies filhos serão automaticamente detectados pelo Cloudability e exibidos na interface do usuário. Passe o mouse sobre os três pontos à direita do contrato de locação do seu filho e selecione o botão “lápis”.

![Captura de tela do OCI Terraform: adicionar credenciais para um objeto filho](../../../../03-media/cloudability-premium/images/oracle-cloud-adding-credentials-child-tenancies.jpg)

Em seguida, você pode começar a credenciar os contratos de locação dos seus filhos, seguindo o mesmo processo descrito acima para os contratos de locação dos pais.

**Verificar credenciais** **por meio de ações em massa**

Para verificar várias contas rapidamente, clique no botão “Ações em massa”. Esta tela exibe todas as contas, exceto aquelas com o status “Credenciais necessárias” (X).

1. Selecione as contas que precisam ser verificadas.
2. Clique em **“Revisar seleção”**
3. Clique em **“Verificar”.**

Isso acionaria o processo de verificação em massa, e o botão de ações em massa ficaria desativado até que o processo fosse concluído.

Após a conclusão, as contas passarão para o status “Credencial verificada” ou para o status “Credencial inválida” (devido a erros).

Observação: caso o número de contas seja muito grande, isso pode levar alguns minutos.

Levará até 48 horas para que seus dados de utilização sejam disponibilizados no Cloudability e você comece a receber recomendações de ajuste de capacidade.

Lista de permissões

Veja abaixo a lista de permissões exibidas nos detalhes das credenciais do OCI. Algumas delas se aplicam apenas à conta principal/contrato de locação, e não à conta secundária/contrato de locação ( “oci.get.costReports”, “ oci.list.tenancies ” e “oci.list.rateCards” ).

| Permissão | Descrição | Aplicável à conta principal/contrato de locação | Aplicável à conta/locação do menor |
| --- | --- | --- | --- |
| oci.get.costReports | Permissão para obter o relatório de custos | Sim | Não |
| oci.list.tenancies | Autorização para listar o contrato de locação do filho a partir do contrato do pai ou da mãe | Sim | Não |
| oci.get.metrics | Permissão para obter métricas | Sim | Sim |
| oci.list.rateCards | Autorização para publicar tabelas de preços | Sim | Não |
| oci.list.assignedSubscriptions | Permissão para listar a assinatura atribuída | Sim | Sim |
| oci.list.computeShapes | Permissão para listar formas de computação | Sim | Sim |
| oci.list.computeImages | Permissão para listar imagens de computação | Sim | Sim |
| oci.list.imageShape.Compatibility | Permissão para listar formas de imagens | Sim | Sim |
| oci.get.instanceFamily | Permissão para ler a família de instâncias | Sim | Sim |
| oci.list.policies | Política de permissão de leitura para fins de verificação | Sim | Sim |

- **[Federação de um usuário para credenciamento na OCI](../admin/oci-credentialing.html)**
