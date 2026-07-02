---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Moedas e câmbio"
breadcrumb:
  - "Billing"
  - "Requisitos e integração de dados"
source_path: "boit/billing/datareq-integrate/currency.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Moedas e câmbio

O faturamento pode operar em ambientes com várias moedas, mas geralmente é mais simples se os resultados do faturamento forem apresentados em uma **única moeda de apresentação** para as partes interessadas do negócio.

Pontos principais:

- **Moedas de origem**
  - O cálculo de custos pode receber custos em várias moedas e convertê-los usando taxas de câmbio.
  - Os volumes de consumo são geralmente neutros em termos monetários.
- **Moeda de apresentação**
  - Decida em que moeda as contas e os diários devem ser apresentados (por exemplo, USD).
  - Certifique-se de que as taxas de câmbio utilizadas no cálculo de custos sejam aplicadas de forma consistente, para que as cobranças sejam reconciliadas.
- **Faturamento entre entidades**
  - Para cenários entre países ou com várias entidades, confirme:
    - Quais taxas de câmbio são utilizadas para faturamento interno e relatórios externos?
    - Se o faturamento precisa refletir o câmbio separadamente ou apenas o resultado convertido.

Documente a configuração da moeda antecipadamente e mantenha-a estável. Alterar a lógica cambial no meio do ano pode criar confusão, a menos que seja comunicada de forma clara e rastreável.
