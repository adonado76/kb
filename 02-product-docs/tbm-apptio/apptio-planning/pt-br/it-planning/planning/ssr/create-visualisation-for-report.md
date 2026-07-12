---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Criar uma visualização para um relatório"
breadcrumb: []
source_path: "it-planning/planning/ssr/create-visualisation-for-report.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Criar uma visualização para um relatório

Conclua as etapas a seguir para criar uma visualização em Apptio BI usando dados de Planning. Você pode personalizar a visualização de várias maneiras, inclusive selecionando o tipo de visualização (gráfico de barras, gráfico de linhas e outros), filtrando dados e selecionando um período de tempo.

Para obter mais informações, consulte [Criar relatórios personalizados](../../../apptio_bi/self-service-reporting_user_guide/create-a-self-service-report.html).

## Procedimento

1. Em Enhanced Access Administration, abra Apptio BI.

   Se esta for a primeira vez que abre o site Apptio BI, você verá uma tela de introdução

   ![Apptio tela de introdução](../../../resources/images/it%20planning_images/pastedimage_22.png)
2. Selecione Criar novo relatório.
3. Selecione Add Visualization (Adicionar visualização) no canto superior direito.

   A página Add Visualization (Adicionar visualização) é aberta.
4. Na seção Fontes de dados e medidas, selecione uma fonte de dados para a visualização.

   As fontes de dados a seguir são exclusivas da ITP e correspondem a diferentes guias de despesas.

   Para visualizar os dados da guia Outras despesas, selecione a fonte de dados Planning Financial e filtre a dimensão "Line Item Type" igual ao valor "Other".

   | Origem de Dados | Ficha Despesas de ITP associadas | Subficha de despesas de ITP associadas |
   | --- | --- | --- |
   | Ativo de planejamento | Ativos | Existente, planejado |
   | Resumo financeiro do planejamento | Todos | Planning |
   | Contrato de planejamento | Contratos | Resumo financeiro do planejamento |
   | Planejamento de mão de obra | Mão de Obra | Existente, planejado |
   | Atividade trabalhista | Mão de Obra | Existente, planejado |
5. Na seção Plan Name (Nome do plano), selecione o plano a ser usado para sua visualização.

   Todos os planos ativos em Planning estão listados. Os planos arquivados ou excluídos não serão exibidos.
6. Selecione as dimensões e métricas que deseja usar.

   Para obter mais informações, consulteVisão [geral](it-planning-data-self-service-reporting.html "Apptio BI permite que os usuários criem e compartilhem seus próprios relatórios personalizados usando dados de vários aplicativos, inclusive o Planning. Com os dados de planejamento disponíveis em Apptio BI, os usuários agora podem criar um relatório personalizado que resume os dados de mão de obra, ativos, contratos e financeiros do departamento de planejamento.")
7. Selecione um tipo de visualização.
8. Selecione um intervalo de datas.

   Até 1 ano de plano pode ser exibido por vez. Planning incluem as seguintes opções, além das opções padrão do site Apptio BI :
   - Próximo ano
   - # Years Future, em que # é o número de anos no futuro para um plano com vários anos, até um máximo de 7 anos. Por exemplo, se o ano atual for 2020 e o plano começar em 2020 e durar 7 anos, o intervalo de datas incluirá "2 Years Future" (2 anos futuros) para exibir o plano 2022’s, "3 Years Future" (3 anos futuros) para exibir o plano 2023’s,.... "7 Years Future" (7 anos futuros) para exibir o plano 2027’s.
   - Observação: na fonte de dados ITP Labor, somente as opções This Month (Este mês) e Last Month (Último mês) são compatíveis com os seguintes tipos de visualização: KPI, Barra, Pizza.
9. Em Exibir por, selecione um período de tempo.

   Na fonte de dados ITP Labor, somente a opção Visualização mensal por é suportada.
10. Opcional: Selecione um filtro.

    Na fonte de dados Planning Labor, você pode usar a dimensão "Is Existing Resource" para filtrar e visualizar apenas os dados da subficha de mão de obra existente (=verdadeiro) versus planejado (=falso).
11. Opcional: Editar o nome da visualização.

    Como prática recomendada, adicione a fonte de dados como um prefixo ao nome da visualização.
12. Quando terminar, clique em Salvar relatório.

    Depois de salvar a visualização, você verá o relatório que contém a visualização. Adicione outras visualizações conforme necessário. Você também pode compartilhar o relatório com outros membros da sua organização. Para obter informações sobre compartilhamento, consulte [Gerenciar relatórios](../../../apptio_bi/self-service-reporting_user_guide/manage-self-service-reports.html).

    Nota:

    A opção Comparar com não é suportada no momento.

    Para exibir cada item de linha em Apptio BI como aparece em Planning, adicione uma coluna com um valor exclusivo à visualização (por exemplo, o nome do funcionário na fonte de dados Labor).

    O valor da mão de obra não está disponível na fonte de dados Planning Labor. Para ver o valor da mão de obra, selecione Planning Financials como a fonte de dados e, em seguida, filtre o valor do tipo de item de linha Trabalho.

## Exemplo

As informações a seguir são um exemplo de uma configuração usada para criar uma visualização de tabela usando o site Planning Financials como fonte de dados. Observe que as opções necessárias mudam de acordo com o tipo de visualização.![Exemplo de uma configuração usada para criar uma visualização de tabela usando o Planning Financials como fonte de dados](../../../resources/images/it%20planning_images/pastedimage_1.png)
