---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Permissões de relatórios e componentes"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
source_path: "studio/new-uc/concepts-architecture/security-model/report-component-permission.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Permissões de relatórios e componentes

Enquanto as funções controlam o acesso geral e o RLS controla a visibilidade dos dados, as permissões de relatórios e componentes oferecem uma camada adicional de controle sobre a experiência do usuário no Report Studio. Essas permissões determinam quais relatórios um usuário pode visualizar e quais componentes dentro de um relatório ficam visíveis para diferentes funções.

## Permissões do relatório

As permissões dos relatórios determinam quem pode visualizar e quem pode editar cada relatório. A partir do TBM Studio 12.7, as permissões de relatórios são gerenciadas por meio de uma interface simplificada, em vez de criar cópias separadas de relatórios para cada função.

**Modelo de permissão de relatórios**

Ao criar um relatório, você seleciona quem pode visualizá-lo. As opções incluem:

- **Todos os usuários:** O relatório está visível para qualquer pessoa com acesso ao projeto.
- **Funções específicas:** Somente os usuários atribuídos às funções selecionadas podem visualizar o relatório.
- **Somente pessoal:** o relatório é visível apenas para o criador. Requer a permissão “Editar relatórios pessoais” (atribuída por padrão à função Analista).

As permissões do relatório são configuradas na caixa de diálogo Permissões, acessível na guia Projeto, no grupo Avançado.

**Coleções de relatórios e permissões**

Agrupe relatórios relacionados para facilitar a navegação. Os administradores podem definir permissões de função para coleções, controlando quais funções de usuário podem acessar relatórios dentro de cada coleção. Somente administradores podem criar coleções de relatórios, e apenas no projeto Padrão de Cálculo de Custos. Depois de criadas, as coleções ficam disponíveis em todo o projeto.

- **[Visibilidade no nível do componente](../../../../studio/new-uc/concepts-architecture/security-model/component-level-visibility.html)**
- **[Permissões para tabelas editáveis](../../../../studio/new-uc/concepts-architecture/security-model/editable-table-permissions.html)**
- **[Permissões do componente de upload de tabelas](../../../../studio/new-uc/concepts-architecture/security-model/table-upload-component-permissions.html)**
- **[Como as permissões de relatório e o RLS interagem](../../../../studio/new-uc/concepts-architecture/security-model/report-permission-rls-interact.html)**
