---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Showback simples do serviço PxQ"
breadcrumb:
  - "Billing"
  - "Padrões de Design e Casos de Uso"
source_path: "boit/billing/design-uc/uc-simple.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Showback simples do serviço PxQ

**Problema**

Você deseja uma visão mensal transparente que responda:

“Quem está usando quais serviços, quanto está usando e qual é o custo calculado?”

**Entradas**

- Catálogo de serviços/ofertas com unidades e sinalizadores faturáveis
- Mestre do consumidor
- Dados de consumo mensal (unidades por serviço e consumidor)
- Tarifas por serviço e período

**Passos**

1. Confirme se o **catálogo de ofertas** está atualizado e se os sinalizadores de cobrança estão configurados corretamente.
2. Carregue ou atualize **os dados de consumo** do período atual.
3. Carregue ou confirme **as taxas** para cada oferta ativa para o período.
4. Execute os modelos de faturamento no ambiente apropriado (em desenvolvimento/staging para testes, produção para operação).
5. Abra **a** fatura/relatório resumido do período.
6. Filtre por consumidor conforme necessário e confirme:
   - Os serviços listados correspondem às expectativas.
   - As unidades e as taxas parecem corretas.
   - Os custos totais são razoáveis.

**Relatórios importantes**

- Fatura / relatório resumido
- Relatório resumido do consumidor
- Relatório de controle de qualidade/exceções para mapeamentos ausentes
