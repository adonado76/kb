---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Todas as opções de configuração de alocação"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Model Studio"
  - "Alocações"
source_path: "studio/new-uc/reference/model-studio-reference/allocation-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Todas as opções de configuração de alocação

Esta tabela reúne todas as opções de configuração para todos os tipos de alocação.

**Referência completa de parâmetros**

|  |  |  |
| --- | --- | --- |
| **Parâmetro** | **Aplica-se a** | **Descrição** |
| Alocar | Todos os tipos | Selecione as métricas a serem alocadas (Custo, Orçamento, etc.) |
| Está usando | Todos os tipos | Seleção do tipo de alocação |
| Para | Todos os tipos | Objeto do modelo de destino |
| Distribuição | Ponderado, Consumo, Padrão, Recursão | Igual, Por peso ou Relação de dados |
| Peso por | Quando a distribuição = peso por | Coluna da tabela, métrica ou outro fator determinante |
| Relação entre dados | Quando a distribuição = relação entre os dados | Pares de colunas de origem e destino |
| Coluna de Consumo | Apenas para consumo | Coluna de meta que mostra as unidades consumidas |
| Coluna de Capacidade | Apenas para consumo | Coluna de origem que mostra a capacidade total |
| Fórmula | Apenas fórmula | Fórmula de alocação personalizada |
| Precisão | Apenas recursão | Valor mínimo para continuar a iteração |
| Número máximo de iterações | Apenas recursão | Número máximo de ciclos de alocação |
| Modo incremental | Apenas recursão | Adiciona o valor da iteração à fonte |
| Por filtro | Fórmula | Filtrar linhas na tabela de origem |
| Para filtrar | Fórmula | Filtrar linhas na tabela de destino |

**Tópico principal:** [Alocações](../../../../studio/new-uc/reference/model-studio-reference/allocations.html)
