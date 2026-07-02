---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Estorno com exportação de diário"
breadcrumb:
  - "Billing"
  - "Padrões de Design e Casos de Uso"
source_path: "boit/billing/design-uc/uc-chargeback.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Estorno com exportação de diário

**Problema**

Você deseja que as saídas de faturamento direcionem os lançamentos internos de receitas e despesas para o razão geral.

**Entradas**

- Todas as contribuições de 15.1 ( PxQ showback)
- Mapeamento dos consumidores para os segmentos financeiros (centro de custos, código da empresa, etc.)
- Mapeamento de serviços para contas financeiras
- Formato do diário e regras de lançamento acordados com o departamento financeiro

**Passos**

1. Valide **as contas do período atual** usando a receita “ PxQ ” ( 15.1 ).
2. Certifique-se de que **as tabelas de mapeamento** estejam completas:
   - Consumidores → centros de custo/segmentos
   - Serviços → Contas contábeis ou modelos de contas
3. Execute os modelos de faturamento e verifique se **a tabela de saída/diário de faturamento** contém:
   - Período, Consumidor, Serviço
   - Unidades, encargos
   - Todos os campos obrigatórios do segmento Financeiro
4. Abra **o relatório de exportação do diário** :
   - Filtrar para o período atual.
   - Confirme se os totais estão de acordo com o relatório resumido de faturamento.
5. Exporte o arquivo do diário no formato acordado (por exemplo, CSV).
6. Forneça o arquivo ao departamento financeiro ou carregue-o por meio da integração.
7. Confirmar publicação:
   - Os totais em Finanças correspondem aos totais exportados.
   - Nenhuma linha falhou devido a segmentos ausentes ou inválidos.

**Relatórios importantes**

- Fatura/relatório resumido (para comparação)
- Relatório de exportação do diário
- Relatório de reconciliação: total de faturamento vs. total do diário
