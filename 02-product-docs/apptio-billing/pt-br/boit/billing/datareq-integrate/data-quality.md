---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Expectativas em relação à qualidade dos dados"
breadcrumb:
  - "Billing"
  - "Requisitos e integração de dados"
source_path: "boit/billing/datareq-integrate/data-quality.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Expectativas em relação à qualidade dos dados

Dados incorretos aparecerão imediatamente nas saídas de faturamento: linhas ausentes, cobranças inexplicáveis ou tarifas que parecem erradas.

No mínimo, espere manter o seguinte:

- **Integridade referencial**
  - Todos os consumidores em Faturamento devem existir no mestre de consumidores.
  - Todas as ofertas de consumo devem constar no catálogo de ofertas.
  - Todos os objetos de domínio (aplicativo, servidor, conta na nuvem, projeto) usados nas visualizações de faturamento devem existir em sua tabela mestre.
- **Totalidade**
  - As alimentações de consumo para ofertas importantes devem estar completas para cada período de faturamento.
  - Os atributos críticos dos dados mestre (por exemplo, ID do consumidor, unidade de medida, período de validade, moeda) não devem ficar em branco.
- **Consistência**
  - Os IDs e as chaves não devem mudar arbitrariamente entre os períodos.
  - As hierarquias para consumidores e ofertas devem permanecer estáveis o suficiente para seguirem as tendências.
- **Verificações de razoabilidade**
  - Procure por:
    - Volumes nulos ou negativos onde não deveriam existir.
    - Picos ou quedas repentinas nas unidades que não são explicados por eventos reais.
    - Taxas que parecem estar erradas por ordens de magnitude.

Essas verificações podem ser implementadas nos relatórios de custos ou de faturamento, mas devem fazer parte de uma rotina mensal padrão antes da publicação das contas.
