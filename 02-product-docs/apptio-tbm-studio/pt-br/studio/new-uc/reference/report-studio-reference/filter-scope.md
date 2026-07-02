---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Escopo do filtro"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Filtros e segmentadores"
source_path: "studio/new-uc/reference/report-studio-reference/filter-scope.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Escopo do filtro

**Âmbito no nível do relatório**

Os filtros colocados diretamente na tela do relatório (e não em uma caixa de grupo) se aplicam a todas as tabelas e gráficos do relatório.

**Comportamento:**

- Todos os componentes da consulta ad hoc respondem às seleções do filtro
- Os filtros em guias diferentes afetam apenas os componentes da mesma guia
- Vários divisores combinados com a lógica AND

**Âmbito no nível do grupo**

Os filtros colocados dentro de uma caixa de grupo se aplicam apenas aos componentes dentro desse grupo (e dos grupos aninhados).

**Para criar filtros com escopo de grupo:**

1. Adicione uma caixa de grupo ao relatório
2. Coloque o cortador dentro da caixa de grupo
3. Coloque as tabelas/gráficos que devem ser filtrados dentro do mesmo grupo

Isso permite a existência de vários contextos de filtro independentes dentro de um único relatório, visualizações comparativas com diferentes configurações de filtro e filtragem específica por seção.

**Tópico principal:** [Componentes do relatório: Filtros e segmentadores](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
