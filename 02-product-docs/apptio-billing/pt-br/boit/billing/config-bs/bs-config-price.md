---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Configurando a lógica de preço e variação"
breadcrumb:
  - "Billing"
  - "Configurando o padrão de faturamento (implementação)"
source_path: "boit/billing/config-bs/bs-config-price.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Configurando a lógica de preço e variação

O Padrão de Faturamento pode analisar custos, planos e preços. A configuração determina como isso funciona.

Passos:

1. **Definir listas de preços**
   - Decida se o preço é:
     - Tarifa única por serviço.
     - Classificado por consumidor, região ou volume.
   - Preencha as tabelas de preços com:
     - ID do serviço/oferta.
     - Período ou datas efetivas.
     - Preço por unidade.
     - Moeda e tipo de taxa.
2. **Conecte os dados do plano e do orçamento**
   - Se a variação estiver dentro do escopo:
     - Integre custos planejados e/ou volumes planejados a partir de sistemas de planejamento ou planilhas.
   - Alinhe as chaves de dados do plano aos mesmos serviços e consumidores usados no faturamento.
3. **Configurar regras de variação**
   - Decida quais tipos de variação serão rastreados:
     - Variação de volume.
     - Variação da taxa (custo vs preço).
     - Mistura ou variação estrutural, quando apropriado.
   - Configure quais variações aparecem em:
     - Relatórios de domínio (por exemplo, nuvem, aplicativos).
     - Relatórios resumidos de variação.
4. **Resultados da variação do teste**
   - Execute pequenos casos de teste:
     - Cenários conhecidos de custos, planos e preços.
     - Confirme se a decomposição da variação corresponde às expectativas.
