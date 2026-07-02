---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Visão da entidade jurídica e interempresarial"
breadcrumb:
  - "Billing"
  - "Padrões de Design e Casos de Uso"
source_path: "boit/billing/design-uc/uc-legal.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Visão da entidade jurídica e interempresarial

Observação: **aplica-se apenas ao padrão de faturamento.**

**Problema**

As equipes financeiras e tributárias precisam ter visibilidade sobre os custos de tecnologia que ultrapassam os limites das entidades jurídicas.

**Entradas**

- Tabela mestre de pessoas jurídicas (entidade, país, atributos fiscais)
- Mapeamentos:
  - Consumidores → pessoa jurídica
  - Serviços/infraestrutura → entidade prestadora
- Configuração de preços de transferência padrão de faturamento

**Passos**

1. Confirme **os mapeamentos das entidades jurídicas** :
   - Os consumidores têm atribuições de entidades válidas.
   - As entidades fornecedoras são definidas para serviços ou domínios dentro do escopo.
2. Execute modelos padrão de faturamento com a lógica de preços de transferência ativada.
3. Abra o **relatório Intercompany / Preços de transferência** :
   - Visualize as cobranças por Entidade de origem, Entidade de destino, Serviço e Período.
   - Verifique os totais em relação à saída de faturamento de alto nível.
4. Filtre para pares de entidades específicas de interesse.
5. Revise os atributos fiscais conforme necessário (por exemplo, país, tipo de serviço).
6. Use os resultados para:
   - Apoiar a preparação do diário interempresarial.
   - Forneça extratos para análise fiscal ou regulatória.

**Relatórios importantes**

- Matriz de preços de transferência (De Entidade × Para Entidade)
- Visões do estilo P&L da entidade jurídica Tecnologia
- Extrato do diário alinhado com os requisitos de contabilidade entre empresas
