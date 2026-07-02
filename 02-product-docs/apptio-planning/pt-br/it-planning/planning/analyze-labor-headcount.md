---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Analisar o número de funcionários"
breadcrumb: []
source_path: "it-planning/planning/analyze-labor-headcount.html"
images:
  - "resources/planning_images/itp_analyze-labor-headcount.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Analisar o número de funcionários

Quando os dados de mão de obra estiverem presentes, você poderá analisar o número de funcionários por meio da página Resumo.

1. Certifique-se de que os recursos de planejamento de mão de obra estejam ativados. Consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning.").
2. No menu da seção Plan (Plano), selecione Departments (Departamentos ). Consulte [Navegar em aplicativos Apptio Planning](navigate-apptio-planning.html) .
3. No menu da subseção Plan (Plano), selecione um departamento específico ou All Departments (Todos os departamentos ).
4. No menu Componente, selecione Planning. Consulte [Navegar nos aplicativos Apptio Planning](navigate-apptio-planning.html) . > Resumo.
5. Selecione a guia Headcount.
6. Opcionalmente, aplique um layout diferente à página selecionando uma opção de layout no canto superior direito.

Diferentemente da análise financeira de OpEx ou CapEx valores financeiros, a análise do número de funcionários usa o número de funcionários como unidade de medida em vez de valores financeiros:

![imagem](../../../../../03-media/apptio-planning/resources/planning_images/itp_analyze-labor-headcount.png)

Observação: A variação codificada por cores em relação às metas de mão de obra aparece somente se as metas de mão de obra estiverem definidas. Consulte [Definir metas de número de funcionários](set-labor-headcount.html).

## Comparar o número de funcionários

Agora você pode comparar os dados trabalhistas entre dois planos.

1. Garanta a opção Ativar experiência da página de novas despesas (Beta). Consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning.").
2. Navegue até a guia Despesas > Trabalho. Ative o botão de alternância Nova visualização.
3. Expanda o ícone ![imagem](../../resources/images/it%20planning_images/three-dots_31x23.png)e selecione a opção Compare Shortcuts (Comparar atalhos ). Consulte [Comparar atalhos](compare-versions-plans.html).

   ![imagem](../../resources/images/it%20planning_images/compare-shortcuts.png)
4. Na janela pop-up Manage Compare Shortcuts (Gerenciar atalhos de comparação), selecione os planos que você deseja comparar e clique no botão Compare. A página a seguir é exibida.

   ![imagem](../../resources/images/it%20planning_images/new-view.png)

   ![imagem](../../resources/images/it%20planning_images/vendor-location-labor.png)

   Observação: o agrupamento padrão é por objeto de custo. Mas se você quiser analisar a variação por outras dimensões, poderá atualizar a exibição de tabela adicionando mais grupos de colunas. Na captura de tela acima, o agrupamento de colunas padrão foi atualizado com a adição do grupo de colunas Fornecedor e Local, de modo que os usuários possam detalhar a exibição de colunas agrupadas para entender a variação do número de funcionários por fornecedor e local.
5. Clique em + Add Comparison (Adicionar comparação ) para ver os planos de trabalho selecionados na etapa 3 acima. Se vários anos de dados estiverem disponíveis para a comparação, o usuário deverá selecionar um ano de cada vez para a comparação.

   ![imagem](../../resources/images/it%20planning_images/select-labor-plan.png)

   A comparação de planos atualiza automaticamente o layout para Group by Cost Object.
6. Escolha o plano apropriado e selecione Compare (Comparar ). Os usuários podem usar essa visualização para comparar o número de funcionários de diferentes planos.

   ![imagem](../../resources/images/it%20planning_images/compare-lp.png)
7. Para adicionar planos adicionais para comparação, selecione qualquer coluna mensal e, em seguida, escolha a opção Adicionar comparação.

   ![imagem](../../resources/images/it%20planning_images/add-monthly-comp_584x263.png)

   ![imagem](../../resources/images/it%20planning_images/monthly-add-comp_471x273.png)
8. Escolha os valores apropriados e clique em Compare (Comparar ). O plano adicional é adicionado ao mês selecionado para comparação, conforme mostrado.

   ![imagem](../../resources/images/it%20planning_images/compare-monthly.png)
9. Para adicionar ou remover qualquer plano da comparação, selecione a coluna em questão e escolha Remover comparação.

   ![imagem](../../resources/images/it%20planning_images/remove-comparison.png)

Você pode adicionar e remover comparações várias vezes, para diferentes planos e métodos de alinhamento. Quando não houver valores para um ano fiscal correspondente, será exibida uma mensagem de erro.
