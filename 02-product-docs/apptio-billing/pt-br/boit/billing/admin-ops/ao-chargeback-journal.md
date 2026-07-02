---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Estorno com diários"
breadcrumb:
  - "Billing"
  - "Administração e Operações"
source_path: "boit/billing/admin-ops/ao-chargeback-journal.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Estorno com diários

**Quando usar**

- O departamento financeiro deseja tratar as saídas de faturamento como receita e despesa internas.
- As entradas de estorno são lançadas no livro razão.

**Orientar**

- A mesma estrutura básica do showback, além de um mapeamento estável para os segmentos GL ou Finance.
- Controle de qualidade mensal mais rigoroso em relação aos totais e publicações dos diários.

**Elementos-chave**

- Tabela de saída de faturamento ampliada com:
  - Campos da conta GL.
  - Centro de custos e outros segmentos financeiros.
  - Qualquer tipo de documento ou campos de referência exigidos pelo departamento financeiro.
- Relatórios de diário ajustados ao formato Finance.

**Relatórios típicos**

- Relatórios de faturamento para conversas com consumidores.
- Relatório de exportação do diário com detalhes ao nível da conta.
- Relatório de reconciliação:
  - Total de faturamento vs. total do diário vs. custo recuperável.

**Notas de implementação**

- Alinhe as estruturas de consumidores e segmentos com o departamento financeiro desde o primeiro dia.
- Trate as alterações nas taxas e no mapeamento como eventos controlados, com histórico de alterações.
