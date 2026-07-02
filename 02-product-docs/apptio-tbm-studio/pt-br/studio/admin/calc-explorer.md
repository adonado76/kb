---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Explorador de cálculos"
breadcrumb: []
source_path: "studio/admin/calc-explorer.html"
images:
  - "resources/images/studio_images/ce-2.png"
  - "resources/images/studio_images/ce-3.png"
  - "resources/images/studio_images/ce-3143_1362x734.png"
  - "resources/images/studio_images/ce-4.png"
  - "resources/images/studio_images/ce-5.png"
  - "resources/images/studio_images/ce-6.png"
  - "resources/images/studio_images/ce-7.png"
  - "resources/images/studio_images/ce-9.png"
  - "resources/images/studio_images/ce-new.png"
  - "resources/images/studio_images/drills-down.png"
  - "resources/images/studio_images/full-data-path.png"
  - "resources/images/studio_images/large-component.png"
  - "resources/images/studio_images/metrics.png"
  - "resources/images/studio_images/partial-build.png"
  - "resources/images/studio_images/r-notes/calc-expl-build.png"
  - "resources/images/studio_images/secondary-metrics.png"
  - "resources/images/studio_images/time-periods.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Explorador de cálculos

## Visão geral

O Calc Explorer permite que os administradores obtenham informações sobre os processos de cálculo e analisem o desempenho de compilações longas. Ele estabelece as bases para futuros aprimoramentos na análise de configuração e desempenho. O Calc Explorer só captura itens que levam mais de 10 segundos para serem calculados. Por exemplo, você pode navegar para um relatório e depois para um período dentro do relatório, mas não encontra nenhum componente listado. Isso ocorre porque, para essa compilação, relatório e período de tempo, nenhum componente do relatório levou mais de 10 segundos para ser calculado. O Calc Explorer também mostra compilações específicas do Tronco ou de uma ramificação, separadamente. O usuário pode alternar entre o Tronco e qualquer Filial ativa para visualizar as compilações desejadas, em vez de percorrer a enorme lista. O "quilate" será exibido somente se houver vários cálculos da mesma construção.

A partir da versão 12.11.4, o Calc Explorer está disponível para todos os administradores por padrão (GA).

## Navegação

Para acessar o Calc Explorer, navegue até a guia Build na faixa de opções do site TBM Studio e selecione Calc Explorer.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/r-notes/calc-expl-build.png)

Isso abre um novo documento que exibe uma lista de compilações para análise.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ce-new.png)

## Definições

| Campo | Descrição |
| --- | --- |
| Construir | Um ponto específico na progressão de Check Ins que pode ser calculado para exibição no Flagship. |
| Calc | Um cálculo de uma construção específica. |
| Entidade | Um componente de um projeto (por exemplo, transformações, métricas, relatórios). |
| Tipo de cálculo | Uma descrição do número de entidades calculadas em comparação com todo o projeto.  - **Todos** - Um cálculo que requer que todas as entidades sejam totalmente calculadas. Exemplo:   - Uma compilação que é acionada após a limpeza ou atualização do cache.   - Uma alteração de material é registrada, como uma configuração de tempo de projeto em que períodos de tempo adicionais são adicionados. - **Parcial** - Um cálculo que requer o cálculo de entidades que são dependentes do conjunto de alterações. Exemplo: Uma construção que é acionada após um upload de dados ou uma alteração de configuração. - **None** - Um cálculo que não exige que nenhuma entidade seja calculada. Exemplo: Uma alteração não material é feita no projeto, como a desativação de um relatório. |
| Consultar | A menor unidade de um cálculo, normalmente uma entidade em um período de tempo específico. |
| Duração da construção | Tempo gasto pela compilação - em hh:mm:ss e em minutos. Você pode pesquisar a maior ou a menor construção especificando o intervalo, como <5, >70 e assim por diante. |
| Máximo de períodos de tempo | Mostra o número máximo de períodos de tempo para a compilação. |
| Número de consultas | Mostra todas as consultas em uma compilação, em forma de tabela. Você pode pesquisar e classificar entidades específicas. A lista de períodos de tempo calculados também pode ser exibida. |
| Conjunto de modificações | Quais alterações de projeto foram feitas desde a compilação anterior. |
| Alterações | Quais verificações foram feitas desde a compilação anterior. |
| Esforço de cálculo | Uma medida dos recursos necessários para concluir uma determinada consulta, expressa em um número. Por exemplo, 3.2M em vez de 3.200.000. |
| Transformar | Uma tabela com todas as suas etapas de transformação associadas, normalmente baseada em uma fonte de dados brutos. |
| Número de colunas | O número de colunas na etapa de saída de uma transformação. Por exemplo, 2.50L em vez de 2.50.000. |
| Número de linhas | O número de linhas na etapa de saída de uma transformação. Por exemplo, 2.50L em vez de 2.50.000. |
| Reportar | Relatório que contém uma coleção de KPIs, gráficos, quadros e tabelas. |
| Componente do relatório | Um único KPI, gráfico, diagrama ou tabela que faz parte do relatório. |

## Interação

Clicar em uma compilação no Calc Explorer exibe um resumo da compilação, incluindo várias entidades com base no escopo do cálculo.

## Construção parcial

Exibe entidades relevantes para o cálculo parcial.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/partial-build.png)

## Todas as construções

Apresenta um diagrama Sankey começando no Nível 1, mostrando entidades dimensionadas e classificadas por esforço de cálculo. Faça uma busca detalhada em cada entidade para ver os componentes de cálculo detalhados e as especificações da entidade.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ce-2.png)

Observação: somente as compilações criadas após a ativação do recurso Calc Explorer estarão acessíveis; o histórico anterior não está disponível. Isso inclui clientes que tiveram acesso anterior por meio da versão beta.

## Navegação Sankey

## Relatórios

Clique na entidade Relatório para detalhar o primeiro nível de informações, onde os 10 principais relatórios são mostrados, com os relatórios restantes consolidados em um único fluxo. O tamanho de cada fluxo é baseado no esforço de cálculo e é classificado em ordem decrescente. Passar o mouse sobre o nome de um relatório exibe o esforço de cálculo para esse relatório específico, incluindo % do total e % do pai.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ce-3.png)

Clique com o botão direito do mouse no relatório para abrir o documento (para o período selecionado) ou ver o caminho completo dos dados.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/full-data-path.png)

Filtre relatórios específicos por nome, inserindo um termo de pesquisa na caixa Pesquisar última camada. Navegue pela lista completa de relatórios usando as setas para a esquerda/direita em torno do recurso de paginação Mostrando 1-10 de X localizado abaixo da caixa Pesquisar.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ce-9.png)

O segundo nível de detalhamento mostra os dez principais períodos de tempo por esforço de cálculo, com o restante consolidado em um único fluxo. Aqui, novamente, você pode clicar com o botão direito do mouse no período de tempo para abrir o documento ou ver o caminho completo dos dados.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/time-periods.png)

A pesquisa de terceiro nível exibe os componentes do relatório que exigem mais cálculos. Ao passar o mouse sobre o componente, você verá insights detalhados sobre o consumo do tempo máximo de cálculo, tanto em relação ao relatório pai quanto ao tempo agregado de todas as entidades.

Observação: Somente os relatórios têm um detalhamento além do nível de período de tempo

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/large-component.png)

Você pode fazer o seguinte para encontrar o local exato de um componente de relatório:

1. Clique com o botão direito do mouse no componente do relatório no Calc Explorer.
2. Selecione "mostrar documento".
3. Quando o relatório for aberto, o componente do relatório deverá ser contornado em azul:

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ce-3143_1362x734.png)

## Transformações

Ao clicar em Transformações, você sairá da entidade anterior que estava visualizando e exibirá o primeiro nível de transformações com a classificação padrão por esforço de cálculo.

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ce-4.png)

As transformações funcionam da mesma forma que os relatórios, exceto pelo fato de terem dois elementos secundários: linha (barra vermelha) e colunas (barra azul). Você pode explorar as transformações usando Sort By para organizar os fluxos por esforço de cálculo, número de linhas ou número de colunas. As barras vermelhas e azuis são indicadores visuais secundários e são controladas pela opção Show (Mostrar):

- O valor no primeiro menu suspenso determina a espessura das linhas e caixas
- O valor no menu suspenso da barra azul determina a altura das barras azuis
- O valor no menu suspenso da barra vermelha determina a altura das barras vermelhas

Somente as transformações têm os atributos Rows e Columns, conforme mostrado:

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ce-5.png)

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ce-6.png)

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ce-7.png)

Clique com o botão direito do mouse no período de transformação para abrir o documento ou ver o caminho completo dos dados.

## Exercícios e métricas

Drills e Metrics funcionam de forma semelhante a Reports e Transforms.

![Exercícios](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/drills-down.png)

Métricas secundárias adicionais são introduzidas para que os exercícios forneçam percepções mais profundas sobre seu desempenho relacionado. Para detalhar métricas adicionais, clique na opção **Drills (Exercícios** ). Essas métricas fornecerão os seguintes insights:

- **Total de linhas da matriz** - Número total de linhas na matriz calculada
- **Total Matrix Columns** - Número total de colunas na matriz calculada
- **Assignment Ratio Rows (Linhas de taxa de atribuição** ) - Contagem de linhas que contêm valores de alocação reais (exclui linhas vazias/zero)
- **Matrix Type (Tipo de matriz** ) - Indica se a matriz é densa (alta porcentagem de valores não nulos) ou esparsa (a maioria dos valores nulos/vazios)

![Métricas secundárias](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/secondary-metrics.png)

![imagem](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/metrics.png)
