---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Gerenciar planos"
breadcrumb: []
source_path: "it-planning/planning/manage-plans.html"
images:
  - "resources/images/icons/icon-column-freeze_21x20.png"
  - "resources/images/icons/icon-filteron_18x20.png"
  - "resources/images/icons/icon-showhide_19x20.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Gerenciar planos

Com a página Planos, você pode gerenciar seus planos de forma fácil e intuitiva.

- Para abrir Planos, abra o painel de navegação à esquerda e selecione Planejamento > Planos.

  ![imagem](../../resources/images/it%20planning_images/plans2_430x128.png)

## Escolha os planos a serem exibidos

Use as guias na parte superior da tela para exibir All Plans (Todos os planos), Active Plans (Planos ativos) ou Archived Plans (Planos arquivados).

## Selecione as colunas a serem exibidas

Você pode fazer isso no painel Show/Hide Columns (Mostrar/Ocultar colunas).

- Selecione ![mais…](../../resources/images/it%20planning_images/options1_23x20.png) > Open Show/Hide Columns (Abrir mostrar/ocultar colunas).
- Marque ou desmarque as caixas de seleção para adicionar ou remover colunas.

## Criar um novo plano

1. Selecione ![adicionar ícone](../../resources/images/it%20planning_images/new-plan-icon_19x20.png).

   A caixa de diálogo New Plan é aberta.
2. Insira os detalhes do plano.

   [Saiba mais sobre a criação de planos](create-budget-plan.dita "(Abre em uma nova guia ou janela)")
3. Selecione Criar plano.

   O novo plano é exibido na página Budget ou Forecast.
4. Retorne a Plans e confirme se o novo plano está listado como um Active Plan (Plano ativo).

   Se Integrated Investment Planning estiver ativado, os projetos serão copiados para o novo plano com um dos seguintes métodos. Para saber mais sobre o Integrated Investment Planning, consulte [Introdução ao Integrated Investment Planning](iip/gs-integrated-investment-planning.dita "(Abre em uma nova guia ou janela)").

   - Criar plano sem plano de linha de base - Se você estiver criando um plano sem um plano de linha de base, os projetos da dimensão de dados de referência "Projeto" serão adicionados ao plano.
   - Create Plan with Baseline Plan (Criar plano com plano de linha de base) - Se você estiver criando um plano com um plano de linha de base, os projetos do plano de linha de base serão adicionados ao novo plano.

## Exibir os detalhes de um plano no painel Properties (Propriedades)

O painel Propriedades exibe as seguintes informações sobre um Plano:

- Tipo
- Estado
- Status (exibido apenas na guia Todos os planos)
- Data de criação
- Comprimento do plano
- Ano de início do plano

Para visualizar um plano no painel Properties, selecione ![visualizar plano](../../resources/images/it%20planning_images/icon-plan-properties_21x20.png).

## Planos de filtragem

Para filtrar os valores exibidos em uma coluna de plano:

1. Passe o mouse sobre o cabeçalho da coluna e selecione ![ícone](../../resources/images/it%20planning_images/burger-button_13x9.png).
2. Selecione ![ícone do filtro](../../../../../03-media/apptio-planning/resources/images/icons/icon-filteron_18x20.png) para filtrar os valores da coluna.

   Lembre-se: Você também pode usar esse painel para:
   - Mostrar e ocultar colunas, selecionando ![ícone de coluna](../../../../../03-media/apptio-planning/resources/images/icons/icon-showhide_19x20.png)
   - Congelar e descongelar colunas, selecionando ![descongelar colunas](../../../../../03-media/apptio-planning/resources/images/icons/icon-column-freeze_21x20.png)

   O planejamento abre a lista de filtros para sua escolha. Por padrão, (Select All) é selecionado.

   ![imagem](../../resources/images/it%20planning_images/plan-filter.png)
3. Filtre os valores a serem exibidos na coluna seguindo um dos seguintes procedimentos:
   - Limpe (Select All) e marque as caixas de seleção ao lado dos valores necessários.
   - Digite um termo de pesquisa a ser usado para filtrar valores. Todos os valores que correspondem a todo ou parte do termo de pesquisa são exibidos em uma lista. Para aplicar o filtro ao plano, selecione Enter.

   Você pode filtrar qualquer coluna, exceto as colunas com valores exclusivos por plano. As colunas que têm filtros aplicados aparecem com um ícone de filtro no cabeçalho.

   ![imagem](../../resources/images/it%20planning_images/current-filters.png)

## Limpar filtros

Para limpar os filtros, selecione ![filtro](../../resources/images/it%20planning_images/clear-filters_20x20.png) acima do plano.

## Ordenar planos por coluna

- Para classificar os planos por uma coluna, passe o mouse sobre o cabeçalho da coluna e selecione ![ordenar](../../resources/images/it%20planning_images/itfmf-ct_images/sort-icon_21x20.png).

## Arquivar planos ativos

Isso move o plano da lista Active (Ativo) para a lista Archived (Arquivado). Você pode restaurar um plano arquivado de volta ao status Active a qualquer momento.

Só é possível arquivar planos na guia Active Plans (Planos ativos).

- Para arquivar um único plano, clique com o botão direito do mouse no plano que deseja arquivar e selecione Archive.
- Para arquivar vários planos, selecione os planos usando a caixa de seleção de edição em massa, clique com o botão direito do mouse em qualquer um dos planos selecionados e selecione Arquivar.

## Restaurar planos arquivados

Só é possível restaurar planos na guia Archived Plans (Planos arquivados).

- Para restaurar um único plano, clique com o botão direito do mouse no plano que deseja restaurar e selecione Restore (Restaurar).
- Para restaurar vários planos, selecione os planos usando a caixa de seleção de edição em massa, clique com o botão direito do mouse em qualquer um dos planos selecionados e selecione Restore (Restaurar).

## Excluir planos

Você pode excluir planos de qualquer guia.

Observação: A exclusão de um plano o remove permanentemente do sistema.

- Para excluir um único plano, clique com o botão direito do mouse no plano que deseja excluir e selecione Delete (Excluir).
- Para excluir vários planos, selecione os planos usando a caixa de seleção de edição em massa, clique com o botão direito do mouse em qualquer um dos planos selecionados e selecione Excluir.

## Plano de exclusão suave

Na versão de planejamento ApptioOne 3.50, o processo de exclusão do plano agora ocorre em duas etapas:

- Soft Delete (Exclusão suave ) - O plano é removido da interface do usuário assim que um administrador clica no botão Delete (Excluir) na página Plans (Planos). O plano excluído não estará mais acessível aos usuários.
- Hard Delete (Exclusão definitiva ) - Os dados do plano são excluídos automaticamente, dois dias após a exclusão definitiva.

Os administradores não precisam mais esperar pelo longo processo de exclusão de planos; exclua um plano rapidamente e depois prossiga com outras tarefas. Caso você exclua acidentalmente algum plano, há um período de dois dias para restaurar os dados do plano registrando um tíquete de suporte em Apptio.

Não há nenhuma alteração para o usuário final no processo de exclusão do plano. As etapas para excluir o plano, conforme descritas aqui, ainda são válidas. A única diferença perceptível para o usuário final é que o plano é removido muito rapidamente da interface do usuário do aplicativo Planning, independentemente do tamanho do plano.

Se vários planos forem selecionados para exclusão, as solicitações de exclusão de dados do plano serão adicionadas em uma fila e processadas sequencialmente durante o processo de limpeza de dados.
