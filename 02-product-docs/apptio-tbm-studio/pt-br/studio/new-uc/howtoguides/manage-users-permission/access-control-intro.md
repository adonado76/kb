---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Controle de acesso"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Gerenciar usuários e permissões"
source_path: "studio/new-uc/howtoguides/manage-users-permission/access-control-intro.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Controle de acesso

|  |  |
| --- | --- |
| **Tipo de Conteúdo** | Guias práticos |
| **Público-alvo** | Administradores, usuários avançados |
| **Tempo de conclusão** | 45 a 60 minutos (varia de acordo com o guia) |
| **Pré-requisitos** | Usuários e funções configurados (Seção 3.4.1 ), função de Administrador ou Usuário Avançado |

## Visão geral

O TBM Studio oferece vários níveis de controle de acesso para garantir que os usuários vejam apenas os relatórios e dados adequados à sua função. Esta seção aborda três abordagens complementares: permissões de relatórios (quem pode ver quais relatórios), segurança no nível da linha (quais linhas de dados os usuários podem visualizar) e permissões de tabelas editáveis (quem pode modificar dados específicos).

Esses mecanismos de controle de acesso atuam em conjunto para criar um modelo de segurança abrangente. Você pode combiná-los de acordo com as necessidades da sua organização. Para conhecer os fundamentos conceituais da arquitetura de segurança do TBM Studio, consulte **a seção “Modelo de segurança do 4.4:** ”. Para obter detalhes sobre a implementação da camada de dados do RLS, consulte **a seção 3.1.4: Segurança de dados**.

## Compreendendo as camadas de controle de acesso

O TBM Studio implementa o controle de acesso em três camadas distintas, cada uma com uma finalidade diferente:

|  |  |  |
| --- | --- | --- |
| **Camada** | **O que controla** | **Ideal para** |
| **Permissões do relatório** | Visibilidade de relatórios completos e de seus componentes | Restringir o acesso a painéis ou coleções de relatórios específicos por função do usuário |
| **Segurança em nível de linha (RLS)** | Quais linhas de dados um usuário pode visualizar em todos os relatórios | Cenários multilocatários em que diferentes usuários devem ter acesso a diferentes subconjuntos de dados (por exemplo, por unidade de negócios ou centro de custo) |
| **Permissões para tabelas editáveis** | Quem pode editar, enviar ou excluir dados em tabelas editáveis | Entrada de dados distribuída, em que diferentes equipes mantêm seus próprios dados de mapeamento ou classificação |

- **[Guia de decisão: Como escolher o sistema de controle de acesso certo](../../../../studio/new-uc/howtoguides/manage-users-permission/decision-guide.html)**
- **[Definir permissões de relatórios por função](../../../../studio/new-uc/howtoguides/manage-users-permission/set-report-perm.html)**
- **[Implementar segurança no nível da linha para o acesso do usuário](../../../../studio/new-uc/howtoguides/manage-users-permission/implement-rls.html)**
- **[Configurar permissões para tabelas editáveis](../../../../studio/new-uc/howtoguides/manage-users-permission/config-et-perm.html)**
