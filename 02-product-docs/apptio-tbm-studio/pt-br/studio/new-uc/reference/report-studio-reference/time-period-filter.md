---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Filtragem por período"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Filtros e segmentadores"
source_path: "studio/new-uc/reference/report-studio-reference/time-period-filter.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Filtragem por período

**Funcionalidade do seletor de datas**

Embora o TBM Studio não possua um componente específico para seleção de datas, é possível criar uma funcionalidade de seleção de datas utilizando seletores de coluna ou botões.

**Opção 1: Seletor de colunas como seletor de datas**

1. Adicionar um seletor de colunas ao relatório
2. Configurar com valores baseados no tempo a partir da perspectiva Tempo
3. Configurar para o modo de seleção única

Os usuários podem escolher entre opções como “Mês atual”, “Trimestre atual”, “Semestre atual” ou “Acumulado no ano”.

**Configuração do período de dados**

Nos gráficos e tabelas, a configuração “Período dos dados” controla quais dados de cada período são exibidos:

|  |  |
| --- | --- |
| **Configuração** | **Comportamento** |
| Data atual do projeto (padrão) | Exibe os dados correspondentes à data selecionada no seletor de datas do cabeçalho do relatório |
| Início do atual exercício fiscal | Bloqueia até o primeiro período do ano fiscal atual |
| Início do trimestre fiscal atual | Dados referentes ao primeiro período do trimestre atual |
| Data específica | Bloqueia durante um período explicitamente especificado |

Observação: Para criar gráficos de tendências que mostrem o ano fiscal completo, independentemente do período atual, defina o “Período de dados” como “Início do ano fiscal atual”

**Tópico principal:** [Componentes do relatório: Filtros e segmentadores](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
