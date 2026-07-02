---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Ordem e prioridade de alocação"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Model Studio"
  - "Alocações"
source_path: "studio/new-uc/reference/model-studio-reference/allocation-order.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Ordem e prioridade de alocação

As alocações são executadas em uma ordem determinística com base na estrutura do gráfico do modelo.

**Regras de execução**

- As alocações são executadas do nível mais baixo para o mais alto (de baixo para cima)
- Dentro de um nível, as alocações são executadas na ordem em que foram criadas
- Os drivers de unidade são executados antes das alocações de cada objeto
- Todas as entradas de um objeto devem ser concluídas antes que suas saídas sejam executadas. As alocações recursivas são executadas após as alocações padrão

**Tópico principal:** [Alocações](../../../../studio/new-uc/reference/model-studio-reference/allocations.html)
