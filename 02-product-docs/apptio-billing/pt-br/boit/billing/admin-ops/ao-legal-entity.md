---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Visão da entidade jurídica e dos preços de transferência"
breadcrumb:
  - "Billing"
  - "Administração e Operações"
source_path: "boit/billing/admin-ops/ao-legal-entity.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Visão da entidade jurídica e dos preços de transferência

Observação: aplica-se apenas ao padrão de faturamento.

**Quando usar**

- Várias entidades jurídicas consomem e prestam serviços de tecnologia.
- Os encargos entre empresas, os impostos e os requisitos regulamentares são importantes.

**Orientar**

- A entidade jurídica torna-se uma dimensão fundamental, juntamente com o consumidor e o serviço.
- Faturamento separado:
  - Linhas de receita interna.
  - Linhas de despesas internas.
  - Possíveis sobretaxas relacionadas a impostos.

**Elementos-chave**

- Dados mestres da pessoa jurídica com atributos de país e impostos.
- Mapeamentos:
  - De consumidores a pessoas jurídicas.
  - Serviços ou infraestrutura para entidades prestadoras.
- Regras nos modelos de faturamento para:
  - Identifique fluxos entre entidades.
  - Crie linhas entre empresas.
  - Marque-os com os códigos apropriados.

**Relatórios típicos**

- Matriz interempresarial:
  - Linhas como entidades fornecedoras.
  - Colunas como entidades consumidoras.
  - Células apresentando cargas.
- Visualizações do estilo P&L da entidade jurídica para serviços de tecnologia.
- Extratos fáceis de auditar que se reconciliam com os diários.

**Notas de implementação**

- Não tente definir preços de transferência até que o modelo básico de faturamento esteja estável e reconciliado.
- Trabalhar em estreita colaboração com as equipes tributária e financeira em estruturas contábeis e documentação.
