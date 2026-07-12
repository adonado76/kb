---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Padrões comuns de filtragem"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Filtros e segmentadores"
source_path: "studio/new-uc/reference/report-studio-reference/common-filter.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Padrões comuns de filtragem

**Seletor de período**

**Objetivo:** Permitir que os usuários alternem entre as visualizações mensal, trimestral e anual.

**Implementação:**

1. Adicionar um seletor de colunas
2. Arraste valores baseados no tempo da perspectiva Tempo: CurrentMonth, CurrentQuarter (ou QTD), YTD
3. Definir como “Seleção única” com “Seleção obrigatória”
4. Adicionar texto dinâmico <%=CurrentDate( )%> aos cabeçalhos das colunas da tabela

**Filtro hierárquico por região**

**Objetivo:** Filtrar por região → país → cidade.

**Implementação:**

1. Criar grupo de perspectivas personalizado
2. Adicionar e renomear campos: 01\_Region, 02\_Country, 03\_City
3. Criar um filtro hierárquico usando o grupo
4. Opcionalmente, use o formato de fatiador compacto para economizar espaço

**Filtro de limite de custo**

**Objetivo:** Filtro que mostre apenas os custos significativos acima de um valor mínimo.

**Implementação:**

1. Adicionar “Custo” (ou métrica relevante) como um filtro
2. Configurar o intervalo do controle deslizante
3. Definir a posição padrão para excluir valores pequenos
4. Salvar relatório com as configurações padrão

**Tópico principal:** [Componentes do relatório: Filtros e segmentadores](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
