---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Relação entre faturamento e custos"
breadcrumb:
  - "Billing"
  - "Administração e Operações"
  - "Arquitetura da solução e dependências"
source_path: "boit/billing/sol-arch-depend/sol-arch-intro.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Relação entre faturamento e custos

Esta seção explica como o faturamento é organizado, como ele se relaciona com o cálculo de custos e o que deve existir antes que o conteúdo do faturamento possa ser usado.

## Relação entre faturamento e custos

O faturamento não é um aplicativo independente. É um conjunto de **componentes, modelos, tabelas e relatórios** que são instalados em um projeto de Cálculo de Custos existente e expostos aos usuários por meio do front-end.

Em um nível elevado:

1. Os dados fluem para o Cálculo de custos a partir dos sistemas de origem.
2. O cálculo de custos aloca e normaliza os custos.
3. Os componentes de faturamento são adicionados a um projeto de cálculo de custos e:
   - Defina ofertas, unidades e tarifas faturáveis.
   - Resultados do cálculo de custos de consumo e dados de consumo.
   - Produza documentos de faturamento, como faturas, relatórios detalhados e diários.

Pontos principais:

- O faturamento **depende da** implantação e estabilidade do projeto de cálculo de custos.
- O faturamento utiliza os **mesmos ambientes** e **o mesmo mecanismo de modelagem** que o cálculo de custos.
