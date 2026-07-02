---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Guia para gerenciamento de compromissos - Perguntas frequentes"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Guia para a gestão de compromissos"
source_path: "product/guide_to_commitment_management_faq.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Guia para gerenciamento de compromissos - Perguntas frequentes

## Gerenciador de compromisso

## Portfólio de compromissos

**Qual é a diferença entre unidades e contagens?**

**Contagens** refere-se ao número de instâncias em uma reserva, enquanto **Unidades** refere-se às horas de instância normalizadas. Isso é relevante para RIs que se aplicam a vários tamanhos de instância dentro de uma família. Isso também ajuda você a decidir sobre o tamanho geral de um RI, de modo que uma reserva de 5 instâncias de m4.large (contagem de 5, unidades de 20) não pareça maior do que uma reserva de instâncias de 4 m4.16xlarge (contagem de 4, unidades de 512).

**Por que minha economia diminui quando vejo o custo ajustado?**

Os preços personalizados muitas vezes transferem as economias de um RI para preços personalizados. Para usar um exemplo simples, se uma instância custar $1/hour e a reserva custar $0.80/hour, uma reserva totalmente utilizada de 10 instâncias proporcionaria uma economia de $48 por dia (10 x 24 x $ 0.2 ).

Se você tiver um contrato de preços personalizado que lhe dá 10% de desconto para instâncias de computação, sua economia efetiva cairia para US$ 43.20 o por dia (10 x 24 x US$ 0.18 o).

**Por que a economia/utilização muda quando seleciono uma visualização?**

O portfólio suporta visualizações baseadas em grupos de contas. No entanto, ao selecionar uma visualização, filtre tanto por onde a reserva é de propriedade quanto por onde a reserva é aplicada. Se sua equipe adquirir RIs em uma conta vinculada e quiser ver quanto do RI foi consumido por sua equipe, você pode fazer isso com uma visualização.

Para visualizar os RIs pertencentes a uma conta específica, utilize o filtro **Conta** na página principal.

**Nas instâncias reservadas do Azure, a porcentagem de economia e os KPIs de economia ao longo do prazo incorporam taxas personalizadas do Azure?**

Se você tiver preços personalizados calibrados no aplicativo, também poderá calcular suas economias líquidas após descontos de preços personalizados.

**O meu portfólio de compromissos está com compromissos em falta. Onde estão eles?**

Cloudability Os compromissos só podem ver os compromissos que a conta do usuário pode ver. Usando o AWS como exemplo, uma conta principal de faturamento consolidado não pode ver a atividade da conta secundária que ocorreu antes de entrar na relação de faturamento consolidado. Isso significa que a conta principal não pode ver os compromissos pertencentes à conta secundária que foram adquiridos antes do início da relação de faturamento consolidado.

A solução alternativa sugerida é adicionar uma credencial IAM para a conta secundária em Cloudability, além da conta principal de faturamento consolidado. Cloudability Os compromissos poderão então ver os compromissos que foram adquiridos pela conta infantil. Cloudability irá automaticamente eliminar a duplicação de quaisquer dados sobrepostos.

## Recomendações de compromisso

- **O valor comprometido no plano de poupança é mais alto quando comparado ao RI para EC2. Você recomenda a compra de ambos?**

  Em Cloudability, é possível que o valor do compromisso em um plano de economia seja superior ao da instância reservada para AWS EC2. As instâncias reservadas oferecem um desconto quando você reserva uma determinada quantidade de capacidade de computação (medida por hora) por um período de um ou três anos, enquanto os planos de economia oferecem um desconto quando você se compromete a gastar uma determinada quantia (medida em dólares por hora) por um período de um ou três anos. A decisão de adquirir um recurso ou assumir um compromisso de gastos cabe ao líder de FinOps na organização. O uso elegível pode ser coberto por vários tipos de compromisso. Atualmente, fornecemos essas recomendações isoladas umas das outras. Por exemplo, não é recomendável adquirir todas as instâncias reservadas e planos de economia do AWS EC2.
- **Qual é a melhor estratégia para usar os compromissos? Quais são as práticas recomendadas? Você espera considerar e agir de acordo com todas as recomendações ao mesmo tempo?**

  A estratégia escolhida ao usar descontos baseados em compromisso para economizar nos gastos com a nuvem varia de acordo com a organização, o fornecedor e o tipo de compromisso. Não existe uma abordagem universalmente melhor. Como os compromissos geralmente envolvem contratos de um ou três anos, é fundamental considerar cuidadosamente os planos futuros. Em geral, é aconselhável fazer compras menores e frequentes ao longo do tempo até atingir a porcentagem de cobertura desejada. Quando esse limite for atingido, compromissos adicionais poderão ser adquiridos à medida que o uso crescer ou quando os compromissos existentes expirarem. Também é importante não renovar os compromissos se houver previsão de diminuição do uso.

  No suporte do Cloudability para compromissos, as recomendações de compromisso fornecem quais compromissos devem ser adquiridos para maximizar a economia líquida, considerando a faixa de uso selecionada. Recomendações individuais são fornecidas para cada permutação dos critérios necessários para cada tipo de compromisso em que o uso de cobertura é detectado. Em suma, as Recomendações de Compromisso do Cloudability lhe proporcionam o compromisso ideal. As organizações devem se esforçar para atingir esse nível de cobertura a fim de obter a economia ideal; no entanto, como as práticas recomendadas exigem pequenas compras incrementais, a recomendação ideal raramente deve ser posta em prática diretamente.

## GCP Perguntas frequentes específicas

**Até onde posso voltar no uso histórico para análise?**

Máximo de 2 meses: todo o uso dos meses anteriores, até o dia anterior do mês atual.

**Que dimensões posso usar para filtrar o uso para análise?**

Você pode usar qualquer dimensão configurada no Cloudability : Tags e rótulos, Grupos de contas ou Mapeamentos comerciais. Algumas dimensões podem não estar disponíveis se a variabilidade dos dados for alta – por exemplo: “nome do servidor”. Apenas dimensões com um nível de variabilidade baixo a moderado estarão disponíveis, por exemplo: “ambiente: produção/preparação”, “centro de custos: abc123””.

**Quantas dimensões posso usar para filtrar meu uso para análise?**

Você pode selecionar até 10 dimensões do Cloudability para aplicar ao seu uso.

**Quando as dimensões selecionadas serão aplicadas ao meu uso?**

As dimensões são aplicadas quando ocorre a próxima ingestão de dados de faturamento. Pode levar até 24 horas para que as dimensões sejam aplicadas ao seu uso e estejam disponíveis para serem usadas como filtros. Quando o processamento do ` GCP ` for iniciado, ele utilizará as preferências configuradas naquele momento e as aplicará.

**Posso alterar as dimensões selecionadas várias vezes?**

Sim, você pode alterar as dimensões várias vezes. Quando a ingestão dos dados de faturamento ocorrer, ela pegará as dimensões configuradas no momento e as aplicará aos dados.

**Diferentes usuários podem ter diferentes dimensões configuradas para seu uso?**

Não, as dimensões são configuradas para toda a organização.

**Como é exibido o uso nos gráficos?**

Os gráficos mostram dados por hora, com várias horas sendo calculadas em média em um único ponto, se necessário, para caber no gráfico.

**Como é calculada a recomendação padrão?**

Este é o algoritmo de propriedade Cloudability, que busca maximizar a economia e, ao mesmo tempo, equilibrar os riscos.

**Os SUDs estão incorporados na recomendação?**

Sim, se um recurso recebeu um SUD anteriormente, a economia recomendada pelo Cloudability mostrará o aumento em relação à taxa SUD, e não à taxa sob demanda.

**O nível de desconto SUD muda ao longo do mês. Qual nível de desconto SUD é utilizado?**

A média do desconto de todos os meses anteriores é utilizada e aplicada ao uso modelado para qualquer recurso que tenha recebido um desconto.

**Quais são** as diferenças entre as recomendações Cloudability **e as recomendações GCP?**

Existem 5 recursos que levarão a resultados diferentes das recomendações nativas do GCP :

1. **Dados incluídos:** Cloudability inclui qualquer recurso em execução por qualquer período de tempo, não sendo necessário que esteja em execução de forma consistente por 30 days/1 meses
2. **Período de uso:** selecionar um período de uso específico
3. **Filtragem dos dados:** Cloudability permite remover o uso da análise em um nível muito granular
4. **SUDs:** Cloudability incorpora descontos SUD nos cálculos, caso tenham sido recebidos anteriormente
5. **Risco:** os usuários do Cloudability podem analisar diferentes níveis de compromisso com base no risco

**Como os valores no console são arredondados**?

Os valores são arredondados para o número inteiro mais próximo.

**Tópico dos pais:** [Guia para gerenciamento de compromissos](../product/guide_to_commitment_management.html)
