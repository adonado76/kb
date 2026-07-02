---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "pt-br"
doc_type: "apptio-cost-management"
title: "Consequências"
breadcrumb:
  - "Costing Essentials"
  - "Ambiente de Trabalho"
source_path: "apptio-cost-management/workbench/fallout.html"
images:
  - "resources/images/studio_images/fall-labor.png"
  - "resources/images/studio_images/fall-oth_958x601.png"
  - "resources/images/studio_images/fall-sol.png"
  - "resources/images/studio_images/fall-vendor.png"
  - "resources/images/studio_images/fallout-1_1202x762.png"
  - "resources/images/studio_images/fallout-2_1017x447.png"
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# Consequências

O painel de fallout destaca prontamente os custos - tanto OpEx quanto CapEx - em seu modelo Costing Essentials que foram totalmente alocados ou não alocados (fallout).

## KPIs

Fornece uma visão geral do custo total em cada nível do modelo. Um modelo totalmente alocado mostrará o mesmo custo total em cada KPI.

Exemplo:

- Fonte de custos - Total de despesas acumuladas no ano = $100
- Soluções - Total de despesas até o momento = US$ 80
- Unidade de negócios - Total de despesas acumuladas até a data = US$ 50

## Fonte de custos

Use esse relatório para visualizar a distribuição OpEx (mão de obra, fornecedores, outros) por período e garantir que suas transações GL correspondam ao objeto de origem de custo no ACM.

![imagem](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/fallout-1_1202x762.png)

De acordo com o projeto, há uma alocação que envia todo o custo restante para Outros - ou seja, o custo que não foi alocado para Fornecedor ou Mão de obra -. Portanto, não há nenhuma consequência da origem do custo e, para garantir que o custo que flui por meio de Outros seja legítimo, exibimos o custo alocado incorretamente em uma tabela abaixo do gráfico. "Alocado incorretamente" significa que esse custo enviado para Outro deveria ter sido enviado para Fornecedor ou Mão de obra, mas foi reprovado devido a uma Relação não correspondente.

Exemplos:

- Em um determinado GL Real, o Pool de custos é Trabalho interno para a conta, mas não conseguimos encontrar nenhum HC de trabalho associado ao mesmo centro de custo nos dados de trabalho.
- Em um determinado GL Actuals, um ID de fornecedor foi mapeado, mas não conseguimos encontrar esse ID de fornecedor na lista mestre de fornecedores (o que pode ser o caso se o fornecedor tiver sido removido da lista mestre de fornecedores usada para o mês selecionado)

![imagem](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/fallout-2_1017x447.png)

## Mão de Obra

Use esse relatório para visualizar todos os custos de mão de obra não alocados que devem ser alocados para as soluções. Para corrigir qualquer problema, o usuário deve utilizar as tabelas de "Mapeamento de mão de obra" para alocar um recurso de mão de obra a ofertas de soluções individuais.

![imagem](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/fall-labor.png)

## Fornecedores

Use esse relatório para visualizar todos os custos de fornecedores não alocados que devem ser alocados para as soluções. Para corrigir qualquer problema, o usuário deve utilizar as tabelas "Vendor Mapping" (Mapeamento de fornecedores).

![imagem](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/fall-vendor.png)

Observação: quando as colunas de pesquisa [In Catalogue Type], [In Catalogue Category], [In Catalogue Offering ID] são destacadas em vermelho, isso significa que os dados mapeados no Workbench não são mais encontrados no Catálogo de Serviços. Isso pode ocorrer quando o Catálogo de serviços é atualizado sem atualizar os mapeamentos de recursos para alinhá-los ao novo Catálogo de serviços.

## Soluções

Use esse relatório para visualizar os custos da solução não alocados que devem ser alocados para as organizações (consumidores). Para corrigir qualquer falha, o usuário deve utilizar as tabelas "Solution Mapping" ou "Organization Mappings" conforme indicado na coluna "Fallout Fix Action".

![imagem](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/fall-sol.png)

## Outras

O custo de Outros está sempre sendo alocado, pois funciona como alocação de custo "Enviar restante". O instantâneo abaixo indica os detalhes desse custo alocado.

![imagem](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/fall-oth_958x601.png)
