---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Manipulação de erros"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Data Studio Referência"
source_path: "studio/new-uc/reference/error-handling.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Manipulação de erros

## Tipos comuns de erros

**Erros na fonte:**

|  |  |  |
| --- | --- | --- |
| **Erro** | **Causa** | **Resolução** |
| Conversão para cordas duplas | Incompatibilidade de tipos na referência à coluna | Alterar o tipo da coluna ou usar conversão explícita |
| Erro ao obter a tabela de referência | Tabela de origem excluída | Recriar a tabela de origem |

**Erros de importação:**

|  |  |  |
| --- | --- | --- |
| **Erro** | **Causa** | **Resolução** |
| Esperava-se um tipo de dados "Label", mas foi encontrado um tipo numérico | Todos os valores numéricos na coluna "Rótulo" | Alterar o tipo de entrada para Qualquer |
| A coluna não existe | A validação detectou a ausência de uma coluna | Excluir da validação ou adicionar ao upload |
| Foi adicionada uma coluna | Coluna inesperada no upload | Adicionar à validação ou remover do upload |

**Erros de fórmula:**

|  |  |  |
| --- | --- | --- |
| **Erro** | **Causa** | **Resolução** |
| Não é possível encontrar a coluna | Falta a coluna referenciada | Adicionar coluna ou corrigir fórmula |
| Não é possível encontrar a tabela | Falta a tabela referenciada | Atualizar referência da fórmula |
| Pesquisa sem correspondência | Incompatibilidade de tipos nas colunas de pesquisa | Alinhar tipos de coluna ou converter |

**Erros no pipeline:**

|  |  |  |
| --- | --- | --- |
| **Erro** | **Causa** | **Resolução** |
| Ciclo detectado | Referência circular entre tabelas | Remover um dos lados da referência circular |
| Detectada recursão | A tabela faz referência a si mesma | Corrigir configuração autorreferencial |

**Tópico principal:** [Referência do ` Data Studio `](../../../studio/new-uc/reference/data-studio-reference.html)
