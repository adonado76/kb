---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "KPI"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "ApptioIBM Report Studio (Novo)"
  - "Visualizações"
source_path: "studio/report-studio/visualizations/rs-kpi.html"
images:
  - "resources/images/studio_images/rs-kpi.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# KPI

O componente KPI (Key Performance Indicator, ou Indicador-chave de desempenho) é usado para destacar métricas importantes em um relatório. Ajuda os usuários a compreender rapidamente as principais métricas num relance

## Quando usar um KPI

Use um componente KPI quando desejar:

- Exiba as métricas de forma destacada
- Destaque o desempenho, os totais ou os principais resultados
- Chame a atenção para valores críticos em um relatório

## Adicionar um KPI ao relatório

1. Adicione um KPI a partir do painel Visualizações na barra de ferramentas
2. Clique no KPI para ativar os painéis Dados e Formato.
3. Painel de dados
   1. Selecione o objeto modelo na lista suspensa
   2. Métrica primária - Arraste ou adicione uma métrica primária
   3. Tipo de comparação - A métrica principal pode ser comparada com o seguinte:
      1. Nenhuma – Sem comparação.
      2. Métrica de comparação – Escolha uma métrica secundária para comparar com a métrica principal
      3. Período anterior – Escolha comparar com o período anterior da métrica principal
   4. Métrica de comparação - Arraste ou adicione uma métrica secundária para comparação
   5. Filtros - Arraste ou adicione os critérios de filtragem
4. Painel de formatação
   1. Propriedades gerais – Veja [Propriedades do componente](../components/components.html#abt-comp__comprop)
   2. Propriedades específicas do KPI
      1. Tendência
         1. Escolha a cor para tendências positivas, negativas e neutras
         2. Escolha o indicador para representar a tendência (seta e valor)
         3. Escolha o tamanho do indicador de tendência
      2. Métrica primária/comparativa
         1. Edite as seguintes propriedades, conforme necessário para o nome e o valor da métrica primária
         2. Tamanho e estilo da fonte (negrito, itálico, sublinhado)
         3. Cor do texto do título (com a opção de redefinir a cor)
      3. Notas abreviadas - Reduza os valores das métricas primárias e secundárias.

Exemplo: Componente KPI

![imagem do componente KPI](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rs-kpi.png)

Observação: o KPI suporta fórmulas personalizadas e dimensões de fórmulas. Para obter mais detalhes, consulte [Fórmulas personalizadas.](../create-first/custom-formula.html "As fórmulas personalizadas (também conhecidas como dimensões de fórmula) permitem definir novas dimensões calculadas utilizando campos existentes no seu modelo de dados. Isso permite uma análise mais profunda e insights mais ricos, sem a necessidade de alterações no conjunto de dados ou esquema subjacente.")
