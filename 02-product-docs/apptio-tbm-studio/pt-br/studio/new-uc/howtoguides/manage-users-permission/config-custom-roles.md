---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configurar funções personalizadas"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Gerenciar usuários e permissões"
  - "Gerenciamento de usuários"
source_path: "studio/new-uc/howtoguides/manage-users-permission/config-custom-roles.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar funções personalizadas

**Objetivo:** Criar funções personalizadas com combinações específicas de permissões para atender às necessidades específicas da organização.

**Quando usar:** Quando as funções padrão não oferecem a combinação exata de permissões de que seus usuários precisam, ou quando você precisa de um controle mais detalhado sobre recursos específicos.

**Tempo estimado:** 15 a 30 minutos por função

**Pré-requisitos**

- É necessário ter o papel de administrador.
- Compreensão clara das permissões necessárias para o grupo de usuários-alvo.
- Documentação dos requisitos de controle de acesso da sua organização.

## Quando criar funções personalizadas

Considere criar uma função personalizada quando:

- Os usuários precisam de um subconjunto das permissões de usuário avançado, mas não de acesso total.
- Você precisa de contas exclusivas para API com permissões limitadas para automação.
- Equipes diferentes exigem níveis diferentes de acesso aos relatórios.
- Você precisa restringir o acesso a ambientes específicos (Dev, Stage, Prod).
- Os requisitos de conformidade exigem a separação de funções.

## Passos

1. **Gerenciamento de funções do Access.** Na Administração de Acesso Avançado, acesse a seção **Funções e Permissões**.
2. **Crie uma nova função.** Clique em **“Adicionar personalizado” RoleName e a função.** Insira um nome e uma descrição que indiquem a finalidade da função (por exemplo, “Carregador de dados”, “Visualizador de relatórios – Finanças”, “Integração de API”).
3. **Selecione as permissões.** Escolha as permissões específicas que esta função deve ter. As categorias comuns de permissão incluem:

   |  |  |
   | --- | --- |
   | **Categoria de permissão** | **Exemplos** |
   | **Acesso ao ambiente** | AccessDev, AccessStg, AccessProd |
   | **Operações de dados** | UploadData, DrillDown, ViewAllData |
   | **Relatório** | ViewMetricReports, ViewObjectReports, ViewTransformReports, ViewReportsSavedForEveryone, Editar relatórios pessoais |
   | **Exportar** | CanExportExcel, CanExportPDF (permite o download de dados) |
4. **Salve a função.** Clique em **Salvar** para criar a função personalizada.
5. **Experimente o papel.** Atribua a função a um usuário de teste e verifique se as permissões funcionam conforme o esperado antes de implementá-la para outros usuários.

## Exemplos de funções personalizadas

***Exemplo 1: Função de carregador de dados***

Para usuários que precisam apenas enviar arquivos de dados, mas não precisam criar modelos nem visualizar todos os relatórios.

- AccessDev
- UploadData

***Exemplo 2: Visualizador de relatórios financeiros***

Para membros da equipe financeira que precisam de acesso aos relatórios de produção, mas não têm permissão para fazer configurações.

- AccessProd
- ViewMetricReports
- ViewObjectReports
- CanExportEcel

***Exemplo 3: Conta de integração de API***

Para processos automatizados que fazem upload e download de dados por meio de API.

- AccessDev
- UploadData
- CanExportExcel

## Armadilhas comuns

- **Excesso de permissões:** adicionar permissões em excesso vai contra o objetivo de uma função personalizada. Comece com o mínimo e adicione permissões conforme necessário.
- **Permissões dependentes ausentes:** algumas permissões dependem de outras para funcionar. Faça testes exaustivos para garantir que a função opera conforme o esperado.
- **Permissões duplicadas de "Upload":** Observe que " "UploadData" " e "Upload Data" são permissões distintas. Inclua ambos para que a funcionalidade de upload funcione corretamente.
- **Não documentar funções personalizadas:** sempre documente a finalidade de cada função personalizada e quais permissões ela inclui.

## O que vem a seguir

Depois de configurar usuários e funções, você pode querer:

- **Configure as permissões dos relatórios** para controlar quais relatórios cada função pode acessar. Consulte [Controle de acesso](access-control-intro.html).
- **Implemente a segurança no nível da linha** para restringir a visibilidade dos dados com base na identidade do usuário. Consulte [Controle de acesso](access-control-intro.html).
- **Configure a integração de SSO** para autenticação corporativa. Consulte [a seção "Gerenciamento de usuários"](../../admin/user-management.html) para obter informações detalhadas.
- **Monitore a atividade dos usuários** usando os relatórios de uso d Apptio. Consulte [Gerenciamento de usuários](../../admin/user-management.html).

**Tópico principal:** [Gestão de usuários](../../../../studio/new-uc/howtoguides/manage-users-permission/manage-up-intro.html)
