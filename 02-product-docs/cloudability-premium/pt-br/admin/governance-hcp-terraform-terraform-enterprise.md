---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "HCP Terraform/Terraform Enterprise"
breadcrumb:
  - "Cloudability Premium"
  - "Governança"
  - "Configurar Cloudability Governança"
source_path: "admin/governance-hcp-terraform-terraform-enterprise.html"
images:
  - "images/Gov5.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# HCP Terraform/Terraform Enterprise

## Visão geral

Cloudability A governança se integra ao [HCP Terraform](https://developer.hashicorp.com/terraform/cloud-docs "(Abre em uma nova guia ou janela)") e ao [Terraform Enterprise](https://developer.hashicorp.com/terraform/enterprise "(Abre em uma nova guia ou janela)") por meio de uma [**tarefa de execução**](https://developer.hashicorp.com/terraform/cloud-docs/workspaces/settings/run-tasks "(Abre em uma nova guia ou janela)"), permitindo a análise automatizada de custos e a aplicação de políticas durante os fluxos de trabalho de solicitação pull.

Uma vez configurada, a Run Task avalia os planos do Terraform e fornece feedback em tempo real - sinalizando riscos de custo, tags ausentes e recursos não compatíveis - antes da implementação.

**Pré-requisito:** Certifique-se de que você instalou o aplicativo IBM Cloudability GitHub antes de prosseguir com a configuração da Run Task.

## Gerar credenciais em Cloudability

1. Na interface do usuário Cloudability, vá para **Configuration > Integrations (Configuração > Integrações** ).
2. Gerar um **retorno de chamada URL** e uma **chave HMAC**.
   - Essas credenciais autenticam e encaminham callbacks de Run Task do HCP Terraform.
   - Cada par de chaves representa uma única credencial de HCP para sua organização.

   ![imagem](../../../../03-media/cloudability-premium/images/Gov5.png)

## Criar uma tarefa de execução no HCP Terraform

1. Na interface do usuário do HCP Terraform, navegue até **Settings → Integrations → Run Tasks**.
2. Crie uma nova tarefa de execução com os seguintes detalhes:
   - **Estágio** : Pós-planejamento
   - **Endpoint URL** : Use o retorno de chamada URL de Cloudability
   - **Chave HMAC** : Use a chave gerada em Cloudability
   - **Nível de aplicação** : Escolha Advisory (somente aviso) ou Mandatory (bloqueio em caso de falha).

     *Dica: comece com o Advisory para avaliar o impacto antes de aplicar.*
3. Anexe a tarefa de execução a um ou mais espaços de trabalho:
   - Você pode aplicá-lo globalmente a todos os espaços de trabalho ou anexá-lo individualmente.
   - Recomenda-se a reutilização de uma única tarefa de execução em vários espaços de trabalho.

   Quando a configuração estiver concluída, vá para a página [**Deployment Configuration (Configuração da implantação**](governance-deployment-configurations.html) ).

## Configuração com o Terraform Enterprise

Se a instância do Terraform Enterprise estiver hospedada atrás de um firewall, certifique-se de que ele permita a **entrada de solicitações de Cloudability** para que os resultados da Run Task possam ser publicados com êxito.

Consulte a documentação da [API Run Task do Terraform Enterprise](https://developer.hashicorp.com/terraform/enterprise/api-docs/run-tasks/run-tasks-integration#run-task-callback "(Abre em uma nova guia ou janela)") para obter detalhes técnicos sobre a configuração de retorno de chamada.

Se tiver algum problema, entre em contato com a equipe da conta Cloudability. Eles o colocarão em contato com a equipe de produtos para obter suporte.

## Como incluir informações da conta do provedor na saída do plano do Terraform

Para AWS recursos, isso pode ser feito incluindo [aws\_caller\_identity](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller_identity "(Abre em uma nova guia ou janela)") como fonte de dados nos seus arquivos Terraform.

Para arquivos Terraform que implantam recursos em uma única conta, isso pode ser feito adicionando a seguinte linha na sua configuração Terraform.

```
data "aws_caller_identity" "defaultidentity" {}
```

Para arquivos Terraform que implantam recursos em várias contas por meio de provedores definidos, isso pode ser feito adicionando as seguintes linhas para cada provedor na sua configuração Terraform. No exemplo abaixo, “engenharia” e “preparação” são dois provedores diferentes.

```
data "aws_caller_identity" "engineering" {
  provider = aws.engineering
}
data "aws_caller_identity" "staging" {
  provider = aws.staging
}
```

## Integre seus preços personalizados e adicione suas informações de uso para obter uma estimativa de custos mais precisa

- Consulte a documentação [em](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=governance-preferences-configuration "(Abre em uma nova guia ou janela)") IBMCloudability para saber como obter uma estimativa de custo mais precisa, incluindo seus preços personalizados.
- Consulte a documentação [em](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=governance-usage-configuration-based-cost-estimation "(Abre em uma nova guia ou janela)") IBMCloudability para adicionar informações de uso e obter uma estimativa de custo mais precisa

**Tópico principal:** [Configurar Cloudability Governança](../admin/governance-setup-cldy-governance.html)
