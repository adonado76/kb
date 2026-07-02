---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Planejamento anual e definição de taxas"
breadcrumb:
  - "Billing"
  - "Executando o ciclo de faturamento"
source_path: "boit/billing/run-bill-cycle/anual-plan.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Planejamento anual e definição de taxas

A maioria das implementações de faturamento segue um ritmo anual para planejamento e taxas, mesmo que ocorram ajustes durante o ano.

Atividades anuais típicas:

1. **Confirmar catálogo e consumidores**
   - Analise a lista de ofertas faturáveis.
   - Confirme quais consumidores (unidades de negócios, centros de custo, projetos, produtos) receberão cobranças.
   - Retire as ofertas que não são mais utilizadas e adicione novas ofertas.
2. **Alinhar com o cálculo de custos**
   - Confirme se os modelos de custos ainda suportam a oferta escolhida e a estrutura do consumidor.
   - Verifique se os principais fatores de custo, alocações e definições de serviço ainda são válidos.
3. **Definir estratégia de taxas**
   - Decida se as taxas serão baseadas no custo, custo mais margem, preço, orçamento ou híbridas.
   - Concordar sobre como lidar com a recuperação insuficiente e a recuperação excessiva:
     - Ajustar taxas futuras.
     - Ajuste único.
     - Acompanhe apenas como variação.
4. **Definir taxas-alvo**
   - Calcule as taxas unitárias preliminares por oferta, com base em:
     - Custo previsto a partir do cálculo de custos.
     - Volumes esperados.
     - Recuperação ou preço-alvo.
   - Documente as premissas que foram utilizadas nas taxas.

1. **Revisão com as partes interessadas**
   - Analise as taxas preliminares com os responsáveis pelas finanças, serviços ou produtos e os principais consumidores.
   - Capture feedback e chegue a um acordo sobre as taxas finais para o ano.
2. **Carregar taxas no faturamento**
   - Atualizar tabelas de taxas para o novo ano:
     - Datas ou períodos de vigência.
     - Valores das taxas, moedas e quaisquer tipos de taxas.
   - Valide se as taxas são calculadas corretamente nas execuções de teste.

O resto do ano consiste em executar o ciclo mensal com base nessa linha de base acordada e lidar com quaisquer alterações aprovadas.
