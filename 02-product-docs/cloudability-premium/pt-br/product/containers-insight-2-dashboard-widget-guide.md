---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Insights sobre contêineres: Guia do painel e do widget"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
  - "Alocação de custos de contêineres"
source_path: "product/containers-insight-2-dashboard-widget-guide.html"
images:
  - "images/container_10.jpg"
  - "images/container_11.jpg"
  - "images/container_12.jpg"
  - "images/container_13.jpg"
  - "images/container_14.jpg"
  - "images/container_15.jpg"
  - "images/container_16.jpg"
  - "images/container_17.jpg"
  - "images/container_3.jpg"
  - "images/container_4.jpg"
  - "images/container_5.jpg"
  - "images/container_6.jpg"
  - "images/container_7.jpg"
  - "images/container_8.jpg"
  - "images/container_9.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Insights sobre contêineres: Guia do painel e do widget

Visão geral

O Containers Insights fornece um painel padrão para exibir um resumo do custo e da eficiência de todos os clusters. Ele também oferece suporte à personalização avançada do painel. Widgets personalizados podem ser usados para consultar conjuntos de dados avançados para revelar insights mais profundos sobre custo, utilização e eficiência em Kubernetes e OpenShift Clusters.

Um painel é exibido por padrão. Você também pode criar painéis personalizados.

Painel de controle padrão

O painel padrão inclui widgets de KPI, como Total Cost (custo total), Idle Cost (custo ocioso) e Efficiency Score (pontuação de eficiência). Ele também exibe widgets de gráficos de séries temporais, mostrando tendências para os 10 principais clusters de custo ocioso e tendências de custo total para os 10 principais clusters. Todas as alterações no painel, como adição ou exclusão de widgets, atualização do layout ou ajuste de filtros globais, são salvas automaticamente. Cada usuário tem seu próprio painel padrão que pode ser personalizado de forma independente.

![Ícone de notas](../../../../03-media/cloudability-premium/images/container_3.jpg)

![Ícone de notas](../../../../03-media/cloudability-premium/images/container_4.jpg)

![Ícone de notas](../../../../03-media/cloudability-premium/images/container_5.jpg)

Painel de controle personalizado

Os usuários podem criar painéis personalizados salvando qualquer painel existente disponível para eles. O layout do painel é estruturado com widgets de KPI na parte superior, widgets de gráfico no meio e um widget de tabela na parte inferior. Em cada seção (KPI, gráfico), o posicionamento dos widgets pode ser ajustado. Se um usuário excluir todos os painéis, ele ainda receberá o painel padrão integrado pré-configurado. Todas as alterações, incluindo filtros globais e ajustes de layout, são salvas automaticamente.

![Ícone de notas](../../../../03-media/cloudability-premium/images/container_6.jpg)

![Ícone de notas](../../../../03-media/cloudability-premium/images/container_7.jpg)

Há vários widgets que podem ser adicionados ao painel.

Widgets de KPI pré-criados

Há quatro widgets de KPI pré-criados: Total Cost (custo total), Efficiency Score (pontuação de eficiência), Efficiency Score (uso) e Idle Cost (custo ocioso). Esses widgets são exibidos no painel padrão e podem ser adicionados a qualquer painel por meio do menu suspenso.

![Ícone de notas](../../../../03-media/cloudability-premium/images/container_8.jpg)

Widget de KPI personalizado

Os usuários podem adicionar widgets de KPI personalizados por meio do menu suspenso para adicionar um widget "Custom KPI".

![Ícone de notas](../../../../03-media/cloudability-premium/images/container_9.jpg)

Tipo de métrica : as opções incluem Total, CPU, Memória, GPU, TX de rede, RX de rede, FileSystem, e Volume persistente. Isso mostra as métricas para tipos de recursos específicos.

Resumo da métrica : As opções incluem custo e utilização. Isso indica se o KPI é baseado em métricas de custo ou métricas de utilização.

Alocação de métricas : As opções incluem "Fair Share" (Participação justa), "Allocated" (Alocado), "Idle" (Ocioso) e "Efficiency" (Eficiência) Isso mostra se a alocação é sobre participação justa, alocada, ociosa ou eficiência do tipo de métrica e resumo.

- Fair Share : recursos provisionados compartilhados proporcionalmente com base na alocação entre todos os locatários.
- Alocados : recursos alocados a um contêiner; o maior valor de uso e solicitação.
- Ocioso : Recursos não alocados e compartilhados de forma justa entre os locatários; a diferença entre Fair Share e Allocated.
- Eficiência : Calculada como Alocada dividida pela Quota Justa.

A combinação de tipo de métrica, resumo e alocação determina o KPI a ser criado. Veja só alguns exemplos:

| Tipo de métrica | Resumo de métricas | Alocação de métrica | KPI |
| --- | --- | --- | --- |
| Total | Custo | Eficiência | Pontuação de eficiência = Custo alocado / Custo de compartilhamento justo (ou custo total) |
| CPU | Custo | Eficiência | Pontuação de eficiência da CPU = custo alocado da CPU / custo justo da CPU |
| CPU | Custo | Fairshare | CPU Fair Share Cost = Custo das unidades de CPU fair share |
| CPU | Custo | Alocado | Custo alocado da CPU = custo das unidades de CPU alocadas |
| CPU | Custo | Inativo | Custo ocioso da CPU = Custo de compartilhamento justo da CPU - Custo alocado da CPU |
| CPU | Utilização | Eficiência | Eficiência de utilização da CPU = Unidades de CPU alocadas / Unidades de CPU de compartilhamento justo |
| CPU | Utilização | Fairshare | CPU Unidades de Ações Justas |
| CPU | Utilização | Alocado | Unidades alocadas à CPU |
| CPU | Utilização | Inativo | Unidades ociosas de CPU = Unidades de CPU Fair Share - Unidades alocadas de CPU |

Esses KPIs podem ser filtrados por clusters, namespaces, carga de trabalho, tipo de carga de trabalho, contêiner, nó ou chaves de rótulo. Os filtros são combinados com operações "AND", e somente o operador "equals" é permitido.

![captura de tela das condições de filtragem](../../../../03-media/cloudability-premium/images/container_10.jpg)

Há também vários widgets de gráficos que podem ser adicionados ao seu painel.

Widgets de gráficos pré-construídos

Há quatro widgets de gráfico pré-criados:

- Eficiência dos 10 principais clusters de custo ocioso
- Os 10 principais custos por clusters
- Os 10 com menor pontuação de eficiência por cluster
- Tendência do custo total

![Ícone de notas](../../../../03-media/cloudability-premium/images/container_11.jpg)

Widgets de gráficos personalizados

Há três tipos de widgets de gráficos personalizados compatíveis:

- Série temporal personalizada: Exibe informações de tendências sobre os conjuntos de dados consultados, com base em qualquer combinação de tipo de métrica, resumo e alocação. Ele pode ser agrupado por combinações de chaves de cluster, namespace, carga de trabalho, tipo de carga de trabalho, nó, contêiner ou rótulo. Ele também permite ordenar por 10 principais ou 10 últimos.

  ![Ícone de notas](../../../../03-media/cloudability-premium/images/container_12.jpg)![Ícone de notas](../../../../03-media/cloudability-premium/images/container_13.jpg)
- Widget personalizado superior/inferior 10 : exibe conjuntos de dados consultados em uma ordem especificada, com suporte apenas para gráficos de barras verticais.

  ![Ícone de notas](../../../../03-media/cloudability-premium/images/container_14.jpg)

  ![Ícone de notas](../../../../03-media/cloudability-premium/images/container_15.jpg)
- Custom Allocated vs Idle : exibe conjuntos de dados consultados para comparação entre alocado e ocioso, utilizável para métricas de custo e utilização.

  ![Ícone de notas](../../../../03-media/cloudability-premium/images/container_16.jpg)

  ![Ícone de notas](../../../../03-media/cloudability-premium/images/container_17.jpg)

Personalização e layout

Os usuários podem personalizar facilmente o layout e o conteúdo de seus painéis adicionando, removendo e reorganizando widgets. As configurações e os filtros de cada widget podem ser ajustados para atender às necessidades específicas de análise, proporcionando uma experiência de visualização altamente flexível e personalizada.

Este guia aborda os recursos essenciais e as opções de personalização disponíveis no novo Containers Insights. Ao utilizar esses painéis e widgets, os usuários podem obter insights mais profundos sobre seus ambientes Kubernetes, otimizando o custo, a utilização e a eficiência.

**Tópico pai:** [Alocação de custos de contêineres](../product/k8s-cost-allocation.html)
