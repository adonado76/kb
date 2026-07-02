---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Trabalhando com o Painel de Integração de Transparência de Custos"
breadcrumb: []
source_path: "it-planning/planning/cti_panel.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Trabalhando com o Painel de Integração de Transparência de Custos

O painel Cost Transparency Integration (CTI) atualizado, introduzido na versão Planning 2.78, é um espaço independente em que os usuários administradores podem executar todas as tarefas do Cost Transparency Integration em um único painel de controle. O novo painel oferece gerenciamento centralizado e importação e exportação com um clique, com transparência de custos.

## Acessar o painel CTI

O painel Cost Transparency Integration permite que você execute todas as tarefas de CTI, que são divididas em páginas separadas. As seções seguintes deste tópico descrevem o conteúdo de cada página e as tarefas correspondentes que podem ser executadas.

1. Faça login em Planning.
2. Abra o menu Configurações.
3. Clique em Cost Transparency Integration.

## Configurar o painel CTI

Essa opção contém as definições de configuração da CTI. Esse processo de configuração geralmente é concluído pelos membros da equipe de entrega do Apptio na configuração inicial e raramente é modificado posteriormente.

Nenhuma alteração foi feita na página de configuração em relação às versões anteriores do produto. Para obter mais informações sobre esse processo de configuração, consulte [Integrar com Costing Standard](integrate-ct.html "Se a sua organização executa o Apptio Costing Standard e um aplicativo Apptio Planning, é possível integrá-los para compartilhar dados.").

## Importação real

A tarefa Import Actuals é executada por um TBMA (geralmente uma vez por mês) para importar dados de despesas reais de Costing Standard para Planning. Use os valores reais importados para formar previsões, realizar análise de variação e criar outras exibições de comparação.

1. Na página Import Actuals CTI, selecione os meses para os quais você deseja importar os dados reais.

   Se forem escolhidos vários meses, será realizada uma importação em massa.
2. Quando todos os meses tiverem sido selecionados, clique no botão azul Importar.

É exibida uma mensagem que recomenda ir para a página Status e verificar o status do seu trabalho. Para o processo Import Actuals (Importar dados reais), vá para a página Status.

Você também pode retornar à página inicial do CTI para continuar com outras tarefas do CTI. Você não fica impedido de realizar outras tarefas de Planning e CTI, mesmo que um trabalho de importação grande ou demorado esteja em andamento.

## Importar dados de referência

PlanningO planejamento usa dados de referência como informações de base para fins de planejamento e inclui informações como plano de contas, hierarquia de departamentos ou listas de centros de custo e fornecedores. A página Importar dados de referência permite que você extraia dados de referência de Costing Standard para Planning.

1. Selecione na lista os dados de referência que deseja importar.
2. Role até a parte inferior da página e clique no botão Importar.

Todos os conjuntos de dados de referência são selecionados por padrão, dando suporte à importação em massa.

É exibida uma janela pop-up que recomenda ir para a página Status e verificar o status do seu trabalho. Para concluir o processo de importação de dados de referência, você deve ir para a página Status e publicar os dados importados quando o trabalho estiver concluído.

Observação: Recomenda-se que você revise os dados carregados caso tenham sido feitas alterações importantes. Depois que você publica os dados de referência, não há como revertê-los.

Você também pode retornar à página inicial do CTI para continuar com outras tarefas do CTI. Você não fica impedido de realizar outras tarefas de Planning e CTI, mesmo que um trabalho de importação grande ou demorado esteja em andamento.

## Publicar em Costing Standard

O modelo de dados Costing Standard pode acomodar apenas um orçamento e uma previsão para análise. Consequentemente, somente um de cada tipo de plano pode ser enviado de Planning para Costing Standard. Use a página Publish to CT para determinar e publicar manualmente os planos apropriados na Transparência de custos.

1. Selecione um plano no menu suspenso e selecione todos os tipos de itens de linha que deseja publicar.
2. Clique no botão azul Publish (Publicar ) quando estiver pronto, e ele iniciará um trabalho de publicação.

Todos os tipos de itens de linha são selecionados por padrão.

É exibida uma janela pop-up que recomenda ir para a página Status e verificar o status do seu trabalho. No entanto, o processo Publish to CT não exige nenhuma tarefa de acompanhamento: você poderá encontrar os dados importados no CT após a conclusão do trabalho.

Você também pode retornar à página inicial do CTI para continuar com outras tarefas do CTI. Você não fica impedido de executar outras tarefas de ITP e CTI, mesmo que um trabalho de importação grande ou demorado esteja em andamento.

## Estado

Você pode acessar essa página a qualquer momento para exibir o status de cada trabalho de CTI que tenha sido tentado, programado ou concluído.

| Estado | Descrição |
| --- | --- |
| Início e fim | Os horários de início e término do trabalho correspondente. |
| Iniciado por | O e-mail do usuário que iniciou o trabalho. |
| Estado | O progresso do trabalho: QUEUE, SUCCESS, SUCCESS WITH WARNINGS ou FAIL. |
| Ações | Ações de acompanhamento que devem ser realizadas:  - Publicar dados quando os trabalhos de importação forem bem-sucedidos (por exemplo, Publicar dados de referência após a importação).  - View para localizar e fazer download de registros de erros de trabalhos com falha. |
