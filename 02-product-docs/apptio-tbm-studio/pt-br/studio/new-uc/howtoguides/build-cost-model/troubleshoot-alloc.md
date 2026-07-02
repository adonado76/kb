---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Referência para solução de problemas de alocação"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar modelos de custos"
  - "Criar alocações"
source_path: "studio/new-uc/howtoguides/build-cost-model/troubleshoot-alloc.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Referência para solução de problemas de alocação

## Mensagens de erro comuns e soluções

|  |  |  |
| --- | --- | --- |
| **Mensagem de erro** | **Causa** | **Solução** |
| Não foi possível encontrar as chaves vinculadas | Não existem colunas correspondentes ou elas não contêm valores em comum | Verifique os nomes das colunas e os dados em ambas as tabelas |
| Não foram encontradas ligações de colunas | A alocação automática herdada não consegue encontrar colunas correspondentes | Mude para a correspondência explícita de chaves; desative a relação automática |
| A tabela de índices de alocação é muito grande | Existem demasiadas combinações de origem e destino | Adicione relações entre dados para restringir o escopo; reduza a granularidade dos identificadores |

## Lista de verificação para quando a alocação não funciona

Quando as alocações gerarem resultados inesperados, verifique:

- Tanto a tabela de origem quanto a de destino estão em checkout
- A etapa do modelo existe em ambas as tabelas
- A alocação é salva (não apenas exibida na pré-visualização)
- Existem colunas correspondentes em ambas as tabelas com valores em comum
- A coluna de ponderação é numérica, sem valores nulos ou negativos
- Os filtros não excluem todas as linhas de origem
- Não há alocações conflitantes para o mesmo destino
- O cálculo do modelo foi executado após as alterações

## Dicas para otimização de desempenho

- **Use relações de dados:** limita o escopo da alocação e melhora o desempenho.
- **Reduzir a granularidade dos identificadores:** um número menor de identificadores únicos resulta em tabelas de alocação menores.
- **Limitar os caminhos de alocação:** cada alocação aumenta a sobrecarga de cálculo.
- **Analise tabelas grandes:** objetos de modelo com mais de 50.000 linhas podem precisar de otimização.

## O que vem a seguir

Depois de criar suas alocações:

- [Acompanhe o fluxo de custos pelo modelo](trace-cost-flow.html) : aprenda a rastrear custos individuais em vários níveis.
- [Criar relatórios de modelo (diagramas de Sankey)](create-model-rep.html) : Crie visualizações de Sankey do seu modelo de custos.
- Entenda [a arquitetura do modelo](../../concepts-architecture/model-architecture/model-concepts-overview.html) : aprofunde seus conhecimentos sobre como funcionam as alocações.

**Tópico principal:** [Criar alocações](../../../../studio/new-uc/howtoguides/build-cost-model/create-allocation.html)
