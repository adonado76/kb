---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Configurações de implantação"
breadcrumb:
  - "Cloudability Premium"
  - "Governança"
  - "Configurar Cloudability Governança"
source_path: "admin/governance-deployment-configurations.html"
images:
  - "images/gov6.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Configurações de implantação

Observação: uma implantação é uma unidade gerenciada pelo Terraform, que normalmente está vinculada a um serviço, ambiente e região específicos. Ele representa uma unidade de alteração única e com versão aplicada ao ambiente de infraestrutura. **Uma implantação corresponde a um espaço de trabalho no HCP Terraform**.

***Por exemplo:*** *Uma equipe é proprietária de um ServiceA e o implementa em vários ambientes, como (beta, staging, production), então ela pode configurar implementações no Governance para ServiceA-beta, ServiceA-staging, ServiceA-production.*

As implantações são geradas automaticamente e listadas na página Configuração de governança quando:

- Uma ação GitHub é invocada a partir de fluxos de trabalho de CI/CD, ou
- Uma tarefa de execução é acionada no HCP Terraform após a conclusão da configuração.

Não é necessário adicionar manualmente as implementações na UI de configuração de governança do Cloudability. Recomendamos agrupar essas "Implantações" em "Projetos" para facilitar a aplicação de políticas. os "projetos" representam mecanismos de agrupamento específicos da Cloudability Governance.

Abaixo estão os campos associados a cada uma de suas implantações (recuperados automaticamente, exceto para "Projeto"):

- **IaC Provedor** : Terraform ou Terragrunt
- **Nome da implantação:** Nome dado à implantação para identificá-la (precisa ser exclusivo entre todas as suas implantações)
- **Projeto:** Mecanismo de agrupamento específico para Cloudability Governança
- **GitHub Repositório:** Repositório onde o código da infraestrutura está localizado
- **Ramificação base:** Branch monitorado pela Governança e é o alvo para mesclagens de pull requests. Normalmente, ele representa sua ramificação principal ou master e serve como ponto de referência para detectar alterações nos custos de infraestrutura.

![imagem](../../../../03-media/cloudability-premium/images/gov6.png)

**Tópico principal:** [Configurar Cloudability Governança](../admin/governance-setup-cldy-governance.html)
