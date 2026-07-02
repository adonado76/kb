---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "AWS Lambda"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Redimensionamento em Cloudability Premium"
  - "Dimensionamento correto"
source_path: "product/rightsizing-aws-lambda.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS Lambda

Use o painel Rightsizing para ver as recomendações de otimização de recursos para o Lambda Amazon Web Services ( AWS ). O painel mostra as recomendações de rightsizing e de inatividade (encerramento). Você pode visualizar as recomendações em várias contas a partir de um único painel.

Visite [Rightsizing em Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html) para saber mais.

## Antes de começar

- Habilite as permissões corretas, que são:
  - lambda:ListFunctions
  - lambda:ListProvisionedConcurrencyConfigs
- Habilite o monitoramento aprimorado do Lambda Insights. Isso permite que o site Cloudability recupere métricas de memória para suas funções Lambda.
- Conecte Cloudability às suas contas AWS corretas.
- Para clientes com conexões já existentes com contas do AWS : crie ou baixe um modelo de credenciais atualizado do AWS em Cloudability e envie o novo modelo de credenciais para o Console de Gerenciamento do AWS.
- Visite as páginas a seguir para saber mais:
  - [Ativando o Lambda Insights](https://docs.aws.amazon.com/lambda/latest/dg/monitoring-insights.html "(Abre em uma nova guia ou janela)")
  - [Conectar Amazon Web Services](../admin/aws-credentialing-standard-enterprise-home.html)

## Explore o painel “ AWS Lambda ” (Avanço do financiamento)

O painel contém uma tabela de recomendações de dimensionamento de direitos, que fornece uma visão geral de seus recursos do Lambda. A tabela inclui as seguintes colunas:

- ID do recurso : a ID da função.
- Nome do recurso : O nome da função.
- Nome da conta : O nome da conta AWS.
- Última execução : A data em que a função foi executada pela última vez.
- Custo : O custo total da função.
- Memória atual : A quantidade de memória configurada atualmente.
- Nova memória : A memória configurada mais recomendada.
- Economia de custos : O valor da economia de custos identificada.
- Ação : Recomendação para o recurso. A recomendação pode ser uma das seguintes:

| Recomendação | Descrição |
| --- | --- |
| Dimensionamento correto | Redimensione para o tipo de recurso especificado na coluna Nova memória. |
| Finalizar | Encerre seu recurso porque ele está predominantemente ocioso. |
| Sem ação | Nenhuma ação é recomendada por padrão. No entanto, recomendações adicionais com níveis de risco mais altos podem estar disponíveis no painel Detalhes. |

Observação: Por padrão, os dados são classificados pela coluna Economia de custos. Para alterar a ordem de classificação, selecione o nome da coluna.

## Acesse o painel do AWS Lambda

Para acessar o painel do AWS Lambda :

1. Abra Cloudability. No menu de navegação, selecione Optimize > Rightsizing.
2. Selecione a guia AWS e, em seguida, selecione a subguia Lambda.

## Personalizar o painel de controle

Observação: somente a base de custo sob demanda é compatível com o Lambda. A base de custo On-Demand fornece uma comparação direta entre a memória listada na coluna Current Memory (Memória atual ) e a memória recomendada na coluna New Memory (Nova memória ), com base exclusivamente no preço On-Demand. Ele não inclui nenhum impacto potencial de instâncias reservadas (RIs) ou planos de economia (SPs). Observe que os preços sob demanda refletirão quaisquer acordos de preços personalizados que você tenha configurado em Cloudability.

Você pode definir as seguintes opções para personalizar seu painel:

1. Selecione Conta : Por padrão, o painel mostra recomendações para todas as contas. Para visualizar as recomendações de uma conta específica, selecione o nome da conta no menu suspenso Select Account (Selecionar conta).
2. Especifique a linha do tempo : Você pode optar por revisar as despesas dos últimos 10 dias ou dos últimos 30 dias. Por padrão, a opção Linha do tempo é definida como 10 dias. Para a maioria dos usuários, 10 dias é o período de tempo recomendado porque captura as tendências de desempenho mais recentes e é mais preditivo do uso futuro de recursos.
3. Aplicar filtros : Você pode adicionar filtros para incluir ou excluir dados com base em uma ou mais condições.

## Adicionar filtros com a opção de filtro

Para adicionar um filtro:

1. Selecione Add Filter (Adicionar filtro ) na barra de ferramentas.
2. No menu Add Filter (Adicionar filtro ), escolha uma Dimensão.
3. Selecione um operador para fornecer uma condição lógica.
4. Escolha um valor para refinar seu filtro.
5. Selecione Add Filter (Adicionar filtro ) para aplicar o novo filtro à página.

## Aplicar filtros com links

Você também pode adicionar filtros selecionando os valores azuis com hiperlink na tabela principal. A regra de filtro é aplicada automaticamente ao campo Filtros. Você pode selecionar apenas um valor ou parâmetro de cada coluna por vez.

## Exibir detalhes da recomendação

Para exibir os detalhes da recomendação de um determinado recurso, selecione o menu More Options (Mais opções ) (3 pontos) e selecione View Details (Exibir detalhes ).

- Para ver as descrições das dimensões e métricas de custo, visite [o Glossário de dimensões e métricas de custo](glossary-of-cost-dimensions-and-metrics.html).
- Para ver detalhes da dimensão e das métricas de utilização, acesse [o Glossário de dimensões e métricas de utilização](glossary-of-utilization-dimensions-and-metrics.html).

**Tópico principal:** [Redimensionamento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
