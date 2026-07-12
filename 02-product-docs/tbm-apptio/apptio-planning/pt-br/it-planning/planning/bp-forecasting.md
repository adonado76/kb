---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Práticas recomendadas: Previsão"
breadcrumb: []
source_path: "it-planning/planning/bp-forecasting.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Práticas recomendadas: Previsão

Em uma previsão, os meses históricos são substituídos por reais para fornecer uma visão única e híbrida do desempenho até o momento e uma perspectiva para o restante do ano. Este documento aborda as práticas recomendadas de previsão, incluindo exemplos e tarefas específicas para a criação de previsões.

Para obter mais informações sobre o amplo fluxo de trabalho de quem faz o quê da previsão nos aplicativos Apptio Planning , consulte [Planejamento e previsão de orçamento](budget-planning-forecasting.html).

## Exemplo: Criar a primeira previsão de 2018

Neste exemplo, assumimos uma cadência de previsão trimestral e um ano fiscal alinhado ao ano civil.

Anteriormente, um orçamento finalizado denominado FY2018 Budget foi criado para FY18. Agora, estamos em abril de 2018, portanto, é hora de criar a primeira previsão trimestral do site FY2018. Esta será a Q2 Forecast.Este exemplo inclui as seguintes tarefas:

- [Tarefa 1: Validar dados reais](#best_practices_forecasting__Validate-actuals)
- [Tarefa 2 (opcional): Atualizar metas no orçamento de linha de base](#best_practices_forecasting__Update-baseline-budget)
- [Tarefa 3: Criar um plano de previsão](#best_practices_forecasting__forecast-plan)
- [Tarefa 4: Ativar recursos do plano para a previsão](#best_practices_forecasting__features-4-forecast)
- [Tarefa 5 (opcional): Atualizar mão de obra, contratos e ativos](#best_practices_forecasting__labor-contracts-assets)
- [Tarefa 6: Permitir que os proprietários do orçamento façam atualizações](#best_practices_forecasting__budget-owners-updates)

## Tarefa 1: Validar dados reais

No Gerenciamento de despesas, certifique-se de que os valores reais sejam carregados corretamente em janeiro de 2018, fevereiro de 2018 e março de 2018. Para obter mais informações, consulte [Importar e publicar dados reais](import-publish-actuals.html).

## Tarefa 2 (opcional): Atualizar metas no orçamento de linha de base

As metas permitem armazenar uma meta de final de ano OpEx, CapEx, e de número de funcionários para cada departamento. KPIs e gráficos em todo o aplicativo fornecem comparações convenientes com as metas. Como as metas são copiadas para novos planos, o armazenamento dos valores orçamentários aprovados como metas no orçamento de linha de base oferece uma maneira fácil de transportá-las para planos de previsão futuros. Consulte [Definir metas financeiras](set-financial-targets.html).

## Tarefa 3: Criar um plano de previsão

Ao criar uma previsão, observe o seguinte e consulte também [Criar um plano ou previsão](create-budget-plan.html) :

1. `Forecast Start Period` - Especifica o primeiro mês da previsão que não contém dados reais. Como o Q2 Forecast tem dados reais para janeiro, fevereiro e março, nesse caso, defina o período inicial da previsão para abril.
2. `Baseline` - Especifica o plano a partir do qual copiar os dados planejados. Todos os dados (por exemplo, contratos, ativos, mão de obra, metas, outras despesas, etc.), exceto os valores financeiros dos meses reais, serão copiados do plano especificado para o novo plano. Como esta é a primeira previsão do FY2018, use o Orçamento FY2018 como linha de base.
3. `Summarize actuals down to the following dimensions and/or attributes` - Somente as colunas marcadas serão transferidas do Gerenciamento de despesas para a nova previsão. Recomenda-se que você verifique a maioria ou todos esses valores para maximizar a granularidade dos dados reais na nova previsão. O exemplo a seguir mostra como a seleção de várias opções para resumir afeta a granularidade dos dados reais na nova previsão:
4. `Rolling forecasts` - Se for usada uma previsão contínua, criar um plano de dois ou três anos para garantir que a previsão contenha de 4 a 6 trimestres futuros.
5. `Reference data usage` - A nova previsão usará a última versão publicada de todas as dimensões de dados de referência, portanto:
   - Os dados reais inseridos na previsão usarão os dados de referência mais recentes, independentemente da versão que estiver sendo usada no Gerenciamento de despesas.
   - Os dados do plano extraídos do plano de linha de base para a previsão usarão os dados de referência mais recentes, independentemente da versão no plano de linha de base.

## Tarefa 4: Ativar recursos do plano para a previsão

Configure os Variance Drivers na previsão com as seguintes opções:

- `Compare Plan` - O orçamento original, FY2018 Budget
- `Comparison Period` - Como essa é a primeira previsão do ano, escolha Q1 FY18

Ao editar itens de linha, use o recurso Compare Shortcuts para adicionar uma comparação ao FY2018 Budget para que os usuários possam ver uma comparação com o orçamento original.

## Tarefa 5 (opcional): Atualizar mão de obra, contratos e ativos

Pode ser mais eficiente fazer algumas atualizações de previsão de base ampla antes de abrir o plano para todos os proprietários de orçamento.

1. Atualizações trabalhistas
   - `Updates for new hires:`
     1. Adicione as novas contratações na aba Despesas > Mão de obra > Existente.
     2. Remova o número de funcionários em aberto preenchido da guia Despesas > Trabalho > Planejado.
   - `Updates for delayed hires` - Atualize a data de início do efetivo em aberto na guia Despesas > Trabalho > Planejado.
   - `Updates for canceled hiring` - Atualize a quantidade de funcionários em aberto para 0 na guia Despesas > Trabalho > Planejado.
   - `Updates for employee departures` - Atualize a Data de término do funcionário para a data de rescisão na guia Despesas > Trabalho > Existente.
2. Atualizações de ativos
   - `Updates for new purchases:`
     1. Adicione a compra real à guia Despesas > Ativos > Existentes.
     2. Remova a compra planejada da guia Despesas > Ativos > Planejado.
   - `Updates for delayed purchases:`
     1. Atualize a data de compra planejada (e a data de entrada em serviço, se apropriado) com a data futura na guia Despesas > Ativos > Existentes.
   - `Updates for canceled purchases` - Atualize a compra planejada `Quantity` para 0 na guia Despesas > Ativos > Existentes.
3. Atualizações de contratos
   - `Updates for delayed contracts:`
     1. Se a data de início do contrato tiver sido atrasada, atualize a Data de início do contrato planejada na guia Despesas > Contratos.
     2. Se o contrato começou no prazo, mas a amortização/faturamento foi adiada, atualize o Offset de início de amortização do contrato existente na guia Despesas > Contratos.
   - `Updates for canceled contracts` - Atualize o valor do contrato planejado para 0 na guia Despesas > Contratos.

Os proprietários do orçamento também podem fazer qualquer uma dessas atualizações quando o plano é aberto.

## Tarefa 6: Permitir que os proprietários do orçamento façam atualizações

Depois de abrir a previsão, os proprietários do orçamento podem fazer atualizações nos períodos futuros do plano, mas não nos períodos reais, que são somente leitura.

Use o recurso Compare com o orçamento original do site FY19 para garantir o alinhamento com o orçamento de cada departamento, conta ou pool de custos e assim por diante, ao revisar e aprovar as alterações dos usuários.

Observação: o recurso Headcount Compare está disponível no momento apenas na página Summary (Resumo ), guia Headcount.

## Criar previsões subsequentes para o ano

Eventualmente, chegará o momento de criar a segunda maior previsão trimestral do ano. Os dados reais serão carregados para abril, maio e junho, permitindo assim a criação da previsão Q3.

As tarefas são as mesmas da primeira previsão do ano acima, exceto pela escolha do plano de linha de base.

Para garantir que você inclua as atualizações feitas na Previsão Q2, use a Previsão Q2 como a linha de base para a Previsão Q3. Isso significa que todos os dados (exceto os valores financeiros reais, que são carregados do Gerenciamento de despesas ) serão copiados da Previsão Q2 para a nova Previsão Q3.

## Estratégias de análise de desvio orçamentário

Há duas abordagens comuns (e diversas variações) para realizar a análise de variância em previsões ao longo do ano.

1. Análise de variação em relação à previsão anterior
   - `Compare plan` - Q2 Previsão.
   - `Compare period` - Q2 uma vez que esses novos dados reais estão sendo comparados com as atualizações de previsão que foram feitas na previsão Q2.
   - `Evaluate year-end totals vs. the baseline budget` - Especifique um atalho de comparação do orçamento FY2018.
2. Análise de variação em relação ao orçamento original
   - `Compare plan` - FY2018 Orçamento.
   - `Compare period` - YTD ( Q1-Q2 ) porque o efeito cumulativo de todos os valores reais está sendo comparado ao orçamento original.
   - `Evaluate year-end totals vs. the baseline budget` - Especifique um atalho de comparação do orçamento FY2018.

## Realizar revisões mensais

Muitas organizações realizam previsões com frequência mensal. As organizações que realizam previsões com frequência trimestral podem se beneficiar de uma revisão mensal assim que os dados reais estiverem disponíveis. Você pode fazer isso seguindo as etapas anteriores de criação de previsão, pulando tarefas conforme apropriado e não abrindo o plano.
