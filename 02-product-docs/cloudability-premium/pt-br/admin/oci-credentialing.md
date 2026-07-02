---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Federando um usuário para credenciamento da OCI"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
  - "Conecte-se Oracle Cloud"
source_path: "admin/oci-credentialing.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Federando um usuário para credenciamento da OCI

Resumo

Esta página descreve o processo passo a passo para gerenciar um usuário federado em um provedor de identidade para a OCI, com foco específico na criação e configuração de usuários e grupos no Serviço de Nuvem de Identidade da Oracle (“IDCS”).

Esse processo é opcional; ele é realizado por meio da implantação de um Terraform e, em seguida, da substituição do usuário por um usuário federado.

Pré-requisitos

Para criar usuários e grupos na federação do Serviço Identity Cloud da Oracle, você precisará da função de Administrador do Domínio de Identidade ou ser membro de um grupo ao qual essa função tenha sido atribuída.

Etapas

Preparação

Certifique-se de que “ CloudabilityDataCollector\_Group ”, “ CloudabilityDataCollector\_User ” e “ CloudabilityCostDataReaderPolicy ” já tenham sido criados pelo Terraform.

Exclusão de usuário local

Exclua o arquivo “ CloudabilityDataCollector\_User ”, caso ele exista.

Criação de um usuário federado

1. Acesse Identidade -> Federação -> Detalhes do provedor de identidade -> Usuários.
2. Crie um novo usuário do IDCS usando as seguintes credenciais.

   - Nome de usuário : CloudabilityDataCollector\_Fed\_User
   - E-mail : cldyfeduser@cloudability.com ou qualquer endereço de e-mail válido
   - Nome : CloudabilityDataCollector
   - Sobrenome : Fed\_User
3. Clique em Criar e, em seguida, em Fechar.

Criação de um grupo federado

1. Acesse Identidade -> Federação -> Detalhes do provedor de identidade -> Grupo.
2. Crie um novo grupo no IDCS chamado “ CloudabilityDataCollector\_Fed\_Group ”.
3. Adicione o usuário federado “ CloudabilityDataCollector\_Fed\_User ” ao grupo.

Mapeamento de um grupo local para um grupo federado

Como não é possível conceder acesso a grupos federados por meio de políticas, é necessário mapear um grupo local para o grupo federado.

1. Acesse Identidade -> Federação -> Detalhes do provedor de identidade -> Mapeamentos de grupos.
2. Crie um novo grupo no IDCS chamado “ CloudabilityDataCollector\_Fed\_Group ”.
3. Crie um mapeamento entre o grupo OCI “ CloudabilityDataCollector\_Group ” e o grupo federado “ CloudabilityDataCollector\_Fed\_Group ”.

Sincronização do usuário sincronizado pelo OCI

Acesse Identidade -> Federação -> Detalhes do provedor de identidade -> Usuários -> " CloudabilityDataCollector\_Fed\_User ".

Clique no link “OCI Synched User” do usuário federado “ CloudabilityDataCollector\_Fed\_User ”.

Geração de chaves de API:

1. Acesse Chaves deAPI.
2. Adicione uma nova chave de API.
3. Gere um par de chaves de API.
4. Baixe a chave privada e a chave pública.
5. Adicione as chaves.

Envio de informações para Cloudability

Forneça os detalhes necessários, incluindo chaves de API e outras informações relevantes, para Cloudability por meio da interface do usuário.

**Tópico principal:** [Conectar o Oracle a nuvem](../admin/connect-oracle-cloud.html)
