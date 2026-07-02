---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Funções padrão"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
  - "Controle de acesso baseado em funções (RBAC)"
source_path: "studio/new-uc/concepts-architecture/security-model/default-roles.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Funções padrão

O TBM Studio oferece três funções padrão. Cada função representa um nível comum de acesso para diferentes tipos de usuários.

**Administrador (Admin)**

|  |  |
| --- | --- |
| **Aspecto** | **Detalhes** |
| Recursos | Acesso total a todos os recursos: criar/editar projetos, gerenciar usuários e funções, definir configurações de segurança, compilar e promover projetos, criar relatórios, modificar modelos, fazer upload de dados, acessar todos os ambientes (Dev, Stage, Prod) |
| Principais responsabilidades | Configuração do sistema, gerenciamento de usuários, administração de segurança, gerenciamento do ciclo de vida de compilação, resolução de problemas, instalação de componentes |
| Quando atribuir | Gerentes financeiros de TI que configuram o TBM Studio, administradores de sistema responsáveis pela plataforma e analistas sênior que gerenciam o modelo e o processo de implantação |
| Permissões essenciais | AccessDev, AccessStg, AccessProd, Editar modelos, UploadData, ViewViewAllData,, além de todas as permissões de visualização e geração de relatórios |

Importante:

**Admin e RLS**

A segurança no nível da linha não restringe de forma confiável os usuários administradores. Os usuários administradores têm acesso ao modo Studio e podem, em última instância, criar relatórios que contornam o RLS, adicionar-se às tabelas de mapeamento do RLS e desativar completamente o RLS. Não confie no RLS para proteger os dados dos usuários administradores.

**Usuário avançado**

|  |  |
| --- | --- |
| **Aspecto** | **Detalhes** |
| Recursos | Pode criar e editar relatórios, modificar modelos e transformações de dados, fazer upload de dados e acessar ambientes de desenvolvimento e de teste. É possível verificar as mensagens de erro. Não é possível gerenciar usuários nem modificar configurações no nível do domínio. |
| Principais responsabilidades | Criação e manutenção de modelos de custos, elaboração de relatórios para as partes interessadas, transformação de dados e execução de cálculos preliminares |
| Quando atribuir | Analistas financeiros de TI que elaboram modelos de custos, desenvolvedores de relatórios que projetam e mantêm relatórios, analistas de dados que gerenciam fluxos de dados |
| Permissões essenciais | AccessDev, AccessStg, Editar modelos, UploadData, DrillDown, Editar relatórios pessoais, além das permissões de visualização padrão |

**Usuário corporativo**

|  |  |
| --- | --- |
| **Aspecto** | **Detalhes** |
| Recursos | Visualizar relatórios e dados em produção. Apenas para visualização — não é possível modificar modelos, transformações ou a configuração do sistema. Pode interagir com componentes de tabela editáveis em relatórios, desde que tenha permissão para isso. |
| Principais responsabilidades | Consultar relatórios de custos, analisar gastos com TI, revisar alocações, inserir dados em tabelas editáveis (se configuradas) |
| Quando atribuir | Partes interessadas da empresa que precisam consultar relatórios, gerentes de departamento que analisam seus dados de custos, qualquer usuário que precise de acesso somente para leitura |
| Permissões essenciais | AccessProd, ViewReportsSavedForEveryone, ViewObjectReports, ViewMetricReports, DrillDown, além de permissões de visualização limitadas |

Nota:

**Cargos adicionais**

Algumas instalações incluem uma função de Analista com a permissão “Editar relatórios pessoais”, permitindo que os usuários criem relatórios pessoais visíveis apenas para eles próprios. Verifique com seu administrador a lista completa de funções em seu ambiente.

**Tópico principal:** [Controle de acesso baseado em funções (RBAC)](../../../../studio/new-uc/concepts-architecture/security-model/role-based-access.html)
