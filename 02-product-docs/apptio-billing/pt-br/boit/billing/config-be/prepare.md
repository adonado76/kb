---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Preparação dos dados dos consumidores"
breadcrumb:
  - "Billing"
  - "Configurando os fundamentos do faturamento (implementação)"
source_path: "boit/billing/config-be/prepare.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Preparação dos dados dos consumidores

O modelo Billing Essentials precisa de uma visão consistente de quem está sendo cobrado.

Passos:

1. **Alinhar-se à estrutura de consumidores existente em Custeio**
   - Identifique o objeto ou tabela “consumidor” usado pelo Cálculo de custos (por exemplo, unidades de negócios, centros de custo, departamentos).
   - Confirme a chave primária e a hierarquia.
2. **Garanta cobertura total**
   - Confirme se todas as entidades que devem ser faturadas aparecem no mestre de consumidores.
   - Adicione novas entradas para:
     - Novas unidades de negócios.
     - Novos centros de custo.
     - Novas entidades de projeto ou produto, se forem tratadas como consumidores.
3. **Validar mapeamentos**
   - Se o Billing usar tabelas de mapeamento (por exemplo, mapeamento de um ID externo para o ID interno do consumidor), certifique-se de que:
     - Cada ID externo nos dados de consumo corresponde a um ID interno do consumidor.
     - As entradas órfãs são resolvidas antes da primeira execução de faturamento.
