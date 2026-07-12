---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Criação de métricas personalizadas"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Model Studio"
  - "Métricas de modelo"
source_path: "studio/new-uc/reference/model-studio-reference/custom-metric-creation.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Criação de métricas personalizadas

**Criação de uma métrica modelada**

1. Na guia Página inicial, clique em Novo > Métrico
2. Digite um nome e clique em OK
3. Defina o tipo de modelo como Modelo
4. Configurar o tipo de métrica (custeio, precificação ou numérico)
5. Defina o formato da tabela e o formato do gráfico conforme necessário
6. Clique em Salvar

**Criação de uma métrica calculada**

1. Na guia Página inicial, clique em Novo > Métrico
2. Digite um nome e clique em OK
3. Defina o tipo de modelo como “Calculado”
4. Insira a fórmula de cálculo do valor
5. Definir comportamento do tempo (Soma, Média ou Recalcular)
6. Configurar a formatação da exibição
7. Clique em Salvar

**Observação:** Após a criação de uma métrica calculada, os campos “Tipo de modelo” e “Cálculo de valor” passam a ser de leitura exclusiva.

**Exemplo: Métrica de desvio orçamentário**

Crie uma métrica calculada que mostre a diferença entre o orçamento e o custo:

- Nome: Variação\_Orçamentária
- Tipo de modelo: Calculado
- Cálculo do valor: =Orçamento - Custo
- Comportamento temporal: Recalcular
- Formato da tabela: =Currency($\_)

Consulte a seção 3.2.8: para criar métricas personalizadas e obter procedimentos detalhados

Consulte a seção Fórmulas e funções do 5.4: para obter informações sobre a sintaxe de cálculo

**Tópico principal:** [Métricas do modelo](../../../../studio/new-uc/reference/model-studio-reference/model-metrics.html)
