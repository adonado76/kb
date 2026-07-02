---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Como os fatores de negociação de preços influenciam os compromissos"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Noções básicas sobre gerenciamento de compromissos no Cloudability"
source_path: "product/custom_pricing_factors_across_commitments.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Como os fatores de negociação de preços influenciam os compromissos

## Propósito

Explique como o preço negociado interage com os programas de compromisso e os KPIs para que as equipes leiam os resultados de forma consistente em todas as páginas e provedores.

Os preços negociados também podem ser chamados de preços personalizados para compromissos que usaremos de forma intercambiável

## Noções básicas de precificação

**O preço negociado altera a linha de base -** as despesas comprometíveis, fornecidas em termos de equivalente sob demanda (ODE), refletem *a lista* ou as taxas *ajustadas*, dependendo da base de custos selecionada. Essa escolha flui para cada um dos cinco indicadores-chave de desempenho.

**Preços negociados alteram a taxa de desconto de compromisso -** Além de negociar taxas sob demanda, os CSPs permitem a negociação de descontos de compromisso, muitas vezes variando de acordo com o tipo de compromisso, a região, a instância, o prazo etc

**Questões de empilhamento -** O preço negociado pode ser empilhado com compromissos (aditivo) ou substituir determinados itens de linha (não empilhamento). Sempre confirme como seu contrato interage com o programa de compromisso para os serviços afetados. Como o Cloudability Commitments extrai esse preço de suas APIs públicas, podemos determinar formalmente o resultado/expectativa real de um determinado compromisso ou recomendação

## Base de custos - Lista vs. Ajustado

A base de custo determina quais preços são usados para ODE e cálculos de custo.

**Lista -** Usa tarifas públicas/lista para preços sob demanda e de compromisso.

**Ajustado -** Usa suas tarifas negociadas/personalizadas para preços sob demanda e de compromisso. Uma ressalva, conforme mencionado na introdução à seção de taxas de economia, é que a ESR usa uma combinação de preços de compromisso negociados e taxas de lista sob demanda quando a base ajustada é selecionada. Dessa forma, isso garante que o preço negociado seja incluído ao avaliar a otimização da taxa no nível mais alto.

**Implicações** - Com a base de custo ajustada, muitas vezes a demanda, o desconto de compromisso e, portanto, a ODE são todos menores do que na lista. Como resultado, a magnitude da Economia Líquida e do Custo do Compromisso provavelmente será menor, pois o desconto em um compromisso é menor, o custo aplicável ao compromisso é menor ou uma combinação de ambos.

## Regras de empilhamento

Os contratos de preços negociados diferem muito de acordo com o tamanho do cliente e o CSP. Os maiores usuários de serviços em nuvem naturalmente têm vantagem na negociação de descontos em relação aos clientes menores. Em um nível elevado, não há regras rígidas e rápidas. Trate os itens a seguir como padrões a serem verificados em seus contratos.

**Empilhamento de aditivos -** Os descontos negociados reduzem a taxa sob demanda; os descontos de compromisso são aplicados por cima, resultando em taxas efetivas mais baixas.

**Termos de substituição -** O preço negociado pode estabelecer um piso que substitui os descontos de lista para determinados SKUs/serviços.

**Prioridade do programa -** Alguns programas aplicam créditos após os compromissos, outros reduzem a base usada para calcular o valor do compromisso.

Embora o site Cloudability possa ajudar sistematicamente a expor as implicações dos preços negociados, é prudente que os profissionais do FinOps entendam os termos negociados por dentro e por fora. Confirme a ordem de empilhamento de seus serviços. A compreensão errônea do empilhamento pode levar à contagem dupla da economia esperada.

## Orientação prática

- Isolar os KPIs baseados em listas dos KPIs baseados em negociações. Misturá-los pode dar uma interpretação errada do desempenho.
- Preste atenção à sua base de custo nas páginas de compromisso. Certifique-se de que o ajuste esteja definido como padrão. Documente sua base em painéis compartilhados e exportações fora do aplicativo.
- Valide o empilhamento por família de serviço antes de prosseguir com as compras.
- Explore a base de custo da lista para entender melhor o impacto de seus termos negociados. Aproveite esse conhecimento em futuras conversas sobre preços negociados.

**Tópico dos pais:** [Entendendo os fundamentos do gerenciamento de compromissos em Cloudability](../product/commitment_management_basics.html)
