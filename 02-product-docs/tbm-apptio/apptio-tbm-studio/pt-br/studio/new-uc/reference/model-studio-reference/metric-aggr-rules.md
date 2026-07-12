---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Regras de agregação de métricas"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Model Studio"
  - "Métricas de modelo"
source_path: "studio/new-uc/reference/model-studio-reference/metric-aggr-rules.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Regras de agregação de métricas

**Como as métricas modeladas são agregadas**

Ao visualizar métricas modeladas em diferentes níveis de agrupamento:

- Nível de detalhe: mostra os valores de cada linha
- Nível agrupado: soma todos os valores do grupo
- Em todos os períodos: segue a configuração de Comportamento temporal

**Como as métricas calculadas são agregadas**

As métricas calculadas recalculam sua fórmula em cada nível de agrupamento, em vez de somar:

- Nível de detalhe: Fórmulas executadas por linha
- Nível agrupado: a fórmula é aplicada a valores agrupados
- Exceção: se a opção “Pode somar” estiver marcada, os valores serão somados

**Tópico principal:** [Métricas do modelo](../../../../studio/new-uc/reference/model-studio-reference/model-metrics.html)
