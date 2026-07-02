---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Filtros hierárquicos e em cascata"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Filtros e segmentadores"
source_path: "studio/new-uc/reference/report-studio-reference/h-c-filter.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Filtros hierárquicos e em cascata

**Criação de um filtro hierárquico**

Os filtros hierárquicos permitem a filtragem detalhada através de vários níveis de classificação.

**Pré-requisitos:**

- Perspectiva personalizada com campos agrupados
- Campos ordenados para representar níveis hierárquicos

**Passos:**

1. Crie um grupo de perspectivas personalizado contendo os campos da hierarquia
2. Organize os campos usando prefixos sequenciais (por exemplo, 01\_Type, 02\_SubType, 03\_OS )
3. Na guia Relatório, clique em Segmentador de linhas
4. Arraste o grupo de perspectivas (não os campos individuais) para a área “Fatiar por”

**Observação:** não é permitido usar traços (-) nos nomes dos campos. Use dois pontos (:) ou sublinhados (\_) em vez disso.

**Pesquisa por código de hierarquia**

Para campos que representam códigos hierárquicos (por exemplo, códigos de conta, IDs de centro de custo), ative o comportamento especial de agrupamento:

1. Clique com o botão direito do mouse no campo na perspectiva personalizada
2. Selecione Editar '[nome do campo]'
3. A marca representa um código de hierarquia

**Comportamento:** Quando um usuário digita um texto na pesquisa do filtro, o sistema localiza todos os valores que começam com esse texto mais um caractere adicional, cria uma entrada de grupo para cada combinação única e, ao selecionar um filtro de grupo, exibe todos os valores correspondentes.

**Tópico principal:** [Componentes do relatório: Filtros e segmentadores](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
