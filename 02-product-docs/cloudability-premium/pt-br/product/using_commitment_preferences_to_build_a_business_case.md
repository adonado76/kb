---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Usando preferências de compromisso para construir um caso de negócios"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Guia para a gestão de compromissos"
source_path: "product/using_commitment_preferences_to_build_a_business_case.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Usando preferências de compromisso para construir um caso de negócios

## Configuração de filtros de uso de recomendações (apenas para o GCP )

Para configurar sua organização, acesse **Configurações** e selecione **Preferências de compromisso**. Aqui você poderá configurar até 10 dimensões Cloudability para aplicar ao seu uso. Selecione dimensões a partir de suas Tags e Etiquetas, Mapeamentos Comerciais ou Grupos de Contas configurados.

Para obter o melhor desempenho, escolha dimensões que ofereçam um nível moderado de variabilidade, como unidades de negócios ou nomes de aplicativos. Dimensões que apresentam grande variabilidade, como o nome do recurso, levarão a uma degradação significativa do desempenho. Se uma dimensão configurada não estiver disponível, é provável que isso se deva a uma variabilidade excessiva.

Quaisquer alterações nas suas preferências serão implementadas no próximo ciclo de processamento. Aguarde até 24 horas para que as alterações entrem em vigor e fiquem disponíveis na página de recomendações do CUD.

As dimensões são verificadas regularmente quanto à variabilidade e serão adicionadas/removidas da lista de dimensões disponíveis. Se uma dimensão se tornar muito variável, ela será removida e não estará mais disponível em seu conjunto de dados.

**Tópico dos pais:** [Guia para gerenciamento de compromissos](../product/guide_to_commitment_management.html)
