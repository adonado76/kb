---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Sobre planejamento e previsão de orçamento"
breadcrumb: []
source_path: "it-planning/planning/budget-planning-forecasting.html"
images:
  - "resources/images/it_planning_images/icon_video.jpg"
  - "resources/planning_images/itp_diagram_budget-plan.png"
  - "resources/planning_images/itp_diagram_budget-workflow.png"
  - "resources/planning_images/itp_diagram_forecast-workflow.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Sobre planejamento e previsão de orçamento

Depois que o administrador tiver configurado o aplicativo Apptio Planning , você poderá começar a prever e planejar seu orçamento. Consulte [Configurar e administrar os aplicativos Apptio Planning](configure-administer-apptio.dita "(Abre em uma nova guia ou janela)") .

![imagem](../../../../../03-media/apptio-planning/resources/images/it_planning_images/icon_video.jpg)

Assista a estes vídeos do site Apptio Education Services:

- [Fluxo de trabalho de planejamento de TI 2.0](https://community.ibm.com/community/user/viewdocument/it-planning-20-workflow-2-min "(Abre em uma nova guia ou janela)")
- [Entendendo as hierarquias de dados no ITP](https://community.ibm.com/community/user/viewdocument/understanding-data-hierarchies-in-i "(Abre em uma nova guia ou janela)")

## Como o planejamento e a previsão orçamentária funcionam em Apptio

Para ter sucesso com os aplicativos Apptio Planning , é necessário ter uma visão clara das tarefas dos usuários e dos fluxos de processos. As imagens a seguir mostram exemplos de tarefas (colunas) e funções de usuário (linhas) para tarefas de planejamento orçamentário em aplicativos Apptio Planning . As imagens mostram exemplos de um processo de planejamento ou previsão orçamentária com três níveis. Você pode adaptar esse processo para atender às suas necessidades organizacionais. Por exemplo, sua organização pode não ter um proprietário de orçamento, um único proprietário de orçamento ou vários níveis de proprietários de orçamento. Da mesma forma, sua organização pode ter um ou vários usuários que aprovam planos.

Nos exemplos a seguir, há apenas um proprietário do processo orçamentário designado, mas provavelmente há vários proprietários do orçamento. Os proprietários de um código pai em dados de referência de departamentos ou de dados de referência de projetos, serviços ou unidades de negócios habilitados são considerados proprietários de orçamento de grupo. Consulte [Gerenciar dados de referência financeira](manage-financial-dimensions.html "As tarefas abaixo só podem ser executadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.").

Aqui está um fluxo de trabalho de planejamento orçamentário:

![imagem](../../../../../03-media/apptio-planning/resources/planning_images/itp_diagram_budget-workflow.png)

Aqui está um fluxo de trabalho de planejamento de previsão:

![imagem](../../../../../03-media/apptio-planning/resources/planning_images/itp_diagram_forecast-workflow.png)

- Os proprietários do processo orçamentário são responsáveis por criar o plano que os proprietários do orçamento usarão para inserir dados e controlar seus gastos. Os proprietários do processo orçamentário também são responsáveis por finalizar e fechar os planos.
- Os proprietários do orçamento são responsáveis por inserir informações orçamentárias para seus objetos de custo. Isso pode se aplicar a proprietários individuais ou em grupo de departamentos, projetos, serviços ou unidades de negócios.
- Os aprovadores são atribuídos como pessoas designadas que podem aprovar ou rejeitar os planos enviados. Os aprovadores não estão vinculados à hierarquia de credenciais, mas à hierarquia de objetos de custo (consulte [os dados de referência Gerenciar permissões de objetos de custo](manage-cost-object.html "As permissões de objetos de custo determinam quais usuários podem visualizar, editar, enviar ou aprovar planos em nível de departamento (objetos de custo). Cada departamento pode ter um ou mais usuários atribuídos com permissões de nível de edição e, para aprovações multinível, permissões de nível de aprovação.") ). Apptio Planning os aplicativos suportam até cinco níveis de aprovadores.

## Previsão

Uma previsão geralmente consiste em:

- Um plano ou previsão orçamentária anterior para servir de base para a nova previsão.
- Dados reais mensais que foram carregados em seu aplicativo Apptio Planning (consulte [Importar e publicar dados reais](import-publish-actuals.html) ). Os dados reais históricos não são editáveis. Se a nova previsão incluir valores reais, mas nenhum valor planejado futuro, isso representa despesas não planejadas.

Cada previsão criada abrange todo o ano do plano (geralmente o ano fiscal). Por exemplo, o ano de seu plano é um ano civil de janeiro a dezembro. Você criou anteriormente um plano orçamentário anual e fez o upload dos dados reais acumulados no ano de janeiro a março. Agora, você deseja criar uma previsão. Na nova previsão, os dados reais históricos de janeiro a março são preenchidos e os valores dos itens de linha de abril a dezembro são copiados da linha de base do Plano Orçamentário:

![imagem](../../../../../03-media/apptio-planning/resources/planning_images/itp_diagram_budget-plan.png)

Depois de atualizar e finalizar a nova previsão, você pode usá-la como linha de base para uma previsão subsequente. Se você usar o plano orçamentário como linha de base para a previsão inicial do ano, poderá usar cada previsão trimestral como linha de base para as previsões subsequentes. Por exemplo, você pode usar o Plano Orçamentário como linha de base para a previsão Q1, depois usar a previsão Q1 como linha de base para a previsão Q2, a previsão Q2 como linha de base para a previsão Q3 e assim por diante. A mesma lógica de sequenciamento se aplica a períodos de previsão mensais ou outros.

## Tarefas de planejamento de orçamento e previsão

- [Criar um plano ou previsão](create-budget-plan.html)
- [Gerenciar tabelas de itens de linha](manage-line-item.html)
- [Insira os detalhes financeiros e ajuste os valores da linha de base](enter-financial-details.html)
- [Definir metas financeiras](set-financial-targets.html)
- [Planeje para vários anos](plan-multiple-years.html "Use os recursos de planejamento plurianual para planejar e acompanhar as finanças de TI em um horizonte de tempo contínuo e plurianual. Você pode dar suporte a planos de longo prazo e previsões contínuas para além dos limites do ano fiscal.")
- [Abrir um plano ou uma previsão](open-plan-forecast.html "Após criar um plano ou previsão orçamentária, opcionalmente ajuste os valores de linha de base, defina as metas e abra o plano para que os proprietários do orçamento possam editar os itens de linha. Os proprietários de orçamentos não podem ver um plano quando ele está no estado Novo. Quando você abre um plano, uma notificação por e-mail é enviada aos proprietários do orçamento e a todos os usuários que têm a permissão Edit & Submit associada aos objetos de custo desse plano.")
- [Importar e publicar dados reais](import-publish-actuals.html)
- [Analisar um plano ou previsão](analyze-plan-forecast.html). Use o Costing Standard [Relatório de revisão financeira](../reports-itfmf-ctv104/itfmf-ct_financialreview107.dita "(Abre em uma nova guia ou janela)") para analisar gastos acumulados no ano, gastos anuais projetados e variação orçamentária por pool de custos. Use o Costing Standard [Relatórios de revisão de mão de obra](../reports-itfmf-ctv104/itfmf-ct_itplaborreview104.html "aplica-se a: Planejamento e cálculo de custos padrão no TBM Studio 12.3 e posterior, com o Template v104 e posterior") para visualizar custos de mão de obra por pessoal interno e externo por Centro de Custo. Veja os principais gastos com mão de obra por função e divisão interna e externa.
- [Comparar versões ou planos](compare-versions-plans.html)
- [Revisar, aprovar ou devolver planos ou objetos de custo](review-approve-return.html)
- [Arquivar, restaurar ou excluir planos](manage-plans.html "Com a página Planos, você pode gerenciar seus planos de forma fácil e intuitiva.")
