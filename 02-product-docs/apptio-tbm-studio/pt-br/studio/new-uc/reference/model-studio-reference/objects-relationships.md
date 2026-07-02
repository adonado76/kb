---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Relações e dependências entre objetos"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Model Studio"
  - "Objetos modelo"
source_path: "studio/new-uc/reference/model-studio-reference/objects-relationships.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Relações e dependências entre objetos

Os objetos do modelo são conectados por meio de alocações e drivers. Compreender essas relações é fundamental para a elaboração de modelos de custos precisos.

**Tipos de relacionamento**

|  |  |  |
| --- | --- | --- |
| **Relacionamento** | **Direção** | **Descrição** |
| Condutor | No objeto | O driver de unidade insere o valor de uma coluna no objeto modelo |
| Alocação (Saída) | Fora do objeto | Envia o valor deste objeto para os objetos de destino |
| Alocação (Entrada) | No objeto | Recebe valores dos objetos de origem |

**Regras de dependência**

- O gráfico do modelo não deve conter ciclos (sem alocações circulares)
- Todos os objetos do modelo devem conter dados válidos para o período ativo
- As tabelas de origem e de destino devem ser extraídas antes de criar alocações
- As alocações são executadas em uma ordem determinística com base no gráfico de objetos
- Os erros de transformação impedem os cálculos do modelo para os objetos afetados

*→ Consulte [a Ordem de Execução do Modelo para obter detalhes sobre a sequência de cálculos](../../concepts-architecture/model-architecture/model-object-relationship.html)*

*→ Consulte [Erros de alocação circular para obter orientações sobre como resolver o problema](../../ts-support/rs-issues.html)*

**Tópico principal:** [Objetos de modelo](../../../../studio/new-uc/reference/model-studio-reference/model-objects.html)
