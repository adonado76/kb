---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Estratégias de contingência e correção"
breadcrumb:
  - "Billing"
  - "Manual de lançamento"
source_path: "boit/billing/go-live/gl-falback.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Estratégias de contingência e correção

Às vezes, as coisas vão dar errado. Decida antecipadamente como irá corrigi-los.

## Correções dentro do período

Use quando um problema for detectado antes que as contas sejam formalmente lançadas ou os diários registrados.

Ações típicas:

- Corrigir dados (por exemplo, consumo, mapeamento, taxas).
- Execute novamente os modelos de faturamento relevantes em Staging e Produção.
- Revalide relatórios principais e visualizações de controle de qualidade.
- Reexporte os diários, se aplicável.

Tente evitar repetidas repetições parciais para o mesmo período; agrupe as correções sempre que possível.

## Correções pós-lançamento

Use quando um problema for descoberto após as contas serem compartilhadas ou os diários lançados.

Opções:

- **Apenas faturamento** (showback):
  - Corrija o modelo e os dados para o próximo período.
  - Documente a correção e, se necessário, aplique um ajuste único na fatura do próximo período.
- **Estorno** (diários):
  - Se o erro for relevante, prepare diários de correção em coordenação com o departamento financeiro.
  - Use o Faturamento para calcular os deltas:
    - O que foi cobrado.
    - O que deveria ter sido cobrado.
    - Diferença por consumidor e conta.

Em ambos os casos, certifique-se de que a causa raiz seja resolvida para que o mesmo problema não se repita todos os meses.
