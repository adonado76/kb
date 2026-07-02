---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configuração de vinculação de dados"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Filtros e segmentadores"
source_path: "studio/new-uc/reference/report-studio-reference/data-binding-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuração de vinculação de dados

**Configuração do campo de origem**

Os filtros são preenchidos a partir dos campos das perspectivas. O tipo de campo determina o comportamento do filtro:

|  |  |
| --- | --- |
| **Tipo de Campo** | **Comportamento do cortador** |
| Texto/Rótulo | Cria um filtro de lista com valores selecionáveis |
| Numérico | Cria um filtro deslizante com controles de intervalo |
| Data | Cria um filtro de lista com ordenação cronológica |
| Campo bloqueado | Oferece resultados mais previsíveis; essencial para cortadores compactos globais |
| Campo desbloqueado | , Produz resultados satisfatórios |

**Para adicionar um filtro:**

1. Na guia Relatório, clique em Segmentador de linhas
2. Arraste um campo de uma perspectiva para a área “Filtrar por”
3. Configure a aparência e o comportamento usando a guia Slicer

**Opções de classificação para valores**

Os valores do filtro podem ser ordenados de duas maneiras por meio das opções de ordenação na guia "Filtro":

|  |  |
| --- | --- |
| **Opção de classificação** | **Comportamento** |
| Por estado | Agrupa os valores por estado (Selecionados → Relacionados → Não relacionados) e, em seguida, ordena-os alfanumericamente dentro de cada grupo |
| abc/123 | Classifica todos os valores em ordem alfabética, independentemente do estado |

**Classificação padrão por tipo de dados:**

- Texto: Por ordem alfabética
- Números: Ascendente
- Datas: Cronológicas

Observação: os usuários que visualizam o relatório não podem alterar a opção de ordenação — ela é definida pelo criador do relatório.

**Tópico principal:** [Componentes do relatório: Filtros e segmentadores](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
