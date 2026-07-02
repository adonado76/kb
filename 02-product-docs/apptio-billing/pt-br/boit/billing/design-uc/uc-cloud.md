---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Visão geral dos custos e taxas unitárias da nuvem"
breadcrumb:
  - "Billing"
  - "Padrões de Design e Casos de Uso"
source_path: "boit/billing/design-uc/uc-cloud.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Visão geral dos custos e taxas unitárias da nuvem

Observação: **aplica-se apenas ao padrão de faturamento.**

**Problema**

Você precisa de uma visão repetível dos custos e encargos da nuvem por provedor, conta, serviço e consumidor, com visibilidade da taxa unitária.

**Entradas**

- Dados de faturamento/uso do provedor de nuvem
- Tabelas de mapeamento de tags e contas (para serviços e consumidores)
- Definições de unidades específicas da nuvem
- Tarifas ou regras de preços para serviços em nuvem

**Passos**

1. Confirme **se os dados de uso da nuvem** para o período foram carregados e estão completos.
2. Validar **mapeamentos de tags** :
   - Analise algumas contas e certifique-se de que as tags correspondem ao serviço e ao consumidor esperados.
3. Execute os **modelos de domínio da nuvem** no Padrão de Faturamento:
   - Agregue volumes em unidades padrão.
   - Anexe o custo e o preço, quando aplicável.
4. Abra o **relatório de faturamento da nuvem** :
   - Filtrar por provedor e período.
   - Revise as cobranças por serviço e consumidor.
5. Abra o **relatório de taxa unitária da nuvem** :
   - Para cada combinação de provedor-serviço:
   - Unidades, custo por unidade, preço por unidade.
   - Identifique valores atípicos (taxas unitárias altas ou baixas).
6. Use filtros para aprofundar:
   - Uma conta ou assinatura.
   - Um agrupamento de tags (por exemplo, aplicação, ambiente).

**Relatórios importantes**

- Faturamento em nuvem por provedor/conta/serviço
- Taxas unitárias de nuvem por provedor/serviço/ambiente
- Relatório de exceções na nuvem para uso sem marcação ou com marcação inadequada
