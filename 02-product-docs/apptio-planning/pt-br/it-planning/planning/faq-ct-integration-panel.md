---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "PERGUNTAS FREQUENTES: Painel de integração de transparência de custos"
breadcrumb:
  - "Planning"
  - "Solução de problemas e perguntas frequentes"
source_path: "it-planning/planning/faq-ct-integration-panel.html"
images:
  - "resources/planning_images/faq-ct-integration-panel-1_700x182.png"
  - "resources/planning_images/faq-ct-integration-panel-2_700x471.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# PERGUNTAS FREQUENTES: Painel de integração de transparência de custos

Esta lista de perguntas frequentes sobre como o painel Cost Transparency Integration (CTI), introduzido na versão de planejamento 2.78. O painel CTI é um espaço independente em que os usuários administradores podem executar todas as tarefas do Cost Transparency Integration em um único painel de controle. O novo painel oferece gerenciamento centralizado e importação e exportação com um clique com Costing Standard.

Nesta FAQ:

[P. Como faço para ativar a nova funcionalidade?](#FAQCostTransparencyIntegrationPanel__Q.)

[P. Que tarefas posso realizar por meio do CTI Panel?](#FAQCostTransparencyIntegrationPanel__Q.2)

[P. Quais funções/permissões são necessárias para acessar o novo painel?](#FAQCostTransparencyIntegrationPanel__Q.3)

[P. Posso importar dados reais de mais de um mês de cada vez?](#FAQCostTransparencyIntegrationPanel__Q.4)

[P. Posso executar outras tarefas do ITP quando meus trabalhos de CTI estiverem na fila ou em execução?](#FAQCostTransparencyIntegrationPanel__Q.5)

[P. Posso ver um status detalhado do meu trabalho?](#FAQCostTransparencyIntegrationPanel__Q.6)

[P. Existe uma ordem de operações ao importar dados de referência em massa?](#FAQCostTransparencyIntegrationPanel__Q.7)

[P. Se um dos conjuntos de dados de referência não for carregado, o trabalho inteiro falhará?](#FAQCostTransparencyIntegrationPanel__Q.8)

[P. Onde posso publicar meus dados de referência?](#FAQCostTransparencyIntegrationPanel__Q.9)

[P. Onde posso verificar se o que carreguei está correto e é o que eu esperava?](#FAQCostTransparencyIntegrationPanel__Q.10)

[P. O novo painel de CTI substitui alguma funcionalidade e processo de CTI existentes?](#FAQCostTransparencyIntegrationPanel__Q.11)

[P. A página CTI Status lista apenas os trabalhos agendados usando o painel Cost Transparency Integration ?](#FAQCostTransparencyIntegrationPanel__Q.12)

## P. Como faço para ativar a nova funcionalidade?

R. A nova funcionalidade está ativada por padrão. Para acessar a funcionalidade aprimorada de CTI, no menu Settings (Configurações ), clique em Cost
Transparency Integration.

## P. Que tarefas posso realizar por meio do CTI Panel?

R. As tarefas a seguir podem ser executadas por meio do CTI Panel:

- Configurar as definições de integração do CT.
- Importar dados reais do CT.
- Importar dados de referência do CT e publicá-los no plano.
- Publicar dados do plano do ITP para o CT.
- Ver o status de todos os empregos da CTI.

## P. Quais funções/permissões são necessárias para acessar o novo painel?

R. Administradores. Nenhuma alteração é feita com relação às permissões das funções de CTI existentes.

## P. Posso importar dados reais de mais de um mês de cada vez?

R. Sim. Use o seletor de calendário para especificar um período. Selecione os meses inicial e final. Para selecionar apenas um mês, selecione os meses inicial e final para que sejam os mesmos.

![imagem](../../../../../03-media/apptio-planning/resources/planning_images/faq-ct-integration-panel-1_700x182.png)

## P. Posso executar outras tarefas do ITP quando meus trabalhos de CTI estiverem na fila ou em execução?

R. Sim. Você não é impedido de executar nenhuma tarefa relacionada ao CTI ou ao ITP quando um trabalho está na fila ou em execução. Você pode acessar a página Status a qualquer momento para visualizar o status de cada trabalho de CTI que tenha sido tentado, agendado ou concluído.

## P. Posso ver um status detalhado do meu trabalho?

R. Sim. Na página Status, clique no ícone de seta para expandir. Você pode visualizar a lista de subtarefas.

Você pode acessar essa página a qualquer momento para exibir o status dos trabalhos de CTI e suas subtarefas que foram tentadas, agendadas ou concluídas.

Exibimos apenas os 100 trabalhos mais recentes com menos de 31 dias.

![imagem](../../../../../03-media/apptio-planning/resources/planning_images/faq-ct-integration-panel-2_700x471.png)

## P. Existe uma ordem de operações ao importar dados de referência em massa?

R. Para obter informações sobre a ordem recomendada para a importação de dados de referência, consulte: [Diagrama de dependências da tabela de referência](https://community.ibm.com/community/user/viewdocument/reference-table-dependencies-diagra?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(Abre em uma nova guia ou janela)").

## P. Se um dos conjuntos de dados de referência não for carregado, o trabalho inteiro falhará?

R. Nº Mesmo que uma das subtarefas não seja carregada, o trabalho CTI\_IMPORT\_REF\_DATA\_IMPORT ainda será aprovado com avisos. É exibida uma mensagem de status de Aviso. Para acessar os registros de erros das subtarefas que falharam, expanda o trabalho e, em Ações, clique em Exibir registro.

## P. Onde posso publicar meus dados de referência?

R. Para publicar dados de referência, na página Status, em Ações, clique em Publicar. O botão Publish (Publicar ) não será exibido se o status do trabalho de importação for Failed (Falha ). Ele será exibido apenas para os estados de Sucesso e Aviso. Depois que os dados de referência são publicados, o texto do botão muda para Publicado e o botão é desativado.

AVISO

Quando um trabalho com status Warning é publicado, somente as tarefas do trabalho que foram bem-sucedidas são publicadas. Os trabalhos com falha são ignorados e não são publicados.

## P. Onde posso verificar se o que carreguei está correto e é o que eu esperava?

R. Você pode verificar o upload antes de publicar. Navegue até a página de dados de referência e clique no conjunto de dados relevante.

## P. O novo painel de CTI substitui alguma funcionalidade e processo de CTI existentes?

R. Nº Esse painel CTI aprimorado é usado juntamente com a funcionalidade existente.

## P. A página CTI Status lista apenas os trabalhos agendados usando o painel Cost Transparency Integration ?

R. Sim. As atividades de CTI realizadas fora do novo painel de CTI não são rastreadas e não serão listadas na página Status de CTI.

Para obter mais informações, consulte: [Cost Transparency Integration Painel](cti_panel.html "O painel atualizado da Integração da Transparência de Custos (CTI), introduzido na versão de planejamento 2.78, é um espaço independente em que os usuários administradores podem executar todas as tarefas da Integração da Transparência de Custos em um único painel de controle. O novo painel oferece gerenciamento centralizado e importação e exportação com um clique, com transparência de custos.").
