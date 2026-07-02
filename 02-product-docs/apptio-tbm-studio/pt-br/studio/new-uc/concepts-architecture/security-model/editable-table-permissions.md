---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Permissões para tabelas editáveis"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Modelo de segurança"
  - "Permissões de relatórios e componentes"
source_path: "studio/new-uc/concepts-architecture/security-model/editable-table-permissions.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Permissões para tabelas editáveis

As tabelas editáveis nos relatórios possuem seu próprio sistema de permissões detalhado, que controla as ações no nível das linhas:

|  |  |  |
| --- | --- | --- |
| **Permissão** | **Controles** | **Padrão** |
| Permissão para adicionar linha | Quais funções podem adicionar novas linhas à tabela | Todos |
| Permissão para duplicar linha | Quais funções podem duplicar linhas | Todos |
| Permissão para excluir linha | Quais funções podem excluir linhas individuais | Todos |
| Permissão para publicar linha | Quais funções podem publicar alterações nas transformações? | Todos |
| Permissão para editar linha | Quais funções podem modificar linhas existentes | Todos |
| Permissão para baixar | Quais funções podem baixar os dados da tabela | Todos |
| Permissão para fazer upload | Quais funções podem enviar dados para a tabela | Todos |
| Mostrar permissão de histórico | Quais funções têm acesso ao histórico de alterações | Todos |
| Permissão para excluir todas as linhas | Quais funções podem excluir todas as linhas de uma só vez? | Administrador e Parceiro |

Cada permissão pode ser definida como “Todos” ou “Funções selecionadas”, permitindo um controle preciso sobre os fluxos de trabalho de entrada de dados.

**Tópico principal:** [Permissões de relatórios e componentes](../../../../studio/new-uc/concepts-architecture/security-model/report-component-permission.html)
