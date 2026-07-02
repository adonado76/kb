---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Considerações sobre desempenho"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Tabelas"
source_path: "studio/new-uc/reference/report-studio-reference/performance-considerations.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Considerações sobre desempenho

O desempenho da tabela depende do volume de dados, dos cálculos e da complexidade da configuração.

|  |  |
| --- | --- |
| **Fator** | **Recomendação** |
| Contagem de linhas | Use paginação para conjuntos de dados grandes. Considere usar filtros para reduzir o número de linhas exibidas. |
| Fórmulas complexas | Sempre que possível, transfira cálculos complexos para transformações d Data Studio. |
| Várias colunas de hora | Cada coluna baseada no calendário requer cálculos separados. Use com moderação. |
| Minigráficos | Solicitar dados para cada período de análise de tendências. Verifique se os dados subjacentes existem. |
| Indicadores de status | Os cálculos de ícones são leves, mas aumentam a carga de processamento. |
| Profundidade de agrupamento | Hierarquias profundas (4 ou mais níveis) afetam o tempo de renderização. |
| Cortadores interativos | Use a atualização manual para relatórios com muitas interações com os filtros. |

**Tópico principal:** [Componentes do relatório: Tabelas](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
