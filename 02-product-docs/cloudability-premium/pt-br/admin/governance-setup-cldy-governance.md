---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Configurar Cloudability Governança"
breadcrumb:
  - "Cloudability Premium"
  - "Governança"
source_path: "admin/governance-setup-cldy-governance.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Configurar Cloudability Governança

## Antes de começar

Esta documentação destina-se às seguintes funções em uma organização:

- **Administradores da plataforma** - São responsáveis por configurar o recurso e instalar o aplicativo GitHub. Para as organizações que usam o HCP ou o Terraform Enterprise, será necessário configurar a tarefa de execução de governança do Cloudability e garantir que ela esteja alinhada com as proteções organizacionais.
- **FinOps Equipes** - Elas definirão e gerenciarão as políticas da organização (como famílias de instâncias aprovadas, tags necessárias ou restrições regionais).
- **Engenheiros de nuvem** - Eles consumirão a integração da governança do Cloudability com o GitHub e o Terraform. Os desenvolvedores executam planos e aplicações do Terraform como parte de seus fluxos de trabalho e recebem feedback imediato sobre custos e conformidade.

Para usar esse recurso com êxito, certifique-se de que os seguintes pré-requisitos estejam em vigor:

- **Para usuários d GitHub :**

  - Repositório contendo exemplos de código Terraform.
  - Lista de permissões de IP - Se a sua organização GitHub utiliza uma lista de permissões de IP, você deve garantir que os intervalos de IP de saída do Cloudability estejam incluídos. Sem essas entradas, o Cloudability Governance não poderá se comunicar com seus repositórios GitHub, e as verificações de política poderão falhar. Os seguintes intervalos de IP devem ser adicionados à lista de permissões da sua organização GitHub :
    - **185.115.88.0/22**
    - **103.195.128.0/22**
    - **129.41.0.0/22**
- Uma conta IBM Cloudability com as permissões de governança corretas atribuídas.
- **Para clientes do HCP Terraform / Terraform** : Uma conta do HCP Terraform com permissões para criar espaços de trabalho e gerenciar Run Tasks.
- **Para usuários da Comunidade Terraform** : GitHub As ações estão disponíveis em sua conta GitHub.

## Visão geral

Para configurar a Governança, os administradores do Cloudability precisam configurar a integração com o GitHub, que será utilizada no fluxo de trabalho de aprovação de Pull Requests (PR) para todos os tipos de clientes. Em seguida, dependendo da plataforma Terraform em uso, as etapas de configuração são diferentes:

- **Para usuários do HCP Terraform ou Terraform Enterprise**, não é necessário acessar GitHub Actions. Em vez disso, os administradores devem configurar uma tarefa de execução no espaço de trabalho do Terraform, recuperando a chave HMAC e o ponto de extremidade URL em Cloudability e adicionando-os à configuração da tarefa de execução.
- **Para os usuários da Terraform Community**, os administradores precisam configurar algumas variáveis/secrets em nível de organização em GitHub para armazenar as chaves da API do Frontdoor, o Frontdoor URL, a ID do ambiente do Frontdoor e a API Cloudability URL. Eles também precisam criar ou configurar seus próprios fluxos de trabalho de ação GitHub que invocam as ações de governança Cloudability GitHub.

Depois de concluído, o Governance identificará suas “implantações” (unidades gerenciadas pelo Terraform, também chamadas de “espaços de trabalho” no HCP Terraform) e as exibirá na página Configuração do Governance. Os usuários precisarão mapeá-los para projetos (que são grupos de implementações), que terão políticas associadas a eles. Os clientes podem optar por definir projetos por aplicativo, equipe, serviço ou ambiente. Um nome de projeto para uma implantação também pode ser fornecido como entrada opcional dentro do próprio fluxo de trabalho da ação GitHub.

- **[Instalação do aplicativo GitHub.com (na nuvem)](../admin/governance-github-app-installation.html)**
- **[GitHub Enterprise Instalação do aplicativo no servidor (local)](../admin/governance-github-enterprise-installation.html)**
- **[HCP Terraform/Terraform Enterprise](../admin/governance-hcp-terraform-terraform-enterprise.html)**
- **[Configurar GitHub Actions for Terraform Community](../admin/governance-configure-github-actions-for-terraform-community.html)**
- **[Configurações de implantação](../admin/governance-deployment-configurations.html)**
- **[Configuração de preferências](../admin/governance-preferences-configurations.html)**
