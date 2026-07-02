---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Design centrado na nuvem"
breadcrumb:
  - "Billing"
  - "Administração e Operações"
source_path: "boit/billing/admin-ops/ao-cloud-centric.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Design centrado na nuvem

Observação: aplica-se apenas ao padrão de faturamento.

**Quando usar**

- Os gastos com a nuvem são significativos e estão sob escrutínio.
- As partes interessadas querem ver as cobranças da nuvem por provedor, conta, serviço, agrupamento de tags e consumidor.

**Orientar**

- Os dados na nuvem são modelados como seu próprio domínio.
- Tags e contas correspondem a:
  - Serviços ou categorias de custos.
  - Consumidores (unidades de negócios, produtos, aplicações).
- O faturamento usa tabelas de domínios na nuvem, além da configuração de unidades e preços, para gerar cobranças e taxas unitárias.

**Elementos-chave**

- Arquivos de faturamento da nuvem importados para tabelas de uso padronizadas.
- Tabelas de mapeamento de tags que vinculam tags e contas a serviços e consumidores.
- Definições de unidades específicas da nuvem:
  - GB por mês.
  - vCPU hora.
  - Contagem de solicitações, etc.
- Opcional:
  - Lógica de preços em nuvem separada para estorno versus custo.

**Relatórios típicos**

- Gastos com nuvem por provedor, região e serviço.
- Taxas unitárias da nuvem e análise de tendências.
- Gastos com nuvem por agrupamento de tags (por exemplo, aplicativo, ambiente).

**Notas de implementação**

- A disciplina na marcação não é negociável aqui. A faturação refletirá com precisão qualquer confusão existente nas etiquetas.
- Use relatórios de exceção para destacar gastos com nuvem não identificados ou mal identificados.
