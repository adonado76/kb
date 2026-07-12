---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Status do plano"
breadcrumb:
  - "Planning"
  - "Fluxos de trabalho e colaboração"
source_path: "it-planning/planning/plan-status.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Status do plano

A página **Status do plano** em Apptio Planning oferece uma visão centralizada para acompanhar o progresso dos planos departamentais durante todo o processo de planejamento e aprovação. Ele ajuda os usuários a monitorar a propriedade do plano, o status atual e a atividade recente em todos os departamentos de um ciclo de plano.

## Visão geral do status do plano

O plano de cada departamento passa por um fluxo de trabalho definido de alterações de status à medida que avança no processo de planejamento e aprovação:

- **Em andamento** - O estado inicial quando um departamento começa a trabalhar em seu plano.
- **Submitted (Enviado** ) - Indica que o plano foi enviado para análise e aprovação.
- **Aprovado** - O plano foi revisado e aprovado.
- **Devolvido** - O plano foi enviado de volta para revisões ou contribuições adicionais.

A tabela **Status** exibe os seguintes detalhes principais de cada departamento:

- **Owners (Proprietários** ) - O(s) usuário(s) atribuído(s) como proprietário(s) do plano do departamento.
- **Status** - O estado atual do plano (Em andamento, Enviado, Aprovado ou Devolvido).
- **Última ação** - A data e a hora da atualização de status mais recente.
- **Ações disponíveis** - Ações contextuais disponíveis com base nas permissões do usuário (por exemplo, aprovar, devolver, comentar).

## Visualização e navegação na tabela de status

***Exibições hierárquicas e de lista***

- Para **aprovações hierárquicas**, é possível alternar entre uma **Visualização hierárquica** (para visualizar os departamentos em sua estrutura organizacional) e uma **Visualização de lista** (para obter uma lista simples de todos os departamentos).
- Use o **Seletor de visualização** na parte superior da página para alternar entre as visualizações.

***Aprovações em vários níveis***

- Para **fluxos de trabalho de aprovação multinível**, a tabela está disponível apenas como uma **Visualização de lista**.
- Uma coluna adicional, **Nível de aprovação**, mostra o andamento atual do processo de aprovação - por exemplo, *"1 de 3 aprovações".*
- À medida que cada nível for concluído, o status passará sequencialmente pelos níveis ( *L1 Approved → L2 Approved → L3 Approved* ), e o plano será exibido como **Approved** quando todas as aprovações necessárias forem concluídas.

## Aprovação e gerenciamento de planos

Os usuários com permissões de aprovação podem gerenciar os planos dos departamentos aos quais estão atribuídos:

- **Approve (Aprovar** ) - Marca o plano como aprovado para o nível de aprovação atual.
- **Devolver** - Envia o plano de volta ao proprietário do departamento para revisões.
- **Comentário** - Permite que os aprovadores ou revisores deixem comentários sem alterar o status.

## Ações em massa e histórico de exportação

Você pode executar ações em vários departamentos ao mesmo tempo usando o **menu Ações** na parte superior da página:

- **Envie, aprove** ou **devolva em massa** vários departamentos simultaneamente.
- **Exportar histórico** para baixar um registro detalhado de todas as alterações de status, incluindo carimbos de data e hora e usuários.

A exportação fornece uma trilha de auditoria completa do progresso e das aprovações do plano para fins de relatório e conformidade.
