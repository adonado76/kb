---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Comportamento do cálculo de alocação"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Model Studio"
  - "Alocações"
source_path: "studio/new-uc/reference/model-studio-reference/allocation-calc-behaviour.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Comportamento do cálculo de alocação

**Custos não alocados**

Quando as alocações baseadas em critérios de correspondência falham, os custos permanecem não alocados no objeto de origem.

**Causas comuns de custos não alocados**

- Os valores das relações entre os dados não correspondem entre a origem e o destino
- A tabela de destino está vazia ou faltam as linhas esperadas
- Ponderar as somas das colunas para zero
- As condições do filtro excluem todas as linhas correspondentes

**Dica:** use o painel de visualização da alocação para identificar linhas não alocadas antes de salvar as alterações.

**Comportamento de ponderação negativa**

Por padrão, o TBM Studio não realiza a alocação quando os valores de ponderação incluem valores negativos. Isso evita resultados de cálculo inesperados.

**Soluções alternativas para valores negativos**

|  |  |
| --- | --- |
| **Abordagem** | **Descrição** |
| Alocação de fórmulas | Use =SOURCE\*( {Table.Weight} /~ {Table.Weight} ) para ativar a ponderação negativa seletivamente |
| Separar valores | Separe os valores positivos e negativos na fonte e utilize o valor absoluto para a ponderação |
| Corrigir os dados de origem | Remova os valores negativos da coluna de ponderação na fonte |

Consulte a seção “Problemas com ponderação negativa” para obter orientações detalhadas sobre o diagnóstico e a resolução de problemas

**Tópico principal:** [Alocações](../../../../studio/new-uc/reference/model-studio-reference/allocations.html)
