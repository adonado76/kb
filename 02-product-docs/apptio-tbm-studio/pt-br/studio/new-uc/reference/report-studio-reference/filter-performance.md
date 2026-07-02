---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Considerações sobre o desempenho do filtro"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Filtros e segmentadores"
source_path: "studio/new-uc/reference/report-studio-reference/filter-performance.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Considerações sobre o desempenho do filtro

**Listas de valores grandes**

**Limites e limites mínimos:**

|  |  |  |
| --- | --- | --- |
| **Componente** | **Limite** | **Manuseio** |
| Valores do Slicer | Máximo de 250 valores | Mensagem exibida quando o limite é excedido |
| Diálogo de filtro | 1.000 valores exibidos | Use a caixa de pesquisa para encontrar outros valores |
| Editar seleções do filtro | Sem limite rígido | Use a opção "Valores não exibidos no momento" |

**Melhores práticas de desempenho:**

1. Filtrar segmentadores para reduzir a contagem de valores antes da exibição
2. Use cortadores compactos quando forem necessárias várias dimensões
3. Aplicar filtros no nível dos componentes para pré-filtrar os dados antes da avaliação do segmentador
4. Considere o uso de filtros hierárquicos para dimensões categóricas de grande porte

**Tópico principal:** [Componentes do relatório: Filtros e segmentadores](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
