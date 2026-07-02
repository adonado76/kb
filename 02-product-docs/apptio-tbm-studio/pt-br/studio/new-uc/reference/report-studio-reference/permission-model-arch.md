---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Arquitetura do modelo de permissões"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Permissões do relatório"
source_path: "studio/new-uc/reference/report-studio-reference/permission-model-arch.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Arquitetura do modelo de permissões

**Como as permissões de relatórios se encaixam na hierarquia de segurança**

O modelo de permissões de relatórios do TBM Studio opera dentro de uma arquitetura de segurança em camadas:

|  |  |  |
| --- | --- | --- |
| **Nível** | **Escopo** | **Controlado por** |
| **Domínio** | Todos os projetos de um domínio | Administração de Acesso Aprimorada |
| **Projeto** | Todos os recursos de um projeto | Atribuições de funções no nível do projeto |
| **Coleta de relatórios** | Grupos de relatórios relacionados | Permissões no nível da coleção |
| **Reportar** | Relatório individual | Permissões no nível do relatório |
| **Componente** | Elementos de um relatório | Configurações de visibilidade dos componentes |
| **Dados (RLS)** | Acesso aos dados em nível de linha | Projeto de Segurança ao Nível da Linha |

As permissões se aplicam de um escopo mais amplo para um mais restrito. Um usuário deve ter permissão adequada em cada nível para visualizar um relatório e seus dados. Por exemplo, um usuário com permissão de visualização no nível do relatório ainda não poderá ver os dados filtrados pelo RLS, a menos que seu ID de usuário esteja incluído nas tabelas de mapeamento do RLS.

**Relação com as permissões do projeto**

As permissões de relatório são um subconjunto do modelo mais amplo de permissões do projeto. A função atribuída a um usuário no âmbito do projeto determina suas competências básicas:

**Herdado da função do projeto:**

- Capacidade de acessar o TBM Studio e projetos específicos
- Capacidade de criar novos relatórios (requer permissões para criação de conteúdo)
- Capacidade de baixar e modificar a configuração
- Acesso a recursos administrativos

**Configurado no nível do relatório:**

- Quais funções têm permissão para visualizar relatórios específicos
- Quais funções têm permissão para visualizar componentes específicos nos relatórios
- Informações sobre a composição e a visibilidade do relatório

Observação: as funções do projeto são gerenciadas por meio da Administração de Acesso Avançada. Para obter informações sobre como configurar funções de usuário, consulte a Seção 6.2: Gerenciamento de usuários.

**Relação com a segurança no nível da linha (RLS)**

A segurança no nível da linha e as permissões de relatório têm finalidades diferentes e funcionam em conjunto:

|  |  |  |
| --- | --- | --- |
| **Aspecto** | **Permissões do relatório** | **Segurança no nível da linha** |
| **Controles** | Acesso à interface do usuário do relatório | Acesso às linhas de dados |
| **Granularidade** | Nível de relatório/componente | Linhas de dados individuais |
| **Configurado em** | Report Studio | Projeto de Segurança ao Nível da Linha |
| **Com base em** | Designação de função | Mapeamento de ID de usuário |

Um usuário pode ter permissão para visualizar um relatório, mas ver apenas dados limitados, dependendo da configuração do RLS. Por outro lado, o RLS não concede acesso aos relatórios — os usuários ainda precisam de permissões adequadas no nível do relatório.

Importante: A segurança no nível da linha afeta todos os usuários, mas não protege os dados dos usuários com privilégios de administrador. Os usuários administradores têm acesso ao modo Studio e podem criar relatórios que contornam o RLS, adicionar-se às tabelas de mapeamento do RLS ou desativar completamente o RLS. Não confie exclusivamente no RLS para proteger dados confidenciais dos administradores

.

**Tópico principal:** [Permissões de relatórios](../../../../studio/new-uc/reference/report-studio-reference/report-permissions.html)
