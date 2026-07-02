---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Configuração de preferências"
breadcrumb:
  - "Cloudability Premium"
  - "Governança"
  - "Configurar Cloudability Governança"
source_path: "admin/governance-preferences-configurations.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Configuração de preferências

Visão geral

Para obter preços específicos para cada conta, o Cloudability Governance atualmente busca as informações da conta do provedor da seguinte forma:

**AWS Recursos**

**Clientes do HCP TF/Terraform Enterprise** — Informações da conta do provedor diretamente no próprio plano do Terraform, a partir da fonte de dados aws\_caller\_identity ( [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller\_identity](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller_identity "(Abre em uma nova guia ou janela)") ). Essas informações, se estiverem presentes na saída do plano do Terraform, têm a maior precedência. Se as informações da conta não estiverem disponíveis através do aws\_caller\_identity, o Cloudability Governance utiliza a conta padrão configurada nas preferências da página Cloudability Governance Configuration. Se a conta padrão não estiver configurada nas preferências, será utilizado o preço de varejo (de tabela).

**Clientes da Comunidade TF (por meio da ação GitHub )** — Informações da conta do provedor dentro do próprio plano do Terraform, provenientes da fonte de dados aws\_caller\_identity ( [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller\_identity](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller_identity "(Abre em uma nova guia ou janela)") ). Essas informações, se estiverem presentes na saída do plano do Terraform, têm a maior precedência. Se as informações da conta não estiverem disponíveis por meio de aws\_caller\_identity, a governança do Cloudability usa o mapa “provider-accounts” como entrada para a ação GitHub, se configurada. Esta é a segunda opção na ordem de preferência. Se as informações da conta não estiverem disponíveis por meio de uma ação de entrada GitHub, o Cloudability Governance usará a conta padrão configurada nas preferências da página Cloudability Governance Configuration. Se a conta padrão não estiver configurada nas preferências, será utilizado o preço de varejo (de tabela).

**Azure Recursos**

Para recursos do Azure, o Cloudability Governance busca informações de assinatura na seguinte ordem de prioridade:

**Clientes do HCP TF/Terraform Enterprise** — Informações sobre a assinatura do provedor no próprio plano do Terraform, a partir do recurso `azurerm\_subscription` ou da fonte de dados `azurerm\_subscription` ( [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/subscription](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/subscription "(Abre em uma nova guia ou janela)") ). Essas informações, se estiverem presentes na saída do plano do Terraform, têm a maior precedência. Caso as informações de assinatura não estejam disponíveis por meio do `azurerm\_subscription`, o Cloudability Governance utiliza a conta padrão configurada nas preferências da página de configuração do Cloudability Governance. Se a conta padrão não estiver configurada nas preferências, será utilizado o preço de varejo (de tabela).

**Clientes da Comunidade TF (por meio da ação GitHub )** — Informações sobre a assinatura do provedor no próprio plano do Terraform, provenientes do recurso `azurerm\_subscription` ou da fonte de dados `azurerm\_subscription` ( [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/subscription](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/subscription "(Abre em uma nova guia ou janela)") ). Essas informações, se estiverem presentes na saída do plano do Terraform, têm a maior precedência. Se as informações de assinatura não estiverem disponíveis por meio do `azurerm\_subscription`, o Cloudability Governance utiliza o mapa “provider-accounts” como entrada para a ação GitHub, caso esteja configurada. Esta é a segunda opção na ordem de preferência. Se as informações de assinatura não estiverem disponíveis por meio da entrada de ação em GitHub, o Cloudability Governance utilizará a conta padrão configurada nas preferências da página de configuração do Cloudability Governance. Se a conta padrão não estiver configurada nas preferências, será utilizado o preço de varejo (de tabela).

**Tópico principal:** [Configurar a governança d Cloudability](../admin/governance-setup-cldy-governance.html)
