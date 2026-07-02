---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Alinhando definições de custo, consumo e unidade"
breadcrumb:
  - "Billing"
  - "Configurando o padrão de faturamento (implementação)"
source_path: "boit/billing/config-bs/bs-align-cost.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Alinhando definições de custo, consumo e unidade

A norma de faturamento precisa de uma história coerente em relação a custos, unidades e preços.

Passos:

1. **Revisar os resultados da alocação de custos**
   - Confirme que os custos fluem:
     - De torres de recursos e domínios a serviços/aplicações.
     - De serviços/aplicativos para consumidores.
2. **Defina unidades padrão**
   - Para cada domínio, mapeie as medidas brutas em unidades padronizadas, por exemplo:
     - Horas de VM → VM por mês.
     - GB brutos/horas → GB por mês.
     - Bilhetes → Bilhetes por mês.
     - Preencha a tabela de unidades de acordo com isso.
3. **Vincule volumes de domínio a serviços e consumidores**
   - Certifique-se de que as tabelas de domínio (servidores, armazenamento, nuvem, dispositivos, projetos) alimentem:
     - Volumes de nível de serviço.
     - Volumes ao nível do consumidor.
4. **Vincule os resultados do cálculo de custos às unidades de faturamento, quando necessário.**
   - Para análise da taxa unitária:
     - Combine o custo do Cálculo de custos com os volumes do Faturamento para obter o custo por unidade.
   - Use isto para:
     - Valide os preços.
     - Explique as alterações nas taxas unitárias.
