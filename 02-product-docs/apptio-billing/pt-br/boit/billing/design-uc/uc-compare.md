---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Compare o plano, o real e o preço de um serviço essencial"
breadcrumb:
  - "Billing"
  - "Padrões de Design e Casos de Uso"
source_path: "boit/billing/design-uc/uc-compare.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Compare o plano, o real e o preço de um serviço essencial

Observação: **Padrão de faturamento primário; pode ser adaptado com o Essentials se os dados do plano forem modelados.**

**Problema**

Você deseja entender se um serviço essencial está abaixo ou acima da recuperação em relação ao plano e ao custo.

**Entradas**

- Custo real por serviço (a partir do Cálculo de Custos)
- Plano ou orçamento por serviço (a partir de ferramentas ou tabelas de planejamento)
- Preço unitário do serviço
- Unidades e cobranças reais da faturação

**Passos**

1. Confirme **se os dados do plano** foram carregados e estão alinhados com a estrutura de serviços e consumidores utilizada no faturamento.
2. Abrir um **relatório de Plano x Real x Preço** :
   - Filtre o serviço e os períodos relevantes (por exemplo, acumulado no ano).
3. Para cada período, revise:
   - Custo do plano por unidade.
   - Custo real por unidade.
   - Preço por unidade.
   - Colunas de variação:
     - Real vs planejado.
     - Preço versus custo.
4. Identifique padrões:
   - Recuperação persistente (preço < custo).
   - Recuperação persistente (preço > custo).
   - Grandes oscilações devido à variação de volume.
5. Resuma as conclusões e as ações potenciais:
   - Ajustar taxas.
   - Ajuste os fatores de custo ou alocações em Cálculo de custos.
   - Reveja o design do serviço ou os padrões de consumo.

**Relatórios importantes**

- Relatório de nível de serviço planejado x real x preço
- Relatório de variação no nível do consumidor para o mesmo serviço
- Visualização da tendência da taxa unitária para o serviço
