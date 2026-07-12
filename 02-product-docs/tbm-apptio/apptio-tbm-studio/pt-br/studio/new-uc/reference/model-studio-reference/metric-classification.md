---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Classificação métrica"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Model Studio"
  - "Métricas de modelo"
source_path: "studio/new-uc/reference/model-studio-reference/metric-classification.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Classificação métrica

As métricas são classificadas em duas categorias com base na forma como seus valores são calculados.

**Métricas modeladas**

**Descrição:** Uma métrica modelada percorre a estrutura de alocação. Possui fatores que geram valor e alocações que distribuem esse valor. Custo, orçamento e previsão são métricas que costumam ser modeladas.

**Características**

- O valor é somado ao agrupar
- Não é possível realizar cálculos entre períodos
- Participa dos fluxos de alocação
- Exibido nos relatórios modelo

**Métricas calculadas**

**Descrição:** Uma métrica calculada utiliza uma fórmula para derivar seu valor a partir de outras métricas ou colunas. Normalmente, calculam-se métricas de variância e de razão.

**Características**

- A fórmula é recalculada a cada visualização (não é somada)
- É capaz de realizar cálculos ao longo de períodos de tempo
- Não participa das alocações
- Utilizado para análise e elaboração de relatórios

**Tópico principal:** [Métricas do modelo](../../../../studio/new-uc/reference/model-studio-reference/model-metrics.html)
