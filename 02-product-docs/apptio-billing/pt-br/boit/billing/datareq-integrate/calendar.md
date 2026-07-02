---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Calendários e períodos"
breadcrumb:
  - "Billing"
  - "Requisitos e integração de dados"
source_path: "boit/billing/datareq-integrate/calendar.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Calendários e períodos

O faturamento precisa de uma noção consistente de **períodos** :

- A maioria das implementações é **mensal**, às vezes alinhada ao calendário fiscal.
- Cada registro nas tabelas de consumo e taxas deve fazer referência a:
  - Um identificador de período (por exemplo, AAAA-MM).
  - Possivelmente uma chave do período fiscal, se o calendário fiscal da organização diferir dos meses civis.

Considerações sobre o design:

- Decida se o faturamento se alinha estritamente ao **calendário** fiscal, ao **mês civil** ou a uma abordagem híbrida.
- Quando ocorrerem períodos parciais ou eventos de transição (por exemplo, entrada em operação no meio do mês), documente como eles são tratados:
  - Períodos divididos.
  - Ajustes únicos.
  - Taxas ou unidades proporcionais.

Se o Cálculo de custos já utiliza um calendário fiscal, reutilize a mesma estrutura no Faturamento para evitar trabalho de reconciliação desnecessário.
