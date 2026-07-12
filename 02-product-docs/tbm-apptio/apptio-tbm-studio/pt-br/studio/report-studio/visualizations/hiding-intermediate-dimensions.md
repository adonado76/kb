---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Ocultando dimensões intermediárias"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "ApptioIBM Report Studio (Novo)"
  - "Visualizações"
  - "Tabela"
source_path: "studio/report-studio/visualizations/hiding-intermediate-dimensions.html"
images:
  - "resources/images/studio_images/hide-1e.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Ocultando dimensões intermediárias

O recurso “Ocultar dimensões intermediárias” permite ocultar dimensões utilizadas como etapas intermediárias em fórmulas ou cálculos, ajudando a apresentar dados mais claros e relevantes aos usuários finais. Isso garante que apenas as dimensões relevantes sejam exibidas nos componentes do relatório, enquanto os campos intermediários ou de apoio permanecem ocultos.

1. Ocultar dimensões nas tabelas
   1. Abra o painel **de configuração de dados** da tabela.
   2. Na seção **“Linhas”** ou **“Valores”**, localize a dimensão que deseja ocultar.
   3. Abra o **menu suspenso** ao lado do nome da dimensão e selecione **Ocultar**.
   4. Depois de ocultar, um **ícone de ocultação** aparece ao lado do nome da dimensão.
   5. A dimensão não está mais visível na visualização da tabela.

      ![imagem de uma dimensão oculta](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/hide-1e.png)
2. Mostrar dimensões ocultas
   1. Para exibir uma dimensão, abra o **menu de opções** novamente e selecione “**Mostrar** ”.
   2. A dimensão reaparece na tabela.
3. Ocultar dimensões nos gráficos
   1. Abra o painel **de configuração de dados** de um gráfico.
   2. Da mesma forma que nas tabelas, clique no **menu de opções** ao lado da dimensão que deseja ocultar e selecione **Ocultar**.
   3. O gráfico é atualizado para exibir apenas as dimensões visíveis.

A tabela suporta fórmulas personalizadas e dimensões de fórmula. Para mais detalhes, consulte [Fórmulas personalizadas](../create-first/custom-formula.html "As fórmulas personalizadas (também conhecidas como dimensões de fórmula) permitem definir novas dimensões calculadas utilizando campos existentes no seu modelo de dados. Isso permite uma análise mais aprofundada e insights mais detalhados, sem exigir nenhuma alteração no conjunto de dados ou no esquema subjacente.")

**Tópico principal:** [Tabela](../../../studio/report-studio/visualizations/rs-table.html "O componente de tabela exibe dados em um formato tabular estruturado. É ideal para apresentar informações detalhadas, resumir métricas e permitir a filtragem interativa dentro de um relatório.")
