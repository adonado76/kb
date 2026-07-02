---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Painel de scorecards em Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
source_path: "product/benchmark-your-cloud-spend-with-scorecards.html"
images:
  - "images/scorecards_1.jpg"
  - "images/scorecards_2.jpg"
  - "images/scorecards_3.jpg"
  - "images/scorecards_4.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Painel de scorecards em Cloudability

Os scorecards ajudam você a entender se está executando bem a sua nuvem, comparando o seu uso com o de seus colegas. Os pares são empresas que usam recursos de nuvem de maneira semelhante à sua. Além disso, o Scorecards facilita a comparação de diferentes unidades de negócios dentro da sua organização para que você possa identificar as equipes que estão liderando a adoção de práticas nativas da nuvem.

Métricas de pontuação

Identificamos três componentes de uma nuvem bem arquitetada que os usuários finais podem implementar facilmente. Todos eles são pontuados em uma escala de 0 a 100, com valores mais altos indicando otimização crescente:

Rightsizing Score (Pontuação de dimensionamento ) - mede a adequação do tamanho de um recurso à carga de trabalho. Observe que isso exclui recursos pontuais, em que não há necessariamente nenhuma penalidade por excesso de provisionamento.

Pontuação de elasticidade - mede o nível de ativação e desativação dos recursos em resposta às mudanças na demanda.

Pontuação de preços - mede o quanto você está aproveitando as diferentes opções de compra para pagar o melhor preço possível por um determinado recurso.

Pontuação de marcação - mede o nível de marcação dos recursos de nuvem pelas equipes.

A pontuação geral combina esses três componentes para fornecer uma única métrica que mede a eficiência geral da nuvem.

![captura de tela dos scorecards](../../../../03-media/cloudability-premium/images/scorecards_1.jpg)

A primeira etapa é identificar a dimensão de agrupamento e a linha do tempo. A dimensão de agrupamento é o que você usará para comparar diferentes unidades de negócios em sua empresa. Os scorecards fornecem métricas de benchmarking com base na linha do tempo dos últimos 10 ou dos últimos 30 dias.

![captura de tela das dimensões de agrupamento de scorecards](../../../../03-media/cloudability-premium/images/scorecards_2.jpg)

A visualização de coorte oferece uma triagem rápida para identificar as equipes que são baratas e menos otimizadas (canto inferior esquerdo) em comparação com as equipes que são relativamente mais caras e mais otimizadas (canto superior direito).

![captura de tela da visualização de coorte de scorecards](../../../../03-media/cloudability-premium/images/scorecards_3.jpg)

Um desafio específico da otimização de sua arquitetura de nuvem é que há retornos marginais decrescentes para a otimização. A solução das instâncias de médio porte mais flagrantes geralmente economiza 20% da conta geral de nossos clientes, mas se você chegar ao ponto de olhar para uma caixa individual do m4.xlarge e debater entre mudar para um t3 e um m5a, talvez tenha atingido (ou já tenha ultrapassado há muito tempo) o ponto de retorno decrescente.

Mostramos como seu uso da nuvem se compara à distribuição de outras organizações que usam a nuvem de forma semelhante. Baseamos essas coortes de outras organizações em uma variedade de fatores, incluindo gastos mensais, serviços usados, crescimento histórico em serviços específicos, etc.

![cartões de pontuação, captura de tela do armazenamento c,oiud](../../../../03-media/cloudability-premium/images/scorecards_4.jpg)

Perguntas Frequentes

Que dimensões posso usar para agrupar unidades de negócios?

Os scorecards suportam tags, mapeamentos de negócios, grupos de contas e IDs de contas.

Quais recursos de nuvem são compatíveis com os Scorecards?

Atualmente, oferecemos suporte ao AWS EC2, ao Azure Compute e ao GCP Compute Engine. No futuro, adicionaremos suporte a outros recursos de nuvem.

E se eu não usar determinados recursos, como o Rightsizing?

Os itens para os quais não temos dados não afetarão sua pontuação. Por exemplo, se você não tiver fornecido credenciais para coletar métricas de utilização, as pontuações de Rightsizing e Elasticity serão exibidas como N/A e não serão levadas em consideração durante a pontuação.
