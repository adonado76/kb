---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Atribuição de permissões"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Permissões do relatório"
source_path: "studio/new-uc/reference/report-studio-reference/permission-assignment.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Atribuição de permissões

**Permissões baseadas em funções**

As permissões no TBM Studio são atribuídas principalmente por meio de funções. Cada usuário é atribuído a uma ou mais funções que determinam seu nível de acesso.

**Funções padrão do sistema:**

|  |  |  |
| --- | --- | --- |
| **Função** | **Descrição** | **Recursos de relatórios** |
| **Admin** | Acesso total ao sistema | Criar, editar, excluir e configurar todos os relatórios |
| **Usuário avançado** | Configuração avançada | Criar e editar relatórios |
| **Analista** | Relatório de consumo com personalização | Visualizar relatórios, criar relatórios pessoais, adicionar tabelas/gráficos personalizados |
| **Somente visualizar** | Relatar apenas o consumo | Visualizar e filtrar relatórios |

**Atribuição de permissões a funções:**

1. Na guia Relatório, clique em Permissões
2. Selecionar funções selecionadas
3. Clique no menu suspenso “Selecionar funções”
4. Escolha as funções que devem ter acesso
5. Clique em OK e verifique o relatório

Dica: Ao restringir um relatório a funções específicas, certifique-se de que todos os usuários que precisam de acesso estejam atribuídos a pelo menos uma das funções selecionadas.

**Herança de permissões**

**Herdando do projeto**

Os relatórios herdam as configurações básicas de acesso das definições no nível do projeto:

- Os usuários devem ter acesso ao projeto para visualizar quaisquer relatórios nesse projeto
- As atribuições de funções no nível do projeto determinam quem pode acessar o projeto
- Os relatórios podem restringir ainda mais (mas não ampliar) o acesso além das permissões do projeto

**Substituir vs. Herdar configurações**

As permissões no nível do relatório substituem as configurações no nível da coleção. A permissão efetiva é a combinação mais restritiva:

|  |  |  |
| --- | --- | --- |
| **Configuração da coleção** | **Configuração do relatório** | **Acesso efetivo** |
| Todos | Todos | Todos |
| Todos | Somente analistas | Somente analistas |
| Somente administradores | Todos | Somente administradores |
| Analistas, Administradores | Somente administradores | Somente administradores |

**Tópico principal:** [Permissões de relatórios](../../../../studio/new-uc/reference/report-studio-reference/report-permissions.html)
