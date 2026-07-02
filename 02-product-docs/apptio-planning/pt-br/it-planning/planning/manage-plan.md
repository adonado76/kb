---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Gerenciando planos"
breadcrumb:
  - "Planning"
  - "Criação e gerenciamento de planos"
source_path: "it-planning/planning/manage-plan.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Gerenciando planos

A página **Planos** oferece um espaço de trabalho central para criar, visualizar e gerenciar seus planos. Aqui, você pode abrir planos existentes, configurar as propriedades do plano e executar ações de ciclo de vida, como arquivamento ou exclusão.

Observação: As funções de administrador ou de proprietário do processo orçamentário são necessárias para gerenciar planos.

## Acesso a planos

1. Abra o painel de navegação à esquerda.
2. Selecione **Planejamento > Planos**.
3. Use as guias na parte superior da página para alternar entre elas:
   - **Available Plans (Planos disponíveis** ) - Mostra todos os planos ativos que podem ser acessados pelos proprietários de centros de custo.
   - **Archived Plans (Planos arquivados** ) - Mostra planos arquivados, acessíveis apenas a usuários com funções de administrador ou proprietário do processo orçamentário.
   - **All Plans (Todos os planos** ) - Mostra todos os planos do sistema.

## Visualização das propriedades do plano

Selecione o **ícone de lápis** ao lado de um plano para abrir o **painel Properties (Propriedades** ), que exibe os seguintes detalhes:

- **Plan Name (Nome do plano** ) - Renomeie o plano clicando no ícone de lápis.
- **Type (Tipo** ) - Indica se o plano é um *orçamento* ou uma *previsão*.
- **Estado** - Mostra o estágio atual do ciclo de vida (*Novo, Aberto ou Final* ).
- **Status** - Exibe se o plano está *Disponível* ou *Arquivado*.
- **Data de criação** - A data em que o plano foi criado.
- **Duração do plano** - O número total de anos cobertos pelo plano.
- **Ano de início do plano** - O primeiro ano incluído no plano.
- **Descrição do plano** – Permite que os administradores ou responsáveis pelo processo orçamentário insiram descrições do plano, premissas-chave, orientações ou comunicados. A descrição é exibida no cabeçalho do plano em todas as páginas, incluindo Despesas, Painel e outras. Os usuários podem mostrar ou ocultar a descrição a qualquer momento usando o ícone de sino no cabeçalho do plano.

## Planos de arquivamento e restauração

- **Arquivar um plano** - Move-o da lista Disponível para Arquivado.
  - Para arquivar um único plano: clique com o botão direito do mouse no plano e selecione **Archive (Arquivar** ).
  - Para arquivar vários planos: selecione-os usando a caixa de seleção de edição em massa, clique com o botão direito do mouse e selecione **Arquivar**.
- **Restaurar um plano** - Move-o de volta para a lista Available (Disponível).
  - Para restaurar um único plano: clique com o botão direito do mouse no plano e selecione **Restore (Restaurar** ).
  - Para restaurar vários planos: selecione-os, clique com o botão direito do mouse e selecione **Restore (Restaurar** ).

## Exclusão de planos

A exclusão do plano é um processo de duas etapas:

- **Soft Delete (Exclusão suave** ) - O plano é imediatamente removido da interface do usuário quando um administrador o exclui. Ele está inacessível para os usuários, mas pode ser restaurado dentro de dois dias com o registro de um tíquete de suporte.
- **Hard Delete (Exclusão definitiva** ) - Dois dias após a exclusão definitiva, os dados do plano são removidos permanentemente.

Esse processo garante uma remoção mais rápida da IU e oferece uma janela de segurança de dois dias para a recuperação. Quando vários planos são excluídos, eles são processados sequencialmente durante a limpeza.

- Para excluir um único plano: clique com o botão direito do mouse e selecione **Excluir**.
- Para excluir vários planos: selecione-os com a caixa de seleção de edição em massa, clique com o botão direito do mouse e selecione **Excluir**.
