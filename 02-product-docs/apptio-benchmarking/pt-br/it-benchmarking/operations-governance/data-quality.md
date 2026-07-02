---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Rotinas de qualidade e validação de dados"
breadcrumb:
  - "Benchmarking"
  - "Relatórios de benchmarking"
  - "Operações e Governança"
source_path: "it-benchmarking/operations-governance/data-quality.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Rotinas de qualidade e validação de dados

Os benchmarks são uma boa maneira de eliminar problemas de modelagem. Use isso em vez de escondê-los.

## Validação anual

A cada atualização anual:

- Compare **a estrutura de TI ( OpEx )** com a do ano anterior:
  - Grandes mudanças devem corresponder a eventos reais (migrações, reestruturações) ou alterações explícitas na modelagem.
- Compare **os principais custos unitários de infraestrutura** em relação ao ano anterior:
  - Grandes saltos justificam uma verificação dos dados relativos aos custos e ao volume.
- Reconcilie **os índices de gastos com TI e receitas** com o departamento financeiro para garantir o equilíbrio.

Se um salto for devido a uma mudança no modelo TBM, identifique claramente esse ano como uma “mudança estrutural” em sua documentação ou comentário.

## Verificações de sanidade antes do uso executivo

Antes de qualquer reunião importante:

- Confirme se os filtros de pares refletem a história: setor, faixa de tamanho, região, ano.
- Certifique-se de que consegue responder:
  - O que está incluído nesta métrica?
  - Com quem nos comparamos?
  - Essa diferença é real ou baseada em dados?

Se você não conseguir responder a essas perguntas em linguagem simples, não use essa visualização ainda. Corrija a configuração ou consulte novamente a métrica em [Referência de dados e metodologia](../home.html#benchmarking__data-methodology).
