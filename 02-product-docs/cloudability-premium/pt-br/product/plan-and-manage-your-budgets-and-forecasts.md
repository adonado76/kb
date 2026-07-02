---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Orçamentos e previsões"
breadcrumb:
  - "Cloudability Premium"
  - "Planejar"
source_path: "product/plan-and-manage-your-budgets-and-forecasts.html"
images:
  - "images/using_the_cost_mceclip0.jpg"
  - "images/using_the_cost_mceclip1.jpg"
  - "images/using_the_cost_mceclip2.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Orçamentos e previsões

O Budgets and Forecasts ajuda você a entender e prever seus gastos com a nuvem:

- Criação  [previsões](bf-forecast.html)  com base em padrões históricos de gastos.
- Utilização de previsões para elaborar [orçamentos](bf-budgets.html).
- Monitorar e notificar os gastos relacionados aos orçamentos.

Essas ferramentas são todas baseadas em visualizações, permitindo que você separe unidades de negócios individuais e as gerencie de forma independente. Se você estiver em um plano Pro, só poderá usar esses recursos no nível da organização. Consulte [a API de Visualizações](https://developers.cloudability.com/v1.0/ "(Abre em uma nova guia ou janela)") para obter mais informações sobre como criar visualizações por meio de programação.

Alguns dos recursos dessas ferramentas são:

- Suporte a várias opções de contabilidade, incluindo dinheiro (recomendado), amortizado (útil se a sua organização comprar RIs parciais/com tudo adiantado), ajustado (refletindo quaisquer acordos de preços personalizados que você tenha calibrado) e amortizado ajust ado.
- Configure alertas periódicos para receber notificações e gastos do mês atual.
- Visualizações simples para analisar seu orçamento,
- Em conjunto com o serviço [de Detecção de Anomalias](identify-unusual-spending-patterns-with-anomaly-detection.html).

Uso da métrica de custo (lista) para elaboração de orçamentos e previsões

O custo (lista) permite que você faça o orçamento e a previsão de seus gastos com a nuvem usando métricas de custo consistentes.

Se o uso de uma instância tiver sido coberto por uma reserva antecipada, o Custo (Total) mostrará US$ 0, enquanto o Custo (Lista) mostrará o custo sob demanda para esse uso específico. Por outro lado, no caso de taxas mensais recorrentes e taxas únicas ocasionais, o Custo (Lista) mostrará US$ 0, pois essas são provavelmente as cobranças a serem excluídas nos exercícios de orçamento e previsão. Para instâncias pontuais, o Custo (Total) exibe o custo real com grande desconto, enquanto o Custo (Lista) mostra o custo sob demanda para esse uso específico.

A [FAQ](#plan-and-manage-your-budgets-and-forecasts__FAQ) explica como o site Cloudability gera valores de custo (lista). A diferença entre o Custo (Lista) e o Custo (Total) ou Custo (Ajustado) mostra os benefícios gerais das reservas e dos preços personalizados.

![captura de tela de orçamentos e previsões](../../../../03-media/cloudability-premium/images/using_the_cost_mceclip0.jpg)

Se métricas de custo específicas não forem expostas, use Cost (List) para fornecer estorno aos consumidores (ou unidades de negócios, grupos de contas, etc.).

![captura de tela de custo](../../../../03-media/cloudability-premium/images/using_the_cost_mceclip1.jpg)

Você pode configurar notificações diárias por e-mail.

![captura de tela dos e-mails de resumo de despesas na nuvem](../../../../03-media/cloudability-premium/images/using_the_cost_mceclip2.jpg)

Perguntas frequentes

**Qual site  Public Cloud Vendors suporta o Cost (List)?**

O “Cost (List)” é compatível com AWS e GCP.

Por que o custo (lista) às vezes mostra um valor mais baixo do que as outras métricas de custo?

O principal caso de uso da métrica de custo (lista) é em relação a orçamentos e previsões. Cloudability zera os valores de determinados itens de linha, dependendo dos tipos de transação e de arrendamento, para ajudar a reduzir o ruído no trabalho de orçamento e previsão. Os itens de linha que o site Cloudability zera incluem:

- Taxas recorrentes de RI
- Taxas únicas iniciais do RI
- Créditos de preços personalizados

**Quais itens o site Cloudability informa como estão para Custo (Lista)**?

Cloudability informa os créditos extraordinários (ex. Correção de erro de faturamento) como está para Custo (Lista). No caso de GCP, Cloudability zera os créditos relativos aos descontos por uso comprometido. No entanto, os créditos para Descontos de uso sustentado são informados como estão. Novamente, trata-se do principal caso de uso do Custo (Lista) - Orçamento e Previsão. Os itens que estão sendo relatados como estão para Custo (Lista) são aqueles que os consumidores (ou unidades de negócios, grupos de contas) precisam contabilizar para os trabalhos de Orçamento e Previsão.

- **[Mês atual](../product/bf-current-month.html)**
- **[Previsão](../product/bf-forecast.html)**
- **[Orçamentos](../product/bf-budgets.html)**
